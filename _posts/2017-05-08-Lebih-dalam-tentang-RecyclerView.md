---
title: "Lebih dalam tentang RecyclerView"
tags:
 Android
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
---
<figure style="width: 700px" class="align-center">
<img src="/images/udaRecycle.gif">
<figcaption>RecyclerView shunshine udacity</figcaption>
</figure>

Mei tahun 2017 begitu membara cukup terseok seok hanya untuk sekedar istiqomah dan waktunya untuk mengupas habis beberapa ketertinggalan diving in biar gak makin tertinggal okey RecyclerView di perkenalkan pada saat android L adalah sebuah ViewGroup baru yang di persiapkan untuk render view adapter menurut mentor di udacity RecyclerView menjadi inti dari banyak aplikasi dengan alesan untuk hal hal yang compleks penangannya daripada ListView isu utama dari RecylcerView adalah mengenai garbage collection memory yang terpakai saat menampilkan data dengan banyak nan kompleks
{: style="text-align: justify;"}

Modular hampir di setiap bagian dari RecyclerView dan untuk mendalaminya saya harus merasa nyaman dengan element elementnya kayak `RecyclerView.Adapter` , `LayoutManager` , `ItemAnimator`  dll berangkat dari sana mencoba untuk menelaah satu persatu 
{: style="text-align: justify;"}
## Adapter
RecyclerView mempunyai Adapter sebuah subclass RecyclerView.Adapter digunakan untuk mengikat data dari beberapa sumber data ke View, Adapter mengirimkan View ke RecyclerView melalui object ViewHolder, ViewHolder sendiri berisikan refrence root object view untuk item digunakan untuk meng cache object view di layout supaya mempermudah pada saat memperbarui view dengan data yang baru dalam app contoh yang saya pelajari dari udacity class adapter saya namakan GreenAdapter.java
{: style="text-align: justify;"}
