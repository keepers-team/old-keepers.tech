---
title: Настройка uTorrent
weight: 3
---
Скачиваем и устанавливаем [uTorrent
2.2.1](https://rutracker.wiki/images/7/74/Utorrent-2.2.zip)

это самая "свежая" версия из рекомендуемых к использованию

Запустим uTorrent и настроем его.

Заходим "Настройка" - "Конфигурация"

![](/images/client-configs/xtttr-utorrent/image12.png)

![](/images/client-configs/xtttr-utorrent/image14.png)

1. Поставив здесь галочку мы наглядно отделим полностью скачанные от незавершенных загрузок при просмотре из Проводника
   Windows.  
   У недокачанных будет расширение ".!ut" Но! Я рекомендую **галочку не ставить**. Если вы решите в будущем перейти на
   другой клиент, например qBittorrent, у вас возникнут сложности с распознаванием этих файлов.

2. Полезная функция, если вы закачиваете раздачи, которые, вы уверены, будут скачаны полностью. **Галочку ставим.**
   Помогает уменьшить фрагментацию файлов и предотвратить ситуацию неожиданной нехватки свободного места на диске.
   В случае, если раздача скачается не полностью (в Хранительстве это не редкость), она все равно будет занимать место
   как целая. Плюс в том что можно быть уверенным что неожиданно место на диске не закончится, вы всегда будете знать
   сколько свободного места в данный момент.
   Если галочку не ставить - экономим место, но, надо следить чтобы диск не переполнился, и делать периодически
   дефрагментацию.
   Самым лучшим решением будет иметь два диска, на первый добавляются раздачи и загружаются, на второй переносятся
   завершенные (см.ниже, п.2)
   ![](/images/client-configs/xtttr-utorrent/image21.png)

1. Путь сохранения при добавлении торрента(ов) в автоматическом режиме из папки, указанной в п.5, либо при скачивании
   торрент-файла браузером (путь по-умолчанию, можно менять каждый раз в окне загрузки торрента)

2. Если указать здесь папку, то все незавершенные торренты (те, что в процессе закачки) будут храниться в этой папке,
   затем автоматически переносится в папку, указанной при добавлении раздачи. Полезно, если вы используете отдельный
   высокоскоростной диск для закачки и несколько для хранения, и хотите избежать фрагментации.  
   P.S: Очень полезно если у вас SMR (черепичная запись) диски, которые не любят фрагментированную запись, их надо
   ставить только под хранение.
   Закачиваемые раздачи записываются фрагментировано, а после скачивания автоматически переносятся в конечную папку (
   указанную при добавлении торрента) уже нефрагментировано.

3. В этой папке будут храниться торрент-файлы (".torrent") всех добавленных раздач.

4. В этой папке будут храниться торрент-файлы (".torrent") полностью закачанных раздач.

5. В эту папку надо копировать (!!!после добавления папка самоочищается!!!) торрент-файлы, которые надо добавить в
   клиент. Можно сразу много, но торрент-клиент будет долго "думать", лучше порциями по 50-100 торрентов за раз.
   Убедитесь что стоит галочка в п.1 и вписан путь.

6. Торрент-файлы после добавления в клиент будут самоудаляться. Удобно, но лучше галочку не ставить и удалять руками.
   Вдруг понадобятся!

![](/images/client-configs/xtttr-utorrent/image13.png)

1. Порт должен быть в диапазоне от 2000 до 65535. Также, лучше избегать \"стандартных\" портов 6881-6889

**UPnP переадресация**. UPnP переадресацию нужно включать если у вас
подключение идёт через роутер и не [проброшен
порт]({{< ref "/network-config/port-forwarding" >}})
через NAT. Если же кабель на прямую к ПК подключается или порт через NAT
уже проброшен, то лучше UPnP выключать.

Включить переадресацию NAT-PMP. Аналогично UPnP.

**В исключения брандмауэра**. Если у вас не отключен стандартный
виндовый брандмауэр, то рекомендуется её включить. [Добавление в
исключения
вручную]({{< ref "/network-config/port-forwarding#открытие-порта-в-брандмауэре-windows" >}}).

Если Ваш интернет-провайдер Билайн, убедитесь что в Личном кабинете
Билайн - Домашний интернет - Дополнительные услуги - Защита от
интернет-атак (Firewall) стоит "Средний" (рекомендуемый) либо "Защита
отключена".

Аналогично и с другими провайдерами, их защита не должна блокировать
порт. **Желательно иметь "белый" IP адрес (обычно требуется небольшая
доплата провайдеру). А также разрешить в firewall, если он у вас или у
провайдера установлен,порты, которые Вы указали в п.1**

**Проверка порта:**

Заходим [сюда](https://2ip.ru/check-port/), впечатываем
(копируем) номер порта, который указали в п.1, жмем кнопку "Проверить".
Если написано "Порт открыт" - все отлично! Если закрыт, значит у вас
либо "серый" ip адрес, либо не работает UPnP на роутере\блокирует Брандмауэр. За подробностями
[сюда](http://rutracker.wiki/%D0%9F%D0%BE%D1%80%D1%82)

2. Если вы стали Кандидатом или Хранителем, то "Прокси-Сервер" вам уже не нужен, должен быть неактивен.

Нажимаем кнопку "Применить"

Далее выставляем как на скриншотах ниже:

![](/images/client-configs/xtttr-utorrent/image18.png)

***Максимальное число соединений***. Максимальное количество соединений,
которое может инициализировать utorrent. От этого параметра напрямую
зависит количество пиров, которые могут подключиться. Нужно задать
исходя из мощности вашего роутера, то есть подбирается экспериментально.
Если производительности роутера будет не хватать, то при больших
значениях будет уменьшаться скорость отдачи и загрузки. В идеале, без
ограничения, то есть поставить большое значение, порядка 10000.

![](/images/client-configs/xtttr-utorrent/image29.png)

***"Включить сеть DHT"*** DHT позволяет найти больше пиров, но и дает
нагрузку на процессор, имеет смысл выключить если слабый компьютер.

DHT в uTorrent нормально работает если в клиенте не более 500 раздач.

Если больше ничего страшного не произойдет, просто работать те самые 500
раздач, остальные будут как если бы DHT было выключено. Чтобы DHT
полноценно работал - рекомендую клиент
[qBittorrent]({{< ref "/client-configs/qbittorrent" >}})

***"Поиск локальных пиров***" Если у провайдера развитая локальная сеть,
то можете включить, хотя последнее время включение никаких преимуществ
не дает.

**\"Вкл. управление скоростью\"** - включает новый [протокол
uTP](http://habrahabr.ru/blogs/p2p/68332/), который служит для
увеличения скорости.

***"Включить scrape-запросы"***. Нужно отключить. Нужно для отображения
количества пиров и сидов на раздаче по трекеру во вкладке \"Трекеры\".
Рутрекер не поддерживает эту функцию.

***Включить обмен пирами.*** Обязательно включить. В отличии от DHT, не
ломается при большом количестве раздач в клиенте. Хорошо помогает в
нахождении пиров, при условии, что на раздаче уже есть несколько пиров.

***Огран.скор. локальных пиров.*** Отдельный лимит для локальных пиров.
Неактуально.

***Шифрование протокола.***

Галка напротив "разрешить входящие соединения" должна стоять
обязательно!

1."*Отключено*". Если ваш провайдер не подавляет торрент-трафик и у вас
открыт порт для входящих соединений
([см.выше](#mrt3ccx5ztzl)), то выбираете "Отключено".
Пользователи, которые из-за своего провайдера могут пользоваться только
шифрованным соединением.

2\. "*Включено*". Предлагать шифрование, но в случае неудачи
устанавливать обычное соединение. То есть шифрованные соединения вам
предпочтительнее, но принципе подходят и обычные. Эта настройка имеет
смысл если ваш провайдер частично подавляет ваш торрент-трафик (т. е.
ваш клиент может и качать и отдавать по обычным соединениям, но
медленно. Кроме того, вы можете выберете этот вариант, если лично у вас
провайдер не подавляет торрент-трафик, но вы снаружи недоступны (порт
закрыт).

Такой выбор - это компромисс, потому как для шифрования оба клиента
используют дополнительные ресурсы процессора, а при такой настройке
многие начинаемые вами соединения будут шифроваться, когда они могли бы
быть обычными. Кроме того, процент «подавленных» провайдерами
пользователей неизвестен, и может быть на раздачах, где вы участвуете,
их вообще нет.

3\. *Усиленно*: предлагать шифрование, и в случае неудачи обычное
соединение НЕ устанавливать. То есть обычные соединения для вас
бесполезны (ваш провайдер полностью или слишком сильно их подавляет).

![](/images/client-configs/xtttr-utorrent/image3.png)

![](/images/client-configs/xtttr-utorrent/image20.png){

***1.Максимально число активных торрентов***, отображаются в списке
\"Активные\". Лучше всего поставить большое, недостижимое число и забыть
о данной настройке. Если поставить меньше возможного числа активных
торрентов, то некоторые их них упадут в статус \"Ожидание раздачи\"

***2.Максимум одновременных загрузок***

Количество активных торрентов. Тонкая настройка, подбирается
индивидуально. Все зависит от мощностей вашей системы, количества
дисков, оперативной памяти (объем дискового кэша) и пр.параметров.

начать стоит с установки значения \~ 60, если клиент выдерживает, ничего
не подвисает, увеличьте значение.

Цель - максимально число активных торрентов при которых система будет
стабильной, отзывчивой. Если же в диспетчере задач Windows
(Ctrl+Shift+Esc) загрузка диска(ов) все время 100%, либо uTorrent висит
в статусе \"Не отвечает\" долгое время и перестал открываться, завис -
лучше снизить количество активных торрентов.

Но, устанавливая маленькое значение вы дольше будете загружать т.к.
большинство торрентов будут простаивать в очереди.

***3.Цель сидирования.*** Рекомендуется ставить \"-1\" в поле для
коэффициента, - это соответствует раздаче без ограничений по величине
отданного. В поле \"Время раздачи\" ставим \"0\" - раздавать бесконечно.

![](/images/client-configs/xtttr-utorrent/image23.png)

По-умолчанию галку ставить не стоит.

Если торрент-клиент сильно грузит интернет-канал в рабочие часы, можно
установить галку и настроить расписание работы. Индивидуально.

![](/images/client-configs/xtttr-utorrent/image16.png)

Вкладку "Дополнительно" **НЕ ОБЯЗАТЕЛЬНО** редактировать в начале работы

Значения могут быть: true - включить, false - выключить

Подробнее углубиться в тему можно
[здесь](https://rutracker.org/forum/viewtopic.php?t=867941)

**bt.allow_same_ip** — true

**bt.auto_ul_factor** — 255

**bt.connect_speed** — сколько соединений utorrent может инициировать
в секунду. При стандартных и низких значениях торренты могут долго на
трекере обновляться и пиры будут медленней находиться. В идеале,
ограничения не должно быть. Подбирается экспериментально, в зависимости
от мощности вашего роутера. Если роутер позволяет или его нет —
поставьте большое значение, вроде 250.

**bt.no_connect_to_services** — false

\"**bt.no_connect_to_services_list**\". не подключаться к пирам по
указанным портам

**bt.use_rangeblock** — false\
блокировка подсетей ip. Если несколько пиров из одной подсети отсылают
битые блоки, то эта подсеть банится. Казалось бы, полезная функция, но,
как я понял, функции разбана подсети в utorrent не предусмотрено и за
длительное время работы может несколько таких банов накопиться. Лучше
отключить.

**diskio.coalesce_writes —** true

**diskio.coalesce_write_size —** 2147483647

Первую опцию нужно обязательно включить (включено по умолчанию). Вторая
отвечает за предел размера, после которого блоки будут объединены в один
фрагмент для последующей записи на диск. Уменьшает количество вызовов к
диску на запись файла, тем самым увеличивая производительность при
загрузке торрента. Нужно поставить 2147483647. Это максимальное значение
для данного поля. При появлении ошибки \"Ошибка! Недостаточно системных
ресурсов для завершения операции\" следует уменьшить значение вплоть до
значения по умолчанию и меньше.

**diskio.no_zero** — true

предотвращает запись нулей на весь объем раздачи при начале закачки

**net_low_cpu** — true\
позволяет чуть-чуть увеличить производительность. Включить.

**isp.bep22** — false

аналог ретрекера. Выключить. Лишняя нагрузка на utorrent, которая не
несёт практически никакой пользы.

**net_max_halfopen** — 1600

Рекомендуется выставлять в 80% от максимального числа соединений. С
дефолтного значения нужно обязательно поменять.

**net.bind_ip** и **net.outgoing_ip** - для тех, у кого несколько
сетевых интерфейсов на компьютере.

Остальные значения лучше оставить по умолчанию.

![](/images/client-configs/xtttr-utorrent/image1.png)

Размер кэша можно увеличить до 2047 Мб**, но не больше!**

**С настройкой все, приступим к работе!**

*Если у Вас в торрент-клиенте уже есть активные раздачи, и Вы хотели бы
отделить их (полезно), сначала задайте им всем свою метку по инструкции
ниже, и только потом добавляйте новые торрент-файлы. Также, чтобы
раздача этих файлов учитывалась в статистике, потом нужно будет поменять
passkey на новый, хранительский.*

Если Вы стали Кандидатом в Хранители, то Ваш Куратор прислал Вам
торрент-файлы в архиве, который распакуйте в отдельную папку, а затем
скопируйте все содержимое в папку "C:\\uTorrentAutoADD" (ту, что указали
в [п.5](#xa656pl27q25))

Файлы должны немного поменять свой вид (как на скриншоте ниже), изменив
расширение с ".torrent" на ".LOADED" Значит торрент-клиент их принял,
все хорошо!

![](/images/client-configs/xtttr-utorrent/image8.png)

Открывайте uTorrent

Вновь добавленные торренты будут без метки.

Выделим их и зададим метку, с именем того раздела, который взяли на
хранение.

![](/images/client-configs/xtttr-utorrent/image6.png)

![](/images/client-configs/xtttr-utorrent/image27.png)

Выделить вновь добавленные торренты, нажать правой кнопкой мыши
"Метка" - "Новая метка". Ввести название того раздела, который добавили.
Например, "Музыка"

![](/images/client-configs/xtttr-utorrent/image11.png)

Теперь слева окна всегда можно отсортировать раздачи ранее добавленные
от вновь добавленных по разделам, переключаясь между ними, нажимая на
название метки.

Со следующим добавляемыми разделами поступаем аналогично.

Впоследствии, после вступления в основную группу Хранителей, добавляя
торрент-файлы при помощи WebTLO метки будут присваиваться автоматически
(если указать их в настройках, в "сканируемых подразделах")

### **Делаем backup на случай сбоя.**

Зачем? В этом файле хранятся сведения о раздаваемых файлах. В случае
серьёзного сбоя программы (что не редкость) либо перебоя с
электропитанием могут слететь все раздачи, а восстановление их
сидирования займёт уйму времени.

Существует две версии uTorrent - стандартная и портативная.

1. Стандартная, установленная в "C:\\Program Files (x86)\\uTorrent" и имеющая отдельную папку с настройками.

2. Портативная, где и программные файлы и настройки находятся в одной папке. Хранители обычно используют ее, для того
   чтобы запускать несколько клиентов параллельно.
   **Создадим текстовый файл**

![](/images/client-configs/xtttr-utorrent/image26.png)

**Если СТАНДАРТНАЯ версия uTorrent**

Копируем туда

echo d\|xcopy \"C:\\Program Files (x86)\\uTorrent\"
\"C:\\backup\\uTorrent_ProgramBackup\" /S /E /H /Y

echo d\|xcopy \"C:\\Users\\ИМЯ
ПОЛЬЗОВАТЕЛЯ\\AppData\\Roaming\\uTorrent\"
\"C:\\backup\\uTorrent_ProfileBackup\" /S /E /H /Y

**Если ПОРТАТИВНАЯ версия uTorrent**

Копируем туда

echo d\|xcopy \"C:\\ПУТЬ ДО ПАПКИ uTorrent\"
\"C:\\backup\\uTorrent_backup\" /S /E /H /Y

**Сохраняем в формате .bat**

Файл - Сохранить как...\
Имя файла: uTorrent_backup**.bat**\
Нажимаем "Сохранить"
**Добавляем в планировщик заданий (если требуется полная автоматизация, запуск по расписанию)**

Запустите планировщик открыв меню "Пуск" - "Средства
администрирования" - "Планировщик заданий"

Либо вызовите окно поиска, нажав по его значку на панели задач или
воспользовавшись клавишами «WIN+S».\
![](/images/client-configs/xtttr-utorrent/image17.png)
Начните вводить в строку запрос «планировщик заданий», без кавычек.
![](/images/client-configs/xtttr-utorrent/image5.png)
Нажмите справа "Создать задачу"
![](/images/client-configs/xtttr-utorrent/image15.png)
Вкладка "Общие" вводим в поле "Имя" : uTorrent_backup  
Нажимаем кнопку "Изменить"
![](/images/client-configs/xtttr-utorrent/image28.png)
Нажимаем "Дополнительно"
![](/images/client-configs/xtttr-utorrent/image9.png)
Нажимаем "Поиск", затем выбираем СИСТЕМА ("SYSTEM")
![](/images/client-configs/xtttr-utorrent/image25.png)
Выходим, нажав "ОК", затем еще раз "ОК"
Переходим на вкладку "Триггеры", нажимаем кнопку "Создать"
![](/images/client-configs/xtttr-utorrent/image10.png)
Выставляем время срабатывания, например, "ежедневно"
![](/images/client-configs/xtttr-utorrent/image22.png)
Переходим на вкладку "Действия"  
Нажимаем кнопку "Создать"
![](/images/client-configs/xtttr-utorrent/image19.png)  
"Действие" - выбираем "запуск программы"  
Нажимаем кнопку "Обзор" указываем путь до файла uTorrent_backup.bat  
"Добавить аргументы" впечатываем -hide
![](/images/client-configs/xtttr-utorrent/image7.png)
![](/images/client-configs/xtttr-utorrent/image24.png)

Нажимаем "ОК", выходим из Планировщика.\
Теперь бэкап торрент-клиента будет производиться каждый день по
расписанию в автоматическом режиме.

[Ответы на вопросы по
uTorrent](https://rutracker.org/forum/viewtopic.php?t=219818)

### **Расшифровка флагов**

![](/images/client-configs/xtttr-utorrent/image2.png)

![](/images/client-configs/xtttr-utorrent/image4.png)
