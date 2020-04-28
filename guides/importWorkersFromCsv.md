---
title: Import workers from CSV
parent_category: Guides
path: /guides_import-workers-from-csv
lang: en
parent_category_path: /guides
order: 1
---

Welcome the new Hive OS feature — import of CSV files. With this function, you can create or update any number of workers quickly and easily, as everything can be done in one file. This is how it works:

1. Log in to your Hive OS account and go to the **Workers** tab.

2. You will see the list of your workers and two buttons on the right side: **Export CSV** and **Import CSV**. They are the first two buttons in that line next to the **Name** field.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers1.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers1.png"
  />

3. Click the **Export CSV** button to download the file (the file will include all the workers available on the Workers tab). After the download is complete, open the file. You will see something like this:

<img src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers3.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers3.png"
  />

4. Then, you can edit the file. The following fields can be changed: the worker’s name, description, hardware power consumption and the power supply unit efficiency:

<img src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers4.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers4.png"
  />

| Worker fields  | Values              | What to write                                            |
|----------------|---------------------|----------------------------------------------------------|
| ID             | Only numbers        | ID of a worker (if, for example, you export 4 workers and delete IDs of 2 of them, 2 new workers with new IDs will be created - there will be 6 of them in total) |
| Name           | Letters and numbers | Name of a worker                                         |
| Description    | Letters and numbers | Description of a worker                                  |
| Power draw     | Only numbers        | Hardware power consumption                               |
| PSU efficiency | Only numbers        | Power supply unit efficiency                             |

5. Save the changes.

6. Go back to your Hive OS account and click the **Import CSV** button:

<img src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers2.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers2.png"
  />

7. Then choose the file that you have just edited and saved. Now check the **Workers** tab — the data (both in this list and in the **Settings** of each particular worker) is updated:

<img src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers5.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\importCSV\workers5.png"
  />
