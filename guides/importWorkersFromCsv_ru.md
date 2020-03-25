---
title: Импорт воркеров из CSV
parent_category: Гайды
path: /guides_import-workers-from-csv_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

## Импорт воркеров из CSV
В Hive OS появилась новая функция — импорт CSV файлов. С её помощью, вы можете создавать или обновлять данные любого количества воркеров легко и просто — всё это может быть сделано в одном и том же файле. Просто следуйте данной инструкции:

1. Войдите в свой аккаунт Hive OS и перейдите на вкладку **Workers** ("Воркеры").

2. Вы увидите список ваших воркеров и две кнопки с правой стороны: **Export CSV** ("Экспорт CSV") и **Import CSV** ("Импорт CSV"). Это первые две кнопки, расположенные справа от поля **Name** ("Имя").

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers1.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers1.png"
  />

3. Нажмите на кнопку **Export CSV**, чтобы скачать файл (файл будет включать в себя все воркеры, доступные на вкладке Workers). Когда загрузка завершится, откройте его. Вы увидите нечто подобное:

<img src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers3.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers3.png"
  />

4. Теперь вы можете отредактировать файл. Менять можно следующие поля: имя воркера, описание, потребляемую мощность и КПД блока питания:

<img src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers4.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers4.png"
  />

5. Сохраните изменения в файле.

6. Вернитесь в свой аккаунт Hive OS и нажмите на кнопку **Import CSV**:

<img src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers2.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers2.png"
  />

7. Выберите файл, который вы только что отредактировали и сохранили. Теперь проверьте вкладку **Workers** — данные (как в этом списке, так и в настройках каждого воркера) уже обновлены:

<img src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers5.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers5.png"
  />