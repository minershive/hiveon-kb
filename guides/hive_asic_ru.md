---
title: Hive OS для ASIC
parent_category: Гайды
path: /guides-hive_asic_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

### Доступное программное обеспечение для ASICов от Hive
**1. [Hive OS Client](https://github.com/minershive/hiveos-asic/blob/master/README.md)**

Это приложение, работающее на заводской или кастомной прошивке ASICа.

- Позволяет видеть майнер в Hive, контролировать кошельки и пулы, перезапускать и перезагружать майнер.
- Поддерживает множество моделей ASICов: Antminer, Innosilicon, Zig и даже некоторые FPGA майнеры.

Поддерживаемые ASICи:
- **Antminer:**
	- A3
	- B3
	- D3, D3 (Blissz)
	- DR3
	- E3
	- L3+, L3++
	- S7
	- S9, S9i, S9j, S9k, S9SE, S9-Hydro, S9 (VNISH), S9 (MSKMINER)
	- S10 (S9 Dual MSKMINER)
	- S11
	- S15
	- S17, S17+, S17E, S17 Pro
	- T9, T9+
	- T15
	- T17, T17+, T17E
	- X3
	- Z9, Z9-Mini
	- Z11
- **Innosilicon:**
	- A5/A8 (need test)
	- A9 ZMaster
	- D9 DecredMaster
	- S11 SiaMaster
	- T3 BTCMiner
	- T3H+, T3+, T2Th+, T2Thf+, T2Thl+, T2Th, T2Tz-30T, T2Thm, T2Thf, T2T+ (32T), T2Ts-26T, T2Ti-25T, T2T-24T
- **Todek:**
	- Toddminer C1, C1 PRO
- **HashAltCoin:**
	- Blackminer F1, F1+, F1-MINI
	- Blackminer F1-Ultra, F1-MINI+
- **Zig:**
	- Z1, Z1+

Самый актуальный список можно найти <a href="https://github.com/minershive/hiveos-asic">здесь</a>.

**Инструкцию по установке Hive OS Client можно найти [здесь](https://hiveos.farm/guides-add-asic-to-hiveos_ru).**


**2. [Hiveon ASIC Firmware](https://hiveos.farm/asic/)**

Это кастомная прошивка, заменяющая заводскую. Поддерживает только некоторые модели: Antminer S17, S17+, S17E, S17 Pro, S9, S9i, S9j, S10, L3+, L3++, T9+, T17, T17+, T17E.

- **S17:** до 72 Th/s с воздушным охлаждением
- **S17 Pro:** до 80.1 Th/s на стандартном блоке питания, до 85 Th/s с жидким охлаждением
- **S9, S9i, S9j:** до 16.8 Th/s на стандартном блоке питания, до 19.1 Th/s на кастомном
- **S10:** до 21.5 Th/s на стандартном блоке питания, до 23.5 Th/s на кастомном
- **T9+:** до 13.6 Th/s на стандартном блоке питания

>Прошивки Hiveon для других моделей ASIC уже в разработке, так что следите за обновлениями!

Что дает прошивка:
* Ускорение изношенных ASIC чипов;
* Подбор поплатно напряжения и частот автоматически и вручную;
* Тонкий тюнинг частот индивидуально почипно;
* При пропадании интернета перестает потреблять электроэнергию чипами;
* Антивирусная защита;
* Восстановление устройств,  которые ранее подверглись заражению вирусами;
* Мигание светодиодами на ASICе в случае поломки вентилятора или чипов;
* Встроенный Ваттметр;
* Вотчдоги по температуре, хешрейту;
* При использовании прошивки, Hive OS - бесплатно.

**Инструкции по установке прошивок можно найти [здесь](https://hiveos.farm/hiveon-asic-firmware_ru).**

### Hive OS Client и прошивка Hiveon ASIC: сравнение

>Hive OS Client и прошивка Hiveon ASIC **не являются одним и тем же продуктом**.

|Модель / Характеристика |	Видеть майнер в Hive OS |Контролировать кошельки и пулы |	Перезапускать майнер	| Перезагружать майнер	|Антивирус (только прошивка Hiveon) |	Разгон (только прошивка Hiveon) |	Даунвольтинг (только прошивка Hiveon) | Регулировка напряжения (только прошивка Hiveon) |	Авто-тюнинг (только прошивка Hiveon)|
|----|----|-----|-----|-----|----|----|----|----|----|
|**Antminer**||||||||||
|A3|*|*|*|*|
|B3|*|*|*|*|
|D3, D3 (Blissz)|*|*|*|*|
|DR3|*|*|*|*|
|E3|*|*|*|*|
|L3+, L3++|*|*|*|*|*|*|*|*|*|*|
|S7|*|*|*|*|
|S9, S9i, S9j|*|*|*|*|*|*|*|*|*|*|
|S9k, S9SE, S9-Hydro|*|*|*|*|скоро|скоро|скоро|скоро|скоро|
|S10 (MSKMINER)|*|*|*|*|*|*|*|*|*|*|
|S11|*|*|*|*|
|S15|*|*|*|*|
|S17, S17+, S17E, S17 Pro|*|*|*|*|*|*|*|*|*|*|
|T9|*|*|*|*|
|T9+|*|*|*|*|*|*|*|*|*|*|
|T15|*|*|*|*|
|T17, T17+, T17E|*|*|*|*|*|*|*|*|*|*|
|X3|*|*|*|*|
|Z9, Z9-Mini|*|*|*|*|
|Z11|*|*|*|*|
|**Innosilicon**|
|A5/A8 (необходимо тестирование)|*|*|*|*|
|A9 ZMaster|*|*|*|*|
|D9 DecredMaster|*|*|*|*|
|S11 SiaMaster|*|*|*|*|
|T3 BTCMiner|*|*|*|*|
|T3H+, T3+, T2Th+, T2Thf+, T2Thl+, T2Th, T2Tz-30T, T2Thm, T2Thf, T2T+ (32T), T2Ts-26T, T2Ti-25T, T2T-24T|*|*|*|*|
|**Todek**|
|Toddminer C1, C1 PRO|*|*|*|*|
|**HashAltCoin**|
|Blackminer F1, F1+, F1-MINI|*|*|*|*|
|Blackminer F1-Ultra, F1-MINI+|*|*|*|*|
|**Zig**|
|Z1, Z1+|*|*|*|*|

Всю информацию и инструкции можно найти в нашей [Базе Знаний](https://hiveos.farm/knowledge-base_ru).

### Видео
- <a href="https://www.youtube.com/watch?v=KY2ld3qUQRg">Hive OS на ASIC. Установка на z9mini и настройка майнинга ZEC на flypool</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=KY2ld3qUQRg
" target="_blank"><img src="http://img.youtube.com/vi/KY2ld3qUQRg/0.jpg"
alt="Hive OS на ASIC. Установка на z9mini и настройка майнинга ZEC на flypool"></a>

- <a href="https://www.youtube.com/watch?v=rVSauk7Jzr4">[mining] Hive OS + ASIC antminer D3 установка и настройка</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=rVSauk7Jzr4
" target="_blank"><img src="http://img.youtube.com/vi/rVSauk7Jzr4/0.jpg"
alt="[mining] Hive OS + ASIC Antminer D3 установка и настройка"></a>
