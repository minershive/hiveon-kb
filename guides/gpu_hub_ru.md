---
title: GPU Hub
parent_category: Гайды
path: /guides-gpu_hub_ru
lang: ru
parent_category_path: /guides_ru
order: 1
meta_description: GPU Hub может существенно упростить управление крупной GPU-фермой. Узнайте, как именно с ним работать.
---

<a href="https://youtu.be/t2FyPFxhThU
" target="_blank"><img src="http://img.youtube.com/vi/t2FyPFxhThU/0.jpg"
alt="Обзорное видео по Hive OS"></a>

GPU Hub – это инструмент, облегчающий жизнь пользователям с большими фермами.
Здесь вы можете управлять всеми вашими видеокартами по всей ферме: видеть список GPU, их статусы онлайн/офлайн, недостающие хэшрейты, невалидные шары, OEM-производителей, бренды, производителей памяти, размер VRAM, разгон и супер-важную утилиту для массовой перепрошивки VBIOS.

Но прежде чем подробнее рассмотреть утилиту для прошивки, команда Hive хотела бы подчеркнуть, что, если у вас нет опыта в перепрограммировании ПЗУ карт, будьте осторожны при использовании этого инструмента, если Вы не уверены в своих знаниях и намерениях. Существует высокий риск “окирпичить” ваши GPU, если что-то было сделано неправильно! Команда Hive не несет ответственности за любое поврежденное оборудование, и вся ответственность лежит исключительно на конечном пользователе.

Теперь подробнее обо всех функциях, доступных на странице GPU Hub.

<img src="https://lbd.hiveos.farm/kb/images/gpuhub1.png" alt="gpuhub">

### Фильтры
На этой странице Вы можете сортировать и находить свои GPU по различным ригам, используя различные типы фильтров:

<img src="https://lbd.hiveos.farm/kb/images/gpuhub2.png" alt="gpuhub">

Вы можете отсортировать GPU по следующим параметрам:

**Online/Offline** – просмотреть, какие работают, а какие нет.

**С ошибками** (With Errors) – это те GPU, которые по какой-то причине не работают должным образом и не показывают хэшрейт, имеют отсутствующие или неисправные драйверы, достигли высоких/критических температур и т. д.

**Имя Воркера** (Worker Name) – сортирует весь список GPU по именам воркеров.

**Проблемы** (Issues) – фильтр по определенной проблеме:
- Перегрев (Overheat)
- Отсутствует хэшрейт (Missing Hashrate)
- Неверные шары (Invalid Shares)
- Карта отсутствует (Missing Card)

**OEM** – сортировка по производителю GPU.

**GPU** – сортировка по модели GPU.

**Память** (Memory) – сортировка по производителю и типу VRAM.

**Размер** (Size) – сортировка по объему VRAM.

**VBIOS** – фильтр GPU по их статусу VBIOS:
- Прошит (Flashed)
- Последняя неудачная попытка (Last Failure)
- В процессе (In Process)
- Предварительно выбранный (Preselected)
- Нет VBIOS (No VBIOS)

**Разгон** (Overclocking) – фильтр GPU по их состоянию разгона (оверклоку):
- Все (All)
- С разгоном (With OC)
- Без разгона (Without OC)

GPU также можно отсортировать по созданным вами тегам, монетам, которые в настоящее время добываются, используемым майнерам и производителю микросхем GPU: AMD или Nvidia.

### Хранилище VBIOS
Этот инструмент позволяет Вам создать библиотеку модернизированных VBIOS для GPU вашей фермы, сохраняя их и позволяя массово прошивать эти ПЗУ на несколько видеокарт.

В приведенных ниже примерах используется GPU AMD.

<img src="https://lbd.hiveos.farm/kb/images/gpuhub3.png" alt="gpuhub">

Работать с хранилищем VBIOS ПЗУ довольно просто. Начните с нажатия кнопки "Добавить VBIOS". Появится новое окно загрузки VBIOS, и здесь Вы можете выбрать между AMD или Nvidia. Затем добавьте файл ПЗУ из локального хранилища, нажав "Выбрать файл". При желании Вы можете ввести имя ПЗУ и описание ПЗУ. Очень удобно, когда у Вас есть несколько доступных файлов для одного и того же типа ГП и для общих организационных целей.

<img src="https://lbd.hiveos.farm/kb/images/gpuhub4.png" alt="gpuhub">

Нажмите "Загрузить", и вы увидите, что ПЗУ отображается в списке хранилища над вашими ГП. Количество ПЗУ, которое можно сохранить, не ограничено. После того, как Вы загрузите ПЗУ, можете при необходимости загрузить его в локальное хранилище или отредактировать описание и имя. Также ПЗУ могут быть удалены из списка, если они вам больше не нужны.

<img src="https://lbd.hiveos.farm/kb/images/gpuhub5.png" alt="gpuhub">

*Пример ПЗУ в списке*

### Панель Инструментов
Как только Вы выберете какое-то количество ГП, вы увидите новую панель инструментов с различными действиями. Все эти действия будут применяться ко всем выбранным ригам и ГП.
Слева направо:

<img src="https://lbd.hiveos.farm/kbase/images/forum/f40f53f24ab2bf17dbdf0061b9d9f1fd41bf9fd5.png">

1. Действия по питанию

<img src="https://lbd.hiveos.farm/kbase/images/forum/f5b504370848c8478f575f73fccd62a5d97f595b.png">

Вы можете выполнить следующие действия на всех ваших ригах:
- Перезагрузка
- Выключение
Завершение работы и загрузка через 30 секунд – обратите внимание, что это не будет работать со всеми материнскими платами. Обратитесь к производителю оборудования для получения дополнительной информации о поддержке wakealarm.

2. Прошивка VBIOS

<img src="https://lbd.hiveos.farm/kbase/images/forum/f3a886240f209860d64faa7e885afc19dc0b608b.png">

После нажатия на это действие откроется новое контекстное окно с вариантами выбора ПЗУ, которое вы хотите прошить для всех выбранных вами ГП. Подробности процесса перепрошивки описаны далее в этой статье.

3. Шаблоны разгона

<img src="https://lbd.hiveos.farm/kbase/images/forum/147921a211fef1549b4af6839f5ec1281acec4cd.png">

Здесь вы можете установить глобальные разгоны для всех выбранных видеокарт. Они могут быть установлены одновременно как для AMD, так и для Nvidia, но имейте в виду, что разгон предпочтительнее устанавливать только для ГП одного типа.

<img src="https://lbd.hiveos.farm/kb/images/gpuhuboctemp2.png" alt="gpuhub">

Если Вы никогда раньше не делали разгон в Hive OS, прочитать об этом больше можно в [этой статье](https://medium.com/hiveon/getting-started-with-hive-os-overclocking-profiles-basics-5e239e4f1ae5).

4. Действия майнера

<img src="https://lbd.hiveos.farm/kbase/images/forum/bf93d014bb6bfc82b28f89a586f9b271ae877105.png">

При нажатии на действие доступны две опции:
- Остановка майнера
- Перезагрузка майнера

### Перепрошивка VBIOS ПЗУ
После загрузки необходимых ПЗУ в Хранилище и выбора ГП, которые вы хотите перепрошить, нажмите кнопку "Перепрошить VBIOS" на панели инструментов, и откроется новое контекстное окно.

<img src="https://lbd.hiveos.farm/kb/images/gpuhubflashvbios.png" alt="gpuhub">

Вы можете настроить перезагрузку ригов после перепрошивки ПЗУ.
Также можно принудительно перепрошить ПЗУ, игнорируя любые проверки безопасности. Эта опция пригодится при перепрошивке несертифицированного ПЗУ.

Позвольте еще раз напомнить, что не следует прошивать ПЗУ для нескольких типов ГП, которые имеют разные технические параметры: производителя, поставщика памяти, размер ОЗУ и т. д.

<img src="https://lbd.hiveos.farm/kbase/images/forum/50d664435e37fa70123ed976b433efd78b89b877.png">

После выбора одного из ПЗУ из списка, при условии, что у вас их несколько, окно закроется, и в верхней части списка видеокарт появится новое уведомление. При нажатии на "Прошить Карты" все выбранные ГП будут прошиты выбранным вами ПЗУ.
Вы можете нажать "Отмена", если вы передумали.

***Всегда имейте резервную копию оригинальных ПЗУ ваших ГП на случай, если вам это понадобится.
Если вы все еще не уверены, что делаете, не стоит использовать эту функцию.***

После того, как все настроено, вы увидите текст "Подготовка VBIOS" с названием ПЗУ в каждом выбранном ГП и указанием, какие из них будут прошиты. Нажмите "Прошить Карты", чтобы продолжить.
Процесс перепрошивки может занять некоторое время в зависимости от количества ГП. Дальше в списке Вы увидите ГП, которые были успешно или безуспешно прошиты.

<img src="https://lbd.hiveos.farm/kb/images/gpuhubafterthatfailed1.png" alt="gpuhub">

Вы также можете по отдельности прошить ПЗУ на один ГП, нажав на кнопку с тремя точками в левой части списка видеокарт.
Процедура идентична перепрошивке нескольких ГП, просто нажмите "Прошить Карты" и подождите. Кроме того, вы можете индивидуально разогнать каждый ГП из этого же всплывающего меню.

<img src="https://lbd.hiveos.farm/kb/images/gpuhubafterthatfailed2.png" alt="gpuhub">

GPU Hub - это мощный инструмент, который при правильном использовании значительно облегчает процесс управления картами.
***Но всегда будьте осторожны и перепроверяйте, что делаете, когда прошиваете ПЗУ. Вся ответственность лежит на вас.***

Успехов и приятного майнинга!
