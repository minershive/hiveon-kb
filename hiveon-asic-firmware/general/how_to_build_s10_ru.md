---
title: Как сделать Antminer S10 из двух Antminer S9
parent_category: Прошивка Hiveon ASIC
category: Общие Вопросы
path: /hiveon-asic-firmware-general-how-to-build-s10_ru
lang: ru
parent_category_path: /hiveon-asic-firmware_ru
category_path: /hiveon-asic-firmware-general_ru
order: 1
meta_description: Собираетесь собрать Antminer S10 из двух Antminer S9? Эта инструкция поможет вам.
---

Antminer S10 — это комбинация двух Antminer S9, подключенных к одному источнику питания. Чтобы превратить ваши Antminer S9 в Antminer S10, следуйте этим шагам:

1. Вам понадобятся **4.7 K кОм SMD** резисторы (9 штук) и **18 разъемы** (3 штуки). Учтите: чем резисторы меньше, тем проще вам будет их установить.

2. Теперь нужно припаять 3 разъема “в” желтые прямоугольники:

<img src="https://lbd.hiveos.farm/kb/images/buildings10image1.png" alt="buildings10">

У вас должно получиться нечто подобное:

<img src="https://lbd.hiveos.farm/kb/images/buildings10image2.png" alt="buildings10">

3. Взгляните на эту картинку ещё раз:

<img src="https://lbd.hiveos.farm/kb/images/buildings10image1.png" alt="buildings10">

Рядом с каждым разъемом нужно установить по 3 резистора. Мы обозначили нужные “локации” красными прямоугольниками.

4. После установки вы можете прошить ваш ASIC прошивкой Hiveon ASIC S10. Её можно скачать [здесь](https://hiveos.farm/asic/). Доступны обе версии прошивки: улучшенная и стандартная. Узнать, в чем именно заключается разница между стандартной и улучшенной прошивками, можно [здесь](https://hiveos.farm/hiveon-asic-firmware-general-standard_improved_firmware_ru/).

Если у вас стандартный блок питания, мы рекомендуем выбирать профили разгона до 1600 W. Если же вы хотите достичь более высоких показателей (выше 21.5 TH/s), вам понадобится более мощный блок питания.
