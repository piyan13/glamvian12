---
title: "Failed to resized display"
tags:
 Linux
layout: single
author_profile: true
read_time: true
comments: true
share: true
realated: true
---

<figure style="width: 400px" class="align-center">
<img src="/images/drivereroorvlc.png">
<figcaption></figcaption>
</figure> 
enak enak liat video di vlc tiba tiba gambarnya pada gak karuan seperti foto diatas analisa pertama adalah mungkin karena codecnya setelah saya update ternyata sama saja. Maklum baru ganti peralatan yang baru sekarang makek lenovo thinkpad e145 jadi baru kali ini kenak masalah video sebelumnya makek acer aspire 5315 asik asik aja heuheuheu biar gak makin penasaran chek errornya

<figure style="width: 400px" class="align-center">
<img src="/images/drivervlc_konsole.png">
<figcaption></figcaption>
</figure> 
setelah baca baca masalah resized diplay itu error mengarah pada ketidak cocokan driver untuk vga yang dipakek langsung aja cuss ke driver manager dengan alt+f2 
dengan bukak vlc mode konsole waktu play video munculah error failed to resized display 
<figure style="width: 400px" class="align-center">
<img src="/images/drivermanager.png">
<figcaption></figcaption>
</figure> 

untuk speck vga ati yang sesuai dengan laptop yang yang saya pake disarankan memakai driver bernama `fglrx`  
<figure style="width: 400px" class="align-center">
<img src="/images/drivermanager1.png">
<figcaption></figcaption>
</figure> 
setelah ganti dengan driver no priopetary diatas alhasil videonya jadi sempurna lagi lagi problem solved dan dapat ilmu baru lagi salah satu dari manfaat linux opensouce ya itu heuheuheu

<figure style="width: 400px" class="align-center">
<img src="/images/solved.png">
<figcaption></figcaption>
</figure> 
okey sekian tulisan saya kali ini dan saya sudah gak sabar untuk melanjutkan video yang tadi semoga dapat berguna
