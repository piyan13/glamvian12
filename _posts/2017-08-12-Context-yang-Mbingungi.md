---
title: "Context yang Mbingungi"
tags:
 Android
header:
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
---
<figure style="width: 300px" class="align-center">
<img src="/images/dunning.jpg">
<figcaption></figcaption>
</figure> 
{% include toc title="Contents" icon="file-text" %}
Mengawali tulisan dengan mengutip dunning-kruger effect dimana semakin seseorang belajar semakin tambah pengetahuan semakin kompleks pula tingkat percaya dirinya seperti nampak pada gambar diatas heuheuheu kenapa Context itu mbingungi ? karena ada begitu banyak cara untuk mengakses Context dengan tipis sekali perbedaan diantara banyak cara tersebut, umumnya ada 4 cara untuk mengakses Context dalam
sebuah Activity yaitu:
{: style="text-align: justify;"}
**1.** getContext()

**2.** getBaseContext()

**3.** getApplicationContext()

**4.** getActionBar().getThemedContext()

## Context ?? ##
Lah Context itu apa? Context adalah abstrack class sebagai state aplikasi pada waktu tertentu, Context mewakili global atau dasar dari aplikasi dimana Activity atau Service bisa dibangun diatasnya. Fungsi Context? Context menyediakan implementasi umum untuk mengakses application level sama halnya system level resources sebagai contoh application level yang diakses seperti string maka menggunakan `getResources()` atau mengakses assets dengan `getAssets()` dan apapun system level resource yang ingin diakses bisa dengan `Context().getSystemService()`.
{: style="text-align: justify;"}
<figure style="width: 500px" class="align-center">
<img src="/images/hirarkiContext.png">
<figcaption>hirarki Context</figcaption>
</figure> 
Menelisik class abstrack Context sendiri tidak menemukan informasi yang mencerahkan akhirnya menelisik lebih dalam di hirarki class turunannya ke class ContextWrapper jugak tidak banyak menemukan pencerahan saat aplikasi extends class ContextWrapper jugak tidak banyak menemukan disana implementasi yang disediakan ContextWrapper yang berarti implementasi untuk Context disediakan oleh OS dan disembunyikan dari API.bila ingin melihat implementasi kongkrit tentang Context bisa melihat source code dari class [ContextImpl.java](https://github.com/android/platform_frameworks_base/blob/master/core/java/android/app/ContextImpl.java)
{: style="text-align: justify;"}


