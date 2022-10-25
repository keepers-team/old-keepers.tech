---
title: "Запуск transmission в docker-compose"
---

# Запуск transmission в docker-compose

Пример конфига в файле docker-compose.yml:
```yaml
version: "2.1"
services:
  transmission:
    image: ghcr.io/linuxserver/transmission
    container_name: transmission
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Europe/London
      - TRANSMISSION_WEB_HOME=/combustion-release/ #optional
      - USER=!!! # пользователь для доступа WebTLO
      - PASS=!!! # пароль
      - WHITELIST= # список IP/масок через запятую, с которых возможен доступ в вэб-морду; крайне рекомендуется задать, если сервер выпячен в интернет
    volumes: # выпячиваем файлы на хост-систему, маст хэв для бекапов и переноса
      - /<тут некий путь>/transmission/config:/config
      - /<тут некий путь>/transmission/downloads:/downloads
      - /<тут некий путь>/transmission/watch:/watch # у меня WatchDir не работает...
    ports: # маппинг портов
      - 9091:9091 # web доступ
      - 51413:51413 # раздачи
      - 51413:51413/udp # раздачи UDP
    restart: unless-stopped # автоматически запускать контейнер при любой остановке, кроме ручной
```

Для запуска выполнить в директории с файлом docker-compose.yml:
```shell
docker-compose up -d .
```
