---
title: "Membongkar source code PrayTime"
tags:
 Java
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
---  
<figure style="width: 200px" class="align-center">
<img src="/images/analog.JPG">
<figcaption>waktu sholat</figcaption>
</figure> 
Karena cukup penasaran dengan algoritma perhitungan waktu sholat dan kebutuhan jugak sih karena terkadang pekerjaan yang saya jalani berada pada posisi tidak dapat mendengar bunyi 
suara adzan bahkan posisi di tempat penduduknya mayoritas non muslim,terbesit keinginan untuk mencari algoritma dari perhitungan sholat dan menemukan beberapa referensi di website [praytime.org](http://praytimes.org/) disana di terangkan bagaimana cara menghitung waktu sholat secara detail yang bersumber dari hadist dan al-quran tidak hanya alur perhitungan manualnya disana jugak sudah ada contoh [source code](http://praytimes.org/wiki/Code) yang di tulis dalam bahasa `javascript` dan di digubah dalam beberapa bahasa pemrogaman terutama `java` setelah saya download langsung saya coba compile di terminal
{: style="text-align: justify;"}


<figure style="width: 500px" class="align-center">
<img src="/images/erorDeprecate.gif">
<figcaption>deprecated API</figcaption>
</figure> 

langsung menemukan Deprecated API (Application Progamming Interface) pada class DATE 
<figure style="width: 600px" class="align-center">
<img src="/images/ana1.png">
<figcaption></figcaption>
</figure>

<figure style="width: 700px" class="align-center">
<img src="/images/ana2.png">
<figcaption></figcaption>
</figure>
 
kalau diliat dari dokumentasi [javadoc](https://docs.oracle.com/javase/7/docs/api/java/util/Date.html) sejak jdk 1.1 tela digantikan oleh Calendar.set di laptop saya telah menggunakan jdk 1.8 setelah menganalisa dengan seksama ternya yang menggunakan class Date adalah method kedua alias opsional jadi saya `comments` saja untuk sementara karena beberapa kali saya coba untuk merubah ke calendar.set belum bisa teratasi heuheuheu
{: style="text-align: justify;"}
<figure style="width: 700px" class="align-center">
<img src="/images/coment.png">
<figcaption></figcaption>
</figure>


<figure style="width: 500px" class="align-center">
<img src="/images/erorpackage.gif">
<figcaption></figcaption>
</figure>

okey compiler sudah tidak ngriwik lagi tapi setelah di execute bycode-nya muncul pesan `Error:could not find or load main class PrayTime`
kenapa gak bisa load main class? ternyata saya menemukan syntax new package pemanggilan package newpackage di line 25 yang gak jelas maksutnya masih misteri
{: style="text-align: justify;"}

<figure style="width: 700px" class="align-center">
<img src="/images/failpackage.png">
<figcaption></figcaption>
</figure>

setelah saya hapus syntax di line 25 akhirnya bisa melihat output dari source code PrayTime

<figure style="width: 500px" class="align-center">
<img src="/images/suksescom.gif">
<figcaption></figcaption>
</figure>

tapi justru setelah code ini berhasil mengeluarkan output beberapa pertanyaan langsung menghujam di pikiran saya,lih alih akan membuat tulisan kali selesai malah bisa jadi tulisan kali ini akan bersambung . okey output yang dihasilkan diambil dari tanggal yang tertara di system computer setelah saya teliti lagi ada selisih sekitar 3menit sama waktu sholat di masjid surabaya beberapa hari mencari informasi ternyata banyak masjid di surabaya dan jawatimur masih berpedoman ke radio yang disiarkan di masjid rahmat salah satu masjid bersejarah di surabaya dan akhirnya saya jugak dapat informasi kalau masjid rahmat surabaya berpedoman pada tim hisab dan ruhiyat kementrian agama, [jadwal sholat](http://simbi.kemenag.go.id/sihat/waktu-sholat) mungkin kedepan saya akan lebih mencari tahu lagi kenapa masih bisa selisih lebih dari 3 menit dari jadwal yang ditentukan oleh kementrian agama
{: style="text-align: justify;"}