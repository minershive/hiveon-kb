---
title: GPU ЧаВо
parent_category: Гайды
path: /guides-gpu_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---
## GPU ЧаВо
### Ферма постоянно перезагружается. Если через Hive Shell включить logs-on, на что обращать внимание?
Нужно обратить внимание на строки лога, которые появляются непосредственно перед уходом рига в оффлайн. Можно там же, в Hive Shell, запустить команду
`tail -f /var/log/syslog` (прервать команду можно нажатием клавиш Ctrl-C).

Когда риг уйдет в оффлайн, Hive Shell разъединится, а на экране как раз останутся именно эти строки.

### Как снизить энергопотребление GPU?
Для снижения потребления ваших GPU (при использовании Hive OS), вы можете указать параметры напряжения ядра и памяти индивидуально для каждой карты.

Для этого зайдите на вашем воркере в раздел **Разгон** и укажите нужные значения в профиле разгона. Обратите внимание, что в графе **Состояние памяти** вы можете указать как индекс состояния 0, 1, или 2, так и напряжение в мВт.

Так же для снижения энергопотребления вы можете воспользоваться режимом агресивного андервольтинга:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu1.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu1.png"
  />

### Как проверить, есть ли интернет на GPU риге?
Для того, чтобы проверить наличие интернета на вашем риге, вам необходим монитор и клавиатура для физического подключения к ригу. После загрузки Hive OS  введите команду `net-test`. После ее применения вы увидите статус доступности серверов Hive OS.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu2.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu2.png"
  />

### Ошибка 511. Почему она возникает?
Данная ошибка возникает в большинстве случаев из за неисправности райзера видеокарты. Проверьте разъем питания на райзере на предмет подгоревшего провода, и замените райзер.

### Что такое DPM на видеокартах AMD?
DPM - это таблица частот ядра и соответствующих вольтажей этих частот. Эту информацию можно увидеть командой `amd-info`. Карта меняет частоты ядра согласно этой таблице, ступенями.

Производитель с большим запасом выставляет вольтаж для каждой ступени частоты ядра. Наша задача для выбранной частоты ядра, прописанной в DPM, подобрать наименьшее значение вольтажа, но при этом чтобы карта продолжала копать стабильно. Так мы получаем пониженное потребление без потери производительности. Это и есть даунвольт. Пример даунвольтов:

- DPM 3 825
- DPM 4 875
- DPM 5 925

По умолчанию, Hive OS использует значение DPM 5. А стоковое значение на Windows - DPM 7.  Указание конкретной частоты ядра работает, но не на всех картах. А вот использование значения DPM - на всех.

### Как риги объединить/перенести на другую ферму?
Перейдите в настройки рига:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu3.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu3.png"
  />

Затем перейдите на нижнюю часть страницы и нажмите **Расширенные настройки**:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu4.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu4.png"
  />

Выберите из выпадающего списка нужную ферму, и нажмите на кнопку **Перенос**:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu5.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu5.png"
  />

### Запуск mc на риге
Для запуска редактора mc, запустите на вашем воркере Hive Shell. Затем введите команду `mc`.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu6.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu6.png"
  />

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu7.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu7.png"
  />

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu8.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu8.png"
  />

### Как через Hive-Shell проверить, действительно ли завис риг?
Зайдите по Hive Shell на **рабочий риг, находящийся в той же локальной сети что и зависший**.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu9.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu9.png"
  />

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu10.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu10.png"
  />

Введите вот эту команду: `ssh user@”Ip_адрес_неработающего_рига”`:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu11.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu11.png"
  />

Далее введите свой пароль от этого рига. Последний ip-адрес рига можно посмотреть на панели управления Hive OS.

Теперь можно проверить, действительно ли риг завис или отключился, или же это какой-то "глюк" сервера веб-интерфейса. Команда `exit` возвращает каждый раз по цепочке обратно.

### Что такое LA (Load Average)?
LA это количество ядер процессора, требуемых для выполнения всех текущих задач. Если у вас Celeron G3930 с двумя ядрами, то LA 2 свидетельствует о 100% загрузке системы. Для Ether это очень ненормально, а вот для современных алгоритмов — вполне подходит.

Максимальное значение LA может быть каким угодно. Это длина очереди к процессору, выраженная в количестве ядер этого процессора. LA всегда считалось в количестве вычислительных устройств, требуемых для выполнения всей текущей очереди задач.

При майнинге Beam и Cuckoo на слабых процессорах, LA может доходить до 3-4. Если не нравится красный цвет индикатора, вы всегда можете настроить пороговое значение вот здесь:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu12.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\gpu\gpu12.png"
  />

Три значения: LA сейчас / среднее LA за 5 минут / среднее LA за 15 минут.