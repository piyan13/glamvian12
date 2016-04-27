---
title: "Ritual setelah install Linux"
tags:
 Linux
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
---

 <figure style="width: 400px" class="align-center">
<img src="/images/ubuntu16.jpg">
<figcaption>credit: google</figcaption>
</figure> 

 {% include toc title="Contents" icon="file-text" %}

 Setelah denger [ubuntu](www.ubuntu.com) launch versi LTS 
 (long terms support) di tahun ini langsung saja bergegas
 saya [downloadnya](http://www.ubuntu.com/download) sudah menjadi kebiasaan dari dulu untuk memakai versi LTS distro satu ini sih ya untuk harian memang sangat stable, tapi minusnya kurang update
 inovasi terbaru dari technology opensourcenya yang makin hari makin cepat pergerakannya, selesai install ubuntu ini beberapa ritual saya untuk menyempurnakan dekstop yang digunakan untuk sehari hari
 
 
## Install Driver wireless
 untuk laptop saya thinkpad edge e145 driver kebetulan wirelessnya gak langsung
 detect alias harus di install sendiri cukup konekin modem buka terminal dan 
 ```ruby
 sudo apt-get install bcmwl-kernel-source
 ```
 kebetulan hardware laptop saya pakek broadcom 
 
## Install codecs
 menurut [wikipedia](https://en.wikipedia.org/wiki/Codec) codec adalah progam
 computer untuk encoding atau decoding data digital. biasa kalau setelah install waktu play music player atau film di video player dia akan bisu dan kalau di telusuri di terminal akan mengeluarkan pesan tidak ditemukannya codec 
 kalau di ubuntuk tinggal klik perintah ini di terminal
 
 ```
 sudo apt-get install ubuntu-restricted-extras
 ```

## Install Chrome
 browser bawakan ubuntu adalah firefox dan saya lebih selera dengan Chrome 
 ```ruby
 wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
 ```