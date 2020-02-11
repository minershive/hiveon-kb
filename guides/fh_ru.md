---
title: Farm Hash
parent_category: Гайды
path: /guides-fh_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

## Farm Hash
Значение FARM_HASH можно найти в веб интерфейсе на закладке Account. Используя это значение, вы можете быстро и легко добавить риги в вашу ферму на Hive OS без необходимости создания ригов через веб интерфейс и указания RIG_ID. Это уникальный хеш для каждой фермы.

Запишите образ Hive как обычно на Flash/SSD. После записи диска вы найдете том с меткой HIVE в Windows. Он содержит конфигурационные файлы Hive OS, здесь же вы найдете файл с названием `rig-config-example.txt`. Откройте его, отредактируйте и сохраните на диске с именем `rig.conf`.
<pre><code>
# THIS IS A STARTING EXAMPLE, REAL CONFIG IS IN rig.conf
# Normally the rig will ask for password at first run.
# Optionally you can put rig ID and password and Save As to "rig.conf" for a fresh start

HIVE_HOST_URL="https://api.hiveos.farm"

# Find out your hash in farm's settings on the web
# The rig will autoregister itself in your account after the first run
FARM_HASH=<поместите ваш Farm Hash сюда>

# Password used for the rig
RIG_PASSWD=

# If you know rig id before creation you can set it here leaving FARM_HASH blank
RIG_ID=

# Disable GUI (x server), uncomment to disable it
#X_DISABLED=1

# Linux system language, like zh_CN.UTF-8, pt_PT.UTF-8, de_DE.UTF-8
#SYSTEM_LANG=en_US.UTF-8
</code></pre>
Поместите сюда значение Farm Hash, скопированное из веб панели, таким образом:

`FARM_HASH=f019745da6ba65630b28ef3c92608e7022b4bf76`

Не нужно ничего писать в переменные RIG_ID или RIG_PASSWD.
Это все что нужно прописать в файле `rig.conf`.
Теперь включайте ваш риг и он подключится к вашей ферме на Hive OS автоматически.
