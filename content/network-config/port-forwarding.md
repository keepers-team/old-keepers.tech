---
title: "Открытие/проброс порта"
weight: 2
---
Данный раздел будет полезен только тем, кто владеет белым IP. И наоборот — если вы приобрели внешний адрес, то ваши
вложения окажутся напрасными, если вы не откроете порт.

Обычно, в целях безопасности, большинство портов закрыто на роутере или в брандмауэре. С закрытыми портами клиент так же
может инициировать соединения, но вот, чтобы принимать соединения, порт всё-таки понадобится открыть.

### Какие порты нужно открыть?

Открыть вам требуется один единственный порт. Для начала вам нужно узнать или установить порт входящих соединений в
целевом торрент-клиенте. Обязательно нужно убрать галочку "случайный порт", если она есть. **Порт веб-интерфейса
открывать не нужно!** Также рекомендуется выключить UPnP и NAT-PMP, так как при ручном открытии порта в них нет смысла.

{{% expand "в qBittorrent" %}}
![](/images/network-config/port-forwarding/image9.png)
{{% /expand %}}

{{% expand "в uTorrent" %}}
![](/images/network-config/port-forwarding/image10.png)
{{% /expand %}}

### Открыт ли у меня порт?

Проверить, открыт ли тот или иной порт на компьютере можно с помощью сайта [2ip](https://2ip.io/ru/check-port/)

### Проброс порта в роутере

Этот шаг предстоит выполнить всем, кто использует роутер для выхода в интернет. Ниже описано, как связать IP и MAC-адрес
целевого компьютера и пробросить для него порт. Инструкция написана на примере роутера линейки ZyXel Keenetic, но для
других роутеров используется похожий принцип. Если вы совсем запутались в меню, то вам может помочь инструкция для
роутеров разных фирм [здесь](https://lumpics.ru/how-to-open-ports-on-router/).

[Официальная инструкция от Keenetic](https://help.keenetic.com/hc/ru/articles/360000360760-Переадресация-портов)

В браузере набираем в поисковой строке 192.168.1.1 (Для некоторых роутеров 192.168.0.1)
Появится окно ввода логин\пароль. Если не меняли, то логин admin \ пароль на самом роутере указан

Находим “Домашняя сеть”

![](/images/network-config/port-forwarding/image1.png)

Регистрируем компьютер в сети, чтобы у него был постоянный адрес.

![](/images/network-config/port-forwarding/image2.png)

Заходим в “Безопасность”

![](/images/network-config/port-forwarding/image3.png)

Настраиваем сначала на TCP

![](/images/network-config/port-forwarding/image5.png)

Жмем “Сохранить”
Затем на UDP

![](/images/network-config/port-forwarding/image7.png)

Заходим на [https://2ip.io/ru/check-port/](https://2ip.io/ru/check-port/), вписываем номер порта, жмем “Проверить”

{{% notice note %}}
Для того, чтобы это сработало, порт должен быть не только проброшен в роутере, но и открыт на целевой машине, если там
включен какой-либо фаервол (Брандмауэр Windows, ufw или правила iptables на Linux). Инструкции для конкретных случаев
написаны ниже
{{% /notice %}}
<!-- В notice не хотят прикрепляться ссылки вида {{< relref "#anchor" >}} -->

Если “Порт открыт” дело сделано, вы молодцы! Если нет, проверяем все ли мы сделали правильно, и еще раз удостоверьтесь
что провайдер выделил вам реальный (белый) IP адрес.
![](/images/network-config/port-forwarding/image15.png)

Для гарантии безопасности рекомендуется удалить UPnP из роутера, для этого перейдите на вкладку “Система”

![](/images/network-config/port-forwarding/image14.png)

Нажмите “Рекомендованный набор”
Уберите галочку рядом с “Служба UPnP”, нажмите “Установить”

### Открытие порта в брандмауэре Windows

Открытие порта начнем с настройки Брандмауэра windows (firewall)  
Нажимаем Пуск - Панель управления - Система и безопасность - Брандмауэр Защитника Windows

![](/images/network-config/port-forwarding/image6.png)

Нажимаем “Дополнительные параметры”

![](/images/network-config/port-forwarding/image13.png)

Слева нажимаем “Правила для входящих соединений” справа “Создать правило”

![](/images/network-config/port-forwarding/image12.png)

Выбираем “Для порта”

![](/images/network-config/port-forwarding/image8.png)

Вписываем номер порта, указанный в “Порт для входящих соединений” торрент-клиента

![](/images/network-config/port-forwarding/image4.png)

Затем несколько раз жмем “Далее”, присваиваем имя

![](/images/network-config/port-forwarding/image11.png)

Жмем “Готово”.
Точно также воздаем разрешение для этого же порта, но уже по протоколу UDP

### Открытие порта в ufw на Ubuntu

Если вы используете ufw, то порт можно открыть командой `sudo ufw allow in <порт клиента>`. Протокол в данном случае не
указывается, так как торренты могут работать и по TCP, и по UDP. Иногда, если установлен пакет **iptables-persistent**
или**netfilter-persistent**, ufw может страдать "потерей памяти" после перезапуска. В таком случае после настройки
правил нужно выполнить команду `sudo netfilter-persistent save`, которая сохранит фильтры и применит их при загрузке.

### Открытие порта в iptables на Linux

Для всех (наверное) дистрибутивов Linux порт можно открыть, используя iptables:

```bash
iptables -A INPUT -p tcp --dport <порт клиента> -j ACCEPT

iptables -A INPUT -p udp --dport <порт клиента> -j ACCEPT
```

Данные команды должны выполняться с правами root, они отроют порт на всех интерфейсах для TCP и uTP. Учтите, что правила
iptables сбрасываются при перезагрузке ПК, поэтому после добавления правил вам нужно сохранить их утилитой
**netfilter-persistent**, **iptables-save** или подобной, в зависимости от вашего дистрибутива.
