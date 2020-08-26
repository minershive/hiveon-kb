---
title: Установка драйверов AMD
parent_category: Гайды
path: /guides-amd_dr_ru
lang: ru
parent_category_path: /guides_ru
order: 1
meta_description: Узнайте, как установить или же обновить драйверы AMD.
---

Скрипт для простой установки драйверов AMD на Hive OS и ОС на основе Ubuntu: https://github.com/CryptoLuigi/AMD_Installer.

**Обратите внимание:** Драйверы с суффиксом 18.04 требуют обновления операционной системы.

**Обратите внимание:** Мы рекомендуем не удалять драйверы при обновлении.

<pre><code>
root@Miner:~# ./amd_install.sh
Stopping screen session 21798

Please note Drivers with the 18.04 suffix require an OS upgrade
1) 16.40-348864-ubuntu-16.04   10) 18.10-572953-ubuntu-16.04
2) 16.60-379184-ubuntu-16.04   11) 18.20-606296-ubuntu-18.04
3) 17.10-429170-ubuntu-16.04   12) 18.30-641594-ubuntu-18.04
4) 17.10-450821-ubuntu-16.04   13) 18.30-641594-ubuntu-16.04
5) 17.30-458935-ubuntu-16.04   14) 18.40-673869-ubuntu-16.04
6) 17.30-465504-ubuntu-16.04   15) 18.40-697810-ubuntu-18.04
7) 17.40-492261-ubuntu-16.04   16) 18.50-725072-ubuntu-18.04
8) 17.40-483984-ubuntu-16.04   17) Quit
9) 17.50-511655-ubuntu-16.04
Please enter your choice Drivers:
</code></pre>

Программа спросит, хотите ли вы удалить текущие драйверы перед установкой новых.

Для пошаговой установки введите следующие 3 команды:

`wget https://raw.githubusercontent.com/CryptoLuigi/AMD_installer/master/amd_install.sh`

`chmod +x ./amd_install.sh`

`./amd_install.sh`

Мы протестировали скрипт, и он работает. Тем не менее, учтите, что он все еще в бета-версии, так что не стесняйтесь сообщать о проблемах. Пожалуйста, предоставьте как можно больше деталей при обращении (например, что вы сделали недавно, что вы запускаете, и так далее).

Также, чтобы лучше понять процесс установки драйверов AMD, вы можете посмотреть данное видео.

**Внимание!** Видео на английском языке.

<a href="https://youtu.be/58pia_gBZ4s
" target="_blank"><img src="http://img.youtube.com/vi/58pia_gBZ4s/0.jpg"
alt="Hive OS Tutorial: Easy AMD Driver Install/Update" width="630" height="400" border="10" /></a>

>Для обновления драйверов AMD - обновите ваш образ Hive OS до последней версии. Отдельно обновлять драйверы AMD не рекомендуется.
