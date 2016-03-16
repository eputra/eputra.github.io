---
layout: post
title: Fix ncmpcpp dan mpd di Xubuntu 14.04
categories: linux
description: Mengatasi masalah ncmpcpp dan mpd di Xubuntu 14.04, playlist dan browser musik di ncmpcpp kosong padahal mpd sudah jalan.
date: 2015-09-27
author: Eka Putra
comments: true
---

Sebenarnya masalah ini sudah saya alami sejak lama (hampir enam bulan mungkin), saat pertama kali menginstall ncmpcpp dan mpd di Xubuntu 14.04 masalah ini sudah ada. Tapi tidak tahu kenapa saya malas memperbaikinya :3 sampai akhirnya kemarin ada teman Facebook saya yang menanyakan masalah ini. Saya pun termotivasi untuk memperbaiki masalah ini, dan jadilah tulisan sederhana ini sebagai dokumentasi :D

Jadi ketika kita menginstall mpd di Xubuntu 14.04, mpd dengan otomatis masuk ke daftar aplikasi autostart, tapi ketika kita menjalankan ncmpcpp, playlist dan browser musik kita kosong[^fn-fn1].

Agar playlist dan browser musik kita tidak kosong kita harus menghentikan dan menjalankan kembali mpd. Saya sendiri tidak tahu kenapa masalah ini bisa terjadi, mungkin ada masalah ketika mpd autostart di Xubuntu 14.04.

Cara saya mengatasi masalah ini adalah dengan menghilangkan mpd dari daftar aplikasi autostart, saya coba dengan menggunakan aplikasi **Session and Startup** default Xubuntu 14.04, dengan menghilangkan tanda centang pada mpd dan dengan menghapus file `mpd.dekstop` di folder `~/.config/autostart`, tapi cara ini tidak bekerja, mpd tetap saja autostart.

![Session dan Startup](/assets/session-and-startup.png "Session dan Startup")

Setelah saya browsing saya menemukan tulisan ini [MPD - Community Help Wiki](https://help.ubuntu.com/community/MPD "MPD - Community Help Wiki"), jadi untuk menghilangkan mpd dari daftar aplikasi autostart kita bisa dengan menjalankan perintah ini di terminal.

<div class="console">
<pre>
<span class="ps1">$</span> sudo service mpd stop
<span class="ps1">$</span> sudo update-rc.d mpd disable
</pre>
</div>

Dan ini ada script kecil untuk menjalankan ncmpcpp dan mpd, agar ketika anda akan memutar musik di ncmpcpp, tidak harus mengetik dua kali/menjalankan dua perintah di terminal (pertama menjalankan mpd lalu ncmpcpp), jadi anda hanya perlu menjalankan satu perintah di terminal.

{% highlight bash %}
#!/bin/sh
# musik
# ----------
# Script kecil untuk menjalankan mpd dan ncmpcpp :D

if [ "$(pidof mpd)" ]; then
    ncmpcpp
    exit
else
    mpd
    ncmpcpp
    exit
fi
{% endhighlight %}

Saya beri nama `musik` untuk script di atas, dan jangan lupa untuk membuat script `musik` executable dengan menjalankan perintah

<div class="console">
<pre>
<span class="ps1">$</span> chmod +x musik
</pre>
</div>

Simpan script `musik` di folder `/usr/bin`. Sekarang dengan menggunakan script `musik` jika anda ingin memutar musik di ncmpcpp anda hanya perlu mengetik satu kali/menjalankan satu perintah di terminal yaitu hanya

<div class="console">
<pre>
<span class="ps1">$</span> musik
</pre>
</div>

Happy Learning!

-----

[^fn-fn1]: Padahal mpd sudah berjalan (autostart).