---
title: "Запуск webTLO на nginx"
---

# Запуск webTLO на nginx

Всё делаем от root.
Ставим пакеты:
```shell
pacman -Syu nginx-mainline php php-fpm php-sqlite
```
* актуально для php7.4, для более старых версий нужно больше пакетов

Если проект выгружаем Git'ом, то ещё ставим git. Можно обойтись выгрузкой zip файла со всем проектом в /var/www/webtlo

## Настройка php-fpm

Нужно выдать права на запись пользователю, под которым работает php-fpm, иначе процесс не сможет сохранять базу данных. Проще всего сменить владельца:
```shell
chown -R http: /var/www/webtlo
```

В /etc/php/php.ini убираем коментарий с extension=pdo_sqlite

## Настройка nginx

Делаем директорию с подгружаемыми конфигурациями

```shell
cd /etc/nginx
mkdir conf.d
```

в nginx.conf в самый конец, но перед последней } пишем:
`include conf.d/*.conf;`

Создаём конфиг nginx для webTLO:
`nano conf.d/webtlo.conf`:

```nginx
server {
        listen 8099; # порт, на котором будет жить WebTLO
        server_name _;
        # Путь к папке с кодом
        root /var/www/webtlo/;
        index index.php;
        # Обработка php файлов с помощью fpm
        location ~ \.php$ {
                try_files $uri =404;
                include /etc/nginx/fastcgi.conf;
                # таймаут, по умолчанию 60 секунд. При большом количестве раздач необходимо увеличивать значение
                fastcgi_read_timeout 600s;
                fastcgi_pass unix:/run/php-fpm/php-fpm.sock;
                }
    }
```

Проверяем конфиг nginx, что не накосячили в синтаксисе `nginx -t`

## Сервисы для запуска

Говорим, что сервисы надо запустить сейчас и запускать автоматически после перезапуска системы:
```shell
systemctl enable --now nginx.service php-fpm.service
```

Если что-то не завелось, смотрим логи nginx (но если проверяли конфиг через `nginx -t`, то это, скорее всего, пытаемся использовать уже занятый порт):
```shell
systemctl status nginx
```
