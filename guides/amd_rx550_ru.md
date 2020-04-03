---
title: Настройка RX550
parent_category: Гайды
path: /guides-amd_rx550_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

## Настройка RX550

Планируете заставить RX 550 работать в Hive OS? Вот инструкция. Вам "понадобится" ядро 4.13 и OpenCL из драйвера 16.60. Если вы можете, сделайте следующее: `amdgpu-pro-uninstall`.

Скачайте ядро 4.13:
<pre><code>
wget http://download.hiveos.farm/kernels/linux-headers-4.13.12-mytest_1_amd64.deb
wget http://download.hiveos.farm/kernels/linux-firmware-image-4.13.12-mytest_1_amd64.deb
wget http://download.hiveos.farm/kernels/linux-image-4.13.12-mytest_1_amd64.deb
</code></pre>
И установите его:
<pre><code>
dpkg -i linux-headers-4.13.12-mytest_1_amd64.deb
dpkg -i linux-firmware-image-4.13.12-mytest_1_amd64.deb
dpkg -i linux-image-4.13.12-mytest_1_amd64.deb
</code></pre>

Выберите загрузку ядра до последней версии:
`grub-set-default "1>0"; update-grub`

Перезагрузите и проверьте, загрузили ли вы правильное ядро:
<pre><code>
uname -a
Linux rig2 4.13.12-mytest #1 SMP Thu Nov 9 15:31:09 EET 2017 x86_64
 x86_64 x86_64 GNU/Linux
</code></pre>
Перейдите в папку с драйверами в Hive и установите только OpenCL из версии 16.60:
<pre><code>
cd /hive-drivers-pack
tar xvf amdgpu-pro-16.60-379184.tar.xz
cd amdgpu-pro-16.60-379184
./amdgpu-pro-install --compute
</code></pre>
И, наконец, перезагрузите.

Для sgminer, возьмите приложенный kernel.tar.gz, и замените ядра в папке **/hive/sgminer_gm** на риге. У RX 550 есть только 512 шейдерных ядер, так что не имеет смысла настраивать 'rawintensity' более 512.

Рекомендуемые настройки:

“rawintensity”: 420

“gpu-threads”: “2”

Вы также можете попробовать [этот образ](http://193.111.83.51/test/hive-0.5-20-rx550_sgminer.zip). Он работает только для RX 550 и основан на последней Hive OS 0.5-20 с ядром 4.13.
