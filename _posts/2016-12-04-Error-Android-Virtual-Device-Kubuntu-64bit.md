---
title: "Error Android Virtual Device kubuntu 64 bit"
tags:
 Linux
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
---
<figure style="width: 700px" class="align-center">
<img src="/images/kinfo.png">
<figcaption>kinfo</figcaption>
</figure>
Tibalah saatnya untuk upgrade Ram ddr3l thinkpad e145 dari 4GB ke 8GB di iringi penuh drama semenjak pertama kali upgrade ke 4GB dan 8GB adalah upgrade terakhir karena thinkpad ini hanya bisa up to 8GB menurut website resminya tapi menurut kabar beredar dari mas mas di VGEN service center ini thinkpad bisa sampek 16GB tapi rasanya saya tidak sebegitu tertarik untuk coba coba pasalnya upgrade ke 8GB hanya untuk memenuhi rekomendasi system untuk [android studio di operating system linux](https://developer.android.com/studio/index.html)

<figure style="width: 700px" class="align-center">
<img src="/images/rekomAndro.png">
<figcaption>system requirement</figcaption>
</figure>

setelah upgrade dan langsung saya coba untuk menjalankan android studio dan run code untuk dijalankan di android virtual device untuk mengetahui bagaimana performa thinkpad saat setelah upgrade ram 8GB akhirnya ketemu error `EmptyThrowable: Failed to create the SD card`.

<figure style="width: 800px" class="align-center">
<img src="/images/empty.png">
<figcaption></figcaption>
</figure>

saya baru inget kalau kubuntu ini baru saya install ulang gara gara percobaan install guitarix beta akhirnya banyak error dedepency yang mengakibatkan harus install ulang (ini cara terjitu hemat waktu agar gak ribet aja heuheuheu) dan jawaban dari error di atas adalah [di postingan saya bulan bulan lalu](http://www.glamvian.com/erorr-android-studio/)
okey problem `EmptyThrowable: Failed to create the SD card` terselesaikan.

<figure style="width: 500px" class="align-center">
<img src="/images/erorRunEmulator.jpg">
<figcaption></figcaption>
</figure>

saat run emulator muncul error baru libGL error setelah baca baca di bug reportnya google jawabanya adalah libstdc++6 yang barusan di install belom terload di sdk kita

```ruby
 ~:$ cd ~/Android/Sdk/tools/lib64/libstdc++
 ~:$ mv libstdc++.so.6 libstdc++.so.6.bak
 ~:$ ln -s /usr/lib64/libstdc++.so.6 ~/Android/Sdk/tools/lib64/libstdc++
```

<figure style="width: 200px" class="align-center">
<img src="/images/solved.jpg">
<figcaption></figcaption>
</figure>

akhirnya emulator bisa mengudara dan setelah compile dan run code app terinstall sempurna di emulator dan berjalan sangat smooth pengaruh ram 8GB alhamdulilah jadi tambah semangat bekarya ya

<figure style="width: 500px" class="align-center">
<img src="/images/emudone.gif">
<figcaption></figcaption>
</figure>