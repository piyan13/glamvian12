---
title: "AsycnTask 🆚 AsycnTaskLoader"
tags:
 Android
header:
    image: Asyntask.png
    caption: "android developer"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
---
selamat datang di bulan ramadhan akhirnya satu tahun mengudara blog minimalis ini.Beberapa hari ini saya terlibat praktek terlalu dalam dengan LifeCycle android termasuk mengenai dasar Thread seperti diketahui android support multitasking dimana setiap aplikasi android dibagi menjadi multiple thread semuanya dapat berjalan bersamaan dalam satu kali eksekusi,eksekusi multiple thread ini di jadwalkan oleh operating system untuk berjalan di core CPU yang berbeda, untuk mempermudah developer android apps di android memiliki satu thread user interface yang mana bertanggung jawab untuk getting event dari berbagai macam sensor dan selanjutnya mengatur frame untuk menggambarnya agar berjalan pada 60 frame per detik karena itulah belajar thread LifeCycle ini sangat fundamental sekali dalam kasus yang saya temui sebisa mungkin meminimkan proses di thread utama karena akan membuat aplikasi menjadi force close  
{: style="text-align: justify;"}

## AsycnTask ##
