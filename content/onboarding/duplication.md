---
title: "Дублирование"
weight: 2
---
Если раньше Хранители брали раздачи с 0 сидов, то на сегодняшний день в большинстве разделов Хранители берут на хранение
уже взятые кем-то раздачи - дублируют друг друга с целью гарантированного сохранения наследия рутрекера. Минимальное
дублирование это два Хранителя на раздаче.

Если Вы хотите задублировать кого-то (подстраховать) проделаем следующие шаги:

Откроем [**"Рабочий подфорум"**](https://rutracker.org/forum/viewforum.php?f=1584)

Выбираем раздел, например Спорт - Рестлинг, открываем, перейдя по ссылке

![](/images/onboarding/duplication/image1.png)

Мы можем видеть:

1. Название раздела
2. Общий вес раздач в разделе
3. Вес хранимых раздач в разделе
4. Список Хранителей этого раздела

Напротив каждого хранителя находится цветовая индикация хранимых им раздач. Расшифровка ниже:

![](/images/onboarding/duplication/image2.png)

Если вы видите красноватые оттенки цвета - все очень плохо и данного Хранителя необходимо срочно поддержать. Также мы
видим что весь раздел хранят два человека, ни одна раздача не задублирована (нет пересечений по вертикали)

Для сравнения снимок другого раздела

![](/images/onboarding/duplication/image5.png)

Здесь мы видим что XTTTR задублировал xsowie в диапазоне "А" и "С" (получилось дублирование х2)

OWmaker задублировал xsowie в диапазоне "В" (дублирование х2, c XTTTR не пересекается)

Volno-rez задублировал xsowie в диапазоне "А" и "В" (дублирование х3 в "А" с XTTTR и дублирование x3 в "В" с OWmaker)

Данный пример хорошо задублированного раздела. Даже избыточно, в случае Volno-rez

Более подробно можно [прочесть](https://rutracker.org/forum/viewtopic.php?p=83602811#83602811) в описании автора
скрипта.

Вернемся к нашему разделу "Рестлинг". Наша задача задублировать SW262144.

1. Для того чтобы задублировать все его раздачи, не беря во внимание что часть раздач уже задублировано - копируем его
   ник, переходим на страницу webtlo, вставляем ник в поле "Поиск по фразе" (убедитесь что стоит "в имени хранителя").
   Интервал выставляем "Не менее 0" (чтобы охватить все раздачи). Если увидите "StatsBot", то он не Хранитель, не
   обращаем внимания!

![](/images/onboarding/duplication/image4.png)

Статусы хранимого:

![](/images/onboarding/duplication/image3.png)

Далее добавляем раздачи в клиент как обычно.

1. Для того чтобы задублировать только то, что еще не задублировано другими Хранителями - делаем все то же самое, но в
   окне "Поиск по фразе" формируем запрос следующего вида:

искомый ник (SW262144),!исключаемый ник (XTTTR)

Должно выглядеть так:

![](/images/onboarding/duplication/image6.png)

Убедитесь что в выдаче остался только искомый ник (SW262144).

Далее добавляем раздачи в клиент как обычно.