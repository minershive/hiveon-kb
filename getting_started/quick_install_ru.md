---
title: Быстрая Установка Hive OS
---

## Быстрая Установка Hive OS

Перед установкой Hive OS на ваш риг, мы рекомендуем сначала <a href="https://the.hiveos.farm/">создать аккаунт</a>, или же войти в уже <a href="https://the.hiveos.farm/">существующий</a>.

### Добавьте воркер
После создания аккаунта, вас встретит вкладка обзора вашей фермы. Нажмите кнопку **add one**, чтобы добавить новый риг.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/add_worker.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/add_worker.gif"
  />

_Добавление нового воркера_

Введите имя и пароль для вашего рига. При желании, вы также можете добавить описание рига. Затем нажмите **Add**.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/worker_info.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/worker_info.gif"
  />

_Добавление данных воркера_

Вы увидите экран с множеством альтернативных вариантов установкиwith (ознакомиться с ними можно [здесь](getting_started\start_worker_setup_ru.md). Нажмите `rig.conf`, чтобы скачать этот файл.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/dl_rig_conf.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/dl_rig_conf.png"
  />

_Скачивание файла rig.conf_

### Скачайте образ
Перейдите на <a href="https://hiveos.farm/install/">эту страницу</a>, чтобы скачать последнюю версию Hive OS. Вы сможете выбрать .zip или .torrent файл.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/install.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/install.png"
  />

_Выбор варианта загрузки_

### Запишите образ
Вставьте USB-накопитель (объемом 8Gb или больше) в ваш компьютер. Пользователи Windows, MacOS и Linux users могут использовать <a href="https://sourceforge.net/projects/win32diskimager/">Win32 Disk Imager</a>, <a href="https://etcher.io/">Etcher</a>, <a href="https://rufus.akeo.ie/">Rufus</a> или любое другое обеспечение по своему выбору. В этом примере показано, как использовать Etcher для записи образа:

**1. Выберите образ**

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_select.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_select.png"
  />

**2. Выберите накопитель**

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_drive.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_drive.png"
  />

**3. Запишите**

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_flash.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_flash.png"
  />

Подождите, пока образ запишется на ваш USB-накопитель.

Как только образ запишется, вы увидите новый накопитель под названием “Hive”. Нажмите на него, чтобы получить доступ к содержимому.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/hive_drive.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/hive_drive.png"
  />

Добавьте ранее загруженный файл `rig.conf` к накопителю с образом Hive.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/hive_drive_conf.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/hive_drive_conf.png"
  />

Извлеките USB-накопитель из вашего компьютера и вставьте его в риг.

### Установите образ
Вставьте USB-накопитель в ваш риг. Загрузите риг и подождите, пока он установит образ. Как только процесс завершится, вы увидите этот экран.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/os_install.jpeg?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/os_install.jpeg"
  />

_Пример экрана, который вы должны увидеть после успешной установки_

Готово! Риг присоединится к Hive, и вы сможете начать с ним работать.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/new_rig.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/new_rig.png"
  />

_Ваш новый риг появится в вашей ферме_

А вот [здесь](getting_started\start_dashboard_setup_ru.md) можно узнать, как настроить ваш риг.
