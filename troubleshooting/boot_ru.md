---
title: Проблемы с загрузкой
parent_category: Исправление проблем
path: /troubleshooting-boot_ru
lang: ru
parent_category_path: /troubleshooting_ru
order: 1
---

## Проблемы с загрузкой
Если коротко, вам нужно подключить свой диск к ригу, и всё. Но иногда это просто не работает.

Во-первых, вы должны убедиться, что вы не пытаетесь загрузиться из раздела UEFI. Некоторые BIOS дают вам такую ​​возможность, но вам не следует этого делать.


<img src="http://forum.hiveos.farm/uploads/editor/b0/5rpntezwp5sf.jpg">

В настройках USB должен быть включен режим Legacy. Подобно тому, как мышь и клавиатура работают во время загрузки, иначе USB-накопитель не будет обнаружен. IOMMU может быть проблемой на некоторых материнских платах. Иногда это называется CSM (модуль поддержки совместимости).


<img src="http://forum.hiveos.farm/uploads/editor/sa/nkq21zwkxe4t.jpg">

Что ж, диск обнаружен, он запускает, но потом возникает следующая ошибка:

<img src="http://forum.hiveos.farm/uploads/editor/bn/ebj16b6y9jub.jpg">

Это говорит о том, что есть проблема с записанным изображением. Обычно это решается попыткой записать изображение при помощи альтернативного программного обеспечения:

- [Etcher](https://www.balena.io/etcher/)
- [Rufus](https://rufus.akeo.ie/)
- [Chrysocome](http://www.chrysocome.net/dd)
- [SourceForge](https://sourceforge.net/projects/win32diskimager/)
- [HDDGURU](http://hddguru.com/software/HDD-Raw-Copy-Tool/)