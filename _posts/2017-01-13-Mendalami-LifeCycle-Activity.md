---
title: "Mendalami Activity Lifecyle"
tags:
 Android
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
---

Mengulang membaca buku materi tentang Lifecyle Activity semakin diulang semaki seru tentu saja merawat ingatan biar fondasi android tak terlupakan kali ini dengan App stopwatch simpel hanya dengan single  class Activity dan single layout yaitu `stopWatchActivity` dan `activity_stop_watch.xml`.
{: style="text-align: justify;"}
{% include toc title="Contents" icon="file-text" %}

<figure style="width:400px" class="align-center">
<img src="/images/stopwatch.gif">
<figcaption>penampakan app</figcaption>
</figure>

Sama seperti stopwatch pada umumnya fungsinya untuk menghitung waktu perdetik ada 3 button disana start, stop, dan reset dengan uml seperti dibawah ini.

<figure style="width:400px" class="align-center">
<img src="/images/StopWatchActiviy.png">
<figcaption>uml class StopWatchActivity</figcaption>
</figure>

issue pertama muncul ketika app berjalan setelah kita touch start button trus device kita ganti rotasi jadi horizontal ditengah tengah app berjalan seketika aplikasi langsung muncul seperti awal lagi alias di destroy.
<figure style="width:400px" class="align-center">
<img src="/images/rotationStp.gif">
<figcaption>rotation</figcaption>
</figure>

apa yang terjadi adalah rotasi layar android dan ukuran layar berubah, dan itu destroy Activity, termasuk semua variabel yang digunakan method runTimer(). setelah itu method onCreate() berjalan lagi dan method runTimer() dipanggil karena Activity di re-create, variabel mSecond dan mRunning bernilai default.

## Launch, Running , Destroy
Main state dari activity adalah ketika dia running atau aktif. activity berjalan di foreground dari screen dan user berinteraksi dengannya, activity running setelah ter launch dan berakhir setelah di destroy. ketika activity berubah dari launched dan akan di destroy dia mentrigger method kunci Lifecyle activity yaitu onCreate() dan onDestroy(). itu adalah method Lifecyle yang kita inherit di Activity dan bisa kita override.
<figure style="width:200px" class="align-center">
<img src="/images/activitylaunchstp.png">
<figcaption>alur activity born to death</figcaption>
</figure>


Method onCreate() akan dipanggil setelah Activity di launch. dan method onDestroy() adalah method terakhir yang di panggil sebelum activity di destroy
<figure style="width:300px" class="align-center">
<img src="/images/inheritstp.png">
<figcaption>turunan class activity</figcaption>
</figure>

karena issue rotasi terjadi karena destroy maka sebelum destroy terjadi saya mau simpan state yang sedang berjalan dengan method onSaveInstanceState() method ini bisa dipanggil sebelum method onDestroy() berjalan. method onSaveInstanceState() mempunyai satu parameter yaitu Bundle dan Bundle
membolehkan kita untuk mengumpulkan data bersama walaupun beda type data kedalam single object.

## onSaveInstanceState
method onCreate akan melewati Bundle sebagai parameter. ini berarti jika saya menambah value mRunning dan mSecond ke Bundle, method onCreate() akan mengambil mereka ketika Activity dimuat ulang. aturan memakai method Bundle :

`bundle.put*("name", value)`

dimana `bundle` adalan nama Bundle, `*` untuk type value yang ingin disimpan, seperti ini jadinya

<figure style="width:400px" class="align-center">
<img src="/images/bundleput.png">
<figcaption>bundle.put</figcaption>
</figure>

akhirnya saya simpan variabel values di Bundle dan dapat menggunakan mereka berdua method di onCreate(). setelah disimpan ketika nantinya activity di destroy dan di muat ulang onCreate() jugak yang telah kita tahu memliki parameter Bundle jugak tapi dalam posisi kali ini parameter menjadi bernilai null namun bisa dibuat pengecualian jika dan simpanan di Bundle kita bisa get value yang sudah disimpan ke Activity seperti dengan method `bundle.get*("name");` 
<figure style="width:500px" class="align-center">
<img src="/images/bundleget.png">
<figcaption>bundle.get</figcaption>
</figure>

alhamdulillah pecah misterinya 
<figure style="width:500px" class="align-center">
<img src="/images/rotatestop.gif">
<figcaption>isuue rotate solve</figcaption>
</figure>

uml setelah penambahan method onSaveInstanceState()
<figure style="width:300px" class="align-center">
<img src="/images/stopwatchactivity2.png">
<figcaption>isuue rotate solve</figcaption>
</figure>

issue selanjutnya adalah ketika app berjalan user klik start button tiba tiba ada email atau notifikasi lain misal aplikasi chat terus kita liat/buka app chat itu aplikasi stopwatch otomatis tidak terlihat dan mungkin stopwatch akan terus berjalan menghitung tiap detik tapi bagaimana kalau aku pengen ketika app stopwatch tidak terlihat dia otomatis stop alias tdak berjalan?
