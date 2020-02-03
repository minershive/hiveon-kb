---
title: RX Буст - AmdMemTweak
category: Гайды
---

## RX Буст - AmdMemTweak
### AMDMemTweak – чтение/запись таймингов памяти
Благодаря усилиям программиста под псевдонимом Eliovp, утилита AMDMemoryTweak доступна на [Bitcointalk](https://bitcointalk.org/index.php?topic=5123724.0) и [GitHub](https://github.com/Eliovp/amdmemorytweak), что позволяет вам работать с таймингами видеопамяти GDDR5 и HBM2 видеокарт на платформе AMD на лету.

AmdMemoryTweak позволяет достичь максимальной скорости при майнинге на алгоритмах с интенсивным использованием памяти на видеокартах AMD. Многие называют эту утилиту “таблетка для красных” по аналогии с программой ETHEnlargment Pill, которая значительно повышает производительность видеокарт Nvidia с памятью GDDR5X. На самом деле это, безусловно, верно, но для достижения эффекта уровень подготовки пользователя должен быть намного выше.
AmdMemoryTweak особенно полезен для видеокарт серии Vega с памятью HBM2.

### Общее использование
В amdmemorytweak вы можете использовать следующие команды:

`--gpu | --i` [разделенных запятыми числа GPU] - выбор задействованных видеокарт

`--current` - показывает текущие тайминги

`--help` - отображает список доступных команд

Чтение и применение параметров должно быть выполнено после разгона - настройки частоты памяти.

### GDDR5
Давайте посмотрим на настройки GDDR5, которые мы можем получить.
Получение текущих значений:

`amdmemtweak --current`

Результат от карты с кастомным BIOS RX570 с памятью Elpida:
<pre><code>
GPU 0:  Ellesmere [Radeon RX 470/480/570/570X/580/580X/590]     pci:0000:01:00.0
   Elpida GDDR5
PMG:      CKSRE: 2        CKSRX: 2        CKE_PULSE: 10   CKE: 10         SEQ_IDLE: 7
CAS:      CL: 20          W2R: 15         R2R: 5          CCDL: 2         R2W: 26         NOPR: 0         NOPW: 0
RAS:      RC: 60          RRD: 5          RCDRA: 22       RCDR: 24        RCDWA: 13       RCDW: 12
MISC:     RFC: 97         TRP: 22         RP_RDA: 24      RP_WRA: 44
MISC2:    WDATATR: 0      T32AW: 0        CRCWL: 22       CRCRL: 3        FAW: 0          PA2WDATA: 0     PA2RDATA  : 0
M3(MR4):          RAS: 38
DRAM1:    RASMACTWR: 6    RASMACTRD: 5    ACTWR: 2        ACTRD: 3
DRAM2:    RAS2RAS: 13     RP: 5   WRPLUSRP: 7     BUS_TURN: 3
Refresh:          tREF: 30
</code></pre>
Как видите, здесь слишком много параметров, и для неподготовленного пользователя это марсианский язык.
Доступные опции для памяти GDDR5:
<pre><code>
 --CKSRE|--cksre [value]
 --CKSRX|--cksrx [value]
 --CKE_PULSE|--cke_pulse [value]
 --CKE|--cke [value]
 --SEQ_IDLE|--seq_idle [value]
 --CL|--cl [value]
 --W2R|--w2r [value]
 --R2R|--r2r [value]
 --CCDL|--ccdl [value]
 --R2W|--r2w [value]
 --NOPR|--nopr [value]
 --NOPW|--nopw [value]
 --RCDW|--rcdw [value]
 --RCDWA|--rcdwa [value]
 --RCDR|--rcdr [value]
 --RCDRA|--rcdra [value]
 --RRD|--rrd [value]
 --RC|--rc [value]
 --RFC|--rfc [value]
 --TRP|--trp [value]
 --RP_WRA|--rp_wra [value]
 --RP_RDA|--rp_rda [value]
 --WDATATR|--wdatatr [value]
 --T32AW|--t32aw [value]
 --CRCWL|--crcwl [value]
 --CRCRL|--crcrl [value]
 --FAW|--faw [value]
 --PA2WDATA|--pa2wdata [value]
 --PA2RDATA|--pa2rdata [value]
 --RAS|--ras [value]
 --ACTRD|--actrd [value]
 --ACTWR|--actwr [value]
 --RASMACTRD|--rasmactrd [value]
 --RASMACWTR|--rasmacwtr [value]
 --RAS2RAS|--ras2ras [value]
 --RP|--rp [value]
 --WRPLUSRP|--wrplusrp [value]
 --BUS_TURN|--bus_turn [value]
 --REF|--ref [value]
</code></pre>
Для пользователей, которые используют карты с пользовательскими настройками таймингов в VBIOS, как правило, использование утилиты не влияет на рост хэшрейта.
Однако, используя параметр ''--REF', вы можете получить выигрыш до 5% на алгоритмах, зависящих от производительности памяти. Хорошее значение для начала - 30. Эта опция получила название "rxboost".

Командная строка будет выглядеть так:

`amdmemtweak --REF 30`

Также интересными могут быть параметры `--RC` и `--RFC`.

### HBM2
HBM2 память используется в семействе карт Vega (56/64 и новейших 7нм, известных как Radeon VII). Для этих карт доступны опции:
<pre><code>
--CL|--cl [value]
 --RAS|--ras [value]
 --RCDRD|--rcdrd [value]
 --RCDWR|--rcdwr [value]
 --RC|--rc [value]
 --RP|--rp [value]
 --RRDS|--rrds [value]
 --RRDL|--rrdl [value]
 --RTP|--rtp [value]
 --FAW|--faw [value]
 --CWL|--cwl [value]
 --WTRS|--wtrs [value]
 --WTRL|--wtrl [value]
 --WR|--wr [value]
 --RREFD|--rrefd [value]
 --RDRDDD|--rdrddd [value]
 --RDRDSD|--rdrdsd [value]
 --RDRDSC|--rdrdsc [value]
 --RDRDSCL|--rdrdscl [value]
 --WRWRDD|--wrwrdd [value]
 --WRWRSD|--wrwrsd [value]
 --WRWRSC|--wrwrsc [value]
 --WRWRSCL|--wrwrscl [value]
 --WRRD|--wrrd [value]
 --RDWR|--rdwr [value]
 --REF|--ref [value]
 --MRD|--mrd [value]
 --MOD|--mod [value]
 --XS|--xs [value]
 --XSMRS|--xsmrs [value]
 --PD|--pd [value]
 --CKSRE|--cksre [value]
 --CKSRX|--cksrx [value]
 --RFCPB|--rfcpb [value]
 --STAG|--stag [value]
 --XP|--xp [value]
 --CPDED|--cpded [value]
 --CKE|--cke [value]
 --RDDATA|--rddata [value]
 --WRLAT|--wrlat [value]
 --RDLAT|--rdlat [value]
 --WRDATA|--wrdata [value]
 --CKESTAG|--ckestag [value]
 --RFC|--rfc [value]
</code></pre>
Выбор хороших параметров для этого типа памяти - более тонкий процесс, но и эффективность хэшрейта является более значительным по сравнению с GDDR5.
Пример использования для Vega 56 с кастомным BIOS:

`amdmemtweak --CL 16 --RAS 30 --RCDRD 12 --RCDWR 5 --RC 44 --RP 10 --RRDS 3 --RRDL 5 --RTP 5 --FAW 20 --CWL 7 --WTRS 4 --WTRL 9 --WR 16 --WRRD 1 --RDWR 19 --REF 17550 --MRD 8 --MOD 15 --PD 8 --CKSRE 10 --CKSRX 10 --RFC 300`

С данными установками данная карта показала результат 50MH/s при майнинге ethash (прирост составил почти 8 МХ).

### Hive RXboost
Утилита amdmemtweak включена в дистрибутив Hive OS. С обновлением Hive до v0.6-45 новая опция появляется в настройках AMD OC. Этот параметр позволяет применить так называемый rxboost, твик ставший известным после появления 14 версии майнера Claymore’s Dual ETH Miner к картам серии RX 4xx / 5xx. Другими словами, это то же самое, что выполнение `amdmemtweak` с параметром `--REF`.

<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/dd4564ddc1ebfe5aee3530837c35220d4a099db8.png">

Если поле пустое (значение по умолчанию), то опция не применяется. Чтобы применить значение для всех карт, введите одно значение. Если нужно применить для разных карт и указать индивидуальные значения, то введите значения, разделенные пробелами.
Вот короткое видео о том, как использовать эту функцию:
- <a href="https://www.youtube.com/watch?v=0zJsU07Lgvc">RX Буст в Hive OS: максимум с ваших RX карт</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=0zJsU07Lgvc
" target="_blank"><img src="http://img.youtube.com/vi/0zJsU07Lgvc/0.jpg"
alt="RX Буст в Hive OS: максимум с ваших RX карт"></a>
