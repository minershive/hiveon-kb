---
title: Hive Shell
category: Гайды
---

## Hive Shell
<img src="https://forum.hiveos.farm/uploads/default/original/2X/8/8580c113d2e085d26be948283c7922532a00d90f.png">

### О Hive Shell
Почти год назад в Hive OS появилась функция удаленного доступа к воркерам посредством сервиса [Teleconsole](https://forum.hiveos.farm/t/teleconsole/3968). Данный сервис сразу стал очень популярен среди наших пользователей для решения различных задач по удаленному обслуживанию.
К большому сожалению, последнее время пользоваться этим сервисом стало очень сложно ввиду нестабильности в работе сервиса, поэтому команда Hive приступила к поиску альтернативного решения, которое теперь мы с большим удовольствием представляем вам.
Итак, встречайте - ***Hive Shell.***
Hive Shell предоставляет удаленный доступ к вашим воркерам, используя сетевую инфраструктуру Hive OS, а также обладает своими уникальными особенностями, такими как доступ через SSH клиент и совместное использование консоли.

Давайте познакомимся с Hive Shell поближе.

### Как этим пользоваться
В веб интерфейсе в меню “Удаленный доступ” появилось два пункта “Hive Shell Start” и “Hive Shell Stop”:

<img src="https://forum.hiveos.farm/uploads/default/original/2X/2/2718fd40aee03d149d85bb58d3bb32d7e71b79d4.png">

После запуска сервиса через пункт меню “Hive Shell Start” вы увидите результат выполнения команды: <img src="https://forum.hiveos.farm/uploads/default/original/2X/f/fa02eab197103fe96142da745133262e42ea8844.png">

Результат данной команды представляет собой кликабельную ссылку, нажав на которую в вкладке браузера вы откроете окно терминала воркера.
Также можно открыть результат выполнения команды, чтобы воспользоваться дополнительными возможностями команды, такими как передача веб-ссылки техническому специалисту или подключение, используя SSH клиент (будет рассмотрено отдельно).
<img src="https://forum.hiveos.farm/uploads/default/original/2X/5/5fa0229f1f913ce1f8267534c34a99922af1a5ee.png">

***Внимание! Передавайте ссылку для доступа к Вашему воркеру только лицу, которому Вы доверяете.***

Так это работает:

<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/dc515fb26c34a078bd34436a3415bdf6fe646695.gif">

### Запуск из консоли
Hive Shell может быть запущен как из веб-интерфейса, так и из консоли. Из консоли Hive Shell запускается командой `hssh` (допустимые параметры start | stop | restart )

Запуск сервиса: `hssh start`
Остановка сервиса: `hssh stop`
Перезапуск сервиса: `hssh restart`

### Совместное использование консоли
Очень важной особенностью Hive Shell является возможность совместного использования консоли. Вы можете наблюдать (или даже принимать участие) за теми действиями которые осуществляются человеком, с которым вы поделились доступом к воркеру посредством Hive Shell.
Использование данного функциона предельно простое - просто откройте ту же ссылку, которой поделились с другим человеком.
Так это выглядит (слева - Hive Shell запущен в браузере FireFox, справа - через клиент PuTTY):
<img src="https://forum.hiveos.farm/uploads/default/optimized/2X/f/f57bd44c479d05d15743b8a57cd92c30a8b83f69_2_690x313.gif">
Все действия в одной консоли отображаются в другой.

### Использование SSH клиента
С помощью Hive Shell вы можете можете подсоединиться к вашему воркеру, используя SSH клиент, такой как PuTTY.

***Генерация приватного ключа***
Для этого вам необходимо провести разовую процедуру - сгенерировать ваши приватные ключи. Для этого нужно воспользоваться программой, входящей в состав пакета PuTTY - PuTTYgen (PuTTY Key Generator).

<img src="https://forum.hiveos.farm/uploads/default/original/2X/c/cd4859a8da5bbf8bf77723734fc1e203f6bbc14e.png">

Запустите PuTTYgen и нажмите кнопку “Generate”, хаотически водите курсор мыши по полю приложения, пока прогресс-бар не дойдет до конца.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/4/488a4e137f3448711ba495bfcaef8ef8fef01374.gif">

После чего нажмите кнопку “Save private key”, предупреждение о сохранении без пароля можно проигнорировать, нажав “Да” и сохраните ключ на Вашем компьютере.

### Настройка SSH-клиента
Далее Вам необходимо настроить ваш SSH-клиент, используя сгенерированный приватный ключ.
Запускаем PuTTY, раскрываем слева секцию Connection и в ней подсекцию SSH, и становимся на Auth, справа будет меню выбора файла, где нужно выбрать сохраненный на предыдущем этапе приватный ключ.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/7/79ab92e1bf5e4bec5ea1a7b2edfec51f5ff560c5.png">

После этого переходим в секцию Session и сохраняем наш профиль. Для этого задаем Host Name - `shell.hiveos.farm` и имя профиля, например - Hive Shell и нажимаем кнопку “Save” для сохранения.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/c/c2d497fea2e00d1d5ffd564d7b88c265d15e553e.png">

Если коротко, это выглядит так:

<img src="https://i.imgur.com/ws4vmZu.gif">

### Запуск PuTTY
Далее процедура предельно проста:
- запускаем Hive Shell и дожидаемся успешного старта <img src="https://forum.hiveos.farm/uploads/default/original/2X/f/fa02eab197103fe96142da745133262e42ea8844.png">

- открываем результат выполнения команды
<img src="https://forum.hiveos.farm/uploads/default/original/2X/3/315f51cc76b82b56a142c1cb79189e551d2beb4d.png">

- копируем имя сессии Hive Shell
<img src="https://forum.hiveos.farm/uploads/default/original/2X/9/9fadda648e24a57709fc8aa51d35504385f8caa0.png">

- запускаем PuTTY, открываем ранее сохраненный профиль Hive Shell, и по правой кнопке мышки будет вставлено сохраненное имя сессии в качестве имени пользователя
<img src="https://forum.hiveos.farm/uploads/default/original/2X/4/40919285c83918465ff126f5a87c0641043c4788.png">
- жмем Enter
- все мы на месте! Действительно просто, не правда ли?
<img src="https://forum.hiveos.farm/uploads/default/original/2X/0/05a5d4e929357b43263cb5db2f57a0df83ae7a11.png">

### Видео

- <a href="https://youtu.be/GgcFNKQvwDA">Новая телеконсоль от создателей Hive OS</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=GgcFNKQvwDA
" target="_blank"><img src="http://img.youtube.com/vi/GgcFNKQvwDA/0.jpg"
alt="Новая телеконсоль от создателей Hive OS"></a>
