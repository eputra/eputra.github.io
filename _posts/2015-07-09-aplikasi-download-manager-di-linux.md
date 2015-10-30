---
layout: post
title: Aplikasi Download Manager di Linux yang Saya Gunakan
categories: linux
description: Beberapa aplikasi download manager di linux yang selalu saya gunakan
date: 2015-07-09
author: Eka Putra
comments: true
permalink: aplikasi-download-manager-di-linux
---

Tidak bisa dimungkiri kegiatan mendownload hampir setiap hari dilakukan oleh pengguna internet. Entah itu mendownload ebook, gambar, mp3, atau video. Namun disituasi-situasi tertentu download manager default browser kurang powerful, jika anda hanya mengandalkan download manager default browser anda akan kesulitan ketika ingin mendownload sebuah video di YouTube atau di Facebook.

Di Linux sendiri saya menggunakan 3 aplikasi download manager untuk memudahkan kegiatan mendownload.

## 1. DownThemAll!
DownThemAll! sendiri adalah sebuah add-ons di Mozilla Firefox, jadi jika ingin menggunakan DownThemAll!, terlebih dahulu anda harus menginstall Mozilla Firefox di sistem operasi anda. Untuk menginstall DownThemAll! di Mozilla Firefox sangat mudah, anda tinggal pergi ke menu add-ons manager lalu search DownThemAll! dan klik install.

![DownThemAll!](/assets/downthemall.png "DownThemAll!")

Sedikit tips dari saya agar anda tidak kesulitan ketika ingin membuka DownThemAll! Manager, anda pergi ke menu customize lalu pindahkan icon DownThemAll! Manager ke menu Mozilla Firefox terakhir klik exit customize.

![DownThemAll!](/assets/downthemall2.png "DownThemAll!")

-----

## 2. FlashGot
FlashGot sama seperti DownThemAll! ini adalah add-ons di Mozilla Firefox, FlashGot sendiri biasanya saya gunakan untuk mendownload video di Facebook atau mendownload film di Bioskops :D untuk cara menginstallnya sama seperti menginstall DownThemAll!

### Cara Menggunakan FlashGot
Untuk cara menggunakan FlashGot sangat mudah anda tinggal memutar video yang ingin anda download, secara otomatis icon FlashGot akan muncul di toolbar Mozilla Firefox.

![FlashGot](/assets/flashgot2.png "FlashGot")

Sedikit tips dari saya agar ketika mendownload video menggunakan FlashGot, dan download manager yang digunakan adalah DownThemAll!, anda pergi ke menu add-ons manager lalu klik preferences pada FlashGot dan pilih DTA pada menu download manager di tab general.

![FlashGot](/assets/flashgot.png "FlashGot")

-----

## 3. youtube-dl
Seperti namanya youtube-dl ini aplikasi untuk mendownload video di YouTube, ini bukan add-ons seperti 2 aplikasi di atas :D

### Cara Menginstall youtube-dl
Ada beberapa cara untuk menginstall youtube-dl ini

Menggunakan curl

<div class="console">
<pre>
<span class="ps1">$</span> sudo curl https://yt-dl.org/latest/youtube-dl -o /usr/local/bin/youtube-dl
<span class="ps1">$</span> sudo chmod a+rx /usr/local/bin/youtube-dl
</pre>
</div>

Menggunakan wget

<div class="console">
<pre>
<span class="ps1">$</span> sudo wget https://yt-dl.org/downloads/latest/youtube-dl -O /usr/local/bin/youtube-dl
<span class="ps1">$</span> sudo chmod a+rx /usr/local/bin/youtube-dl
</pre>
</div>

Menggunakan pip

<div class="console">
<pre>
<span class="ps1">$</span> sudo pip install youtube-dl
</pre>
</div>

<span class="box notice small">Update</span>10 Jul 2015<br>
youtube-dl sudah tersedia di repo. Jadi anda bisa menginstall youtube-dl seperti menginstall aplikasi pada umumnya, contohnya untuk distro Ubuntu. Anda bisa menginstall youtube-dl menggunakan Ubuntu Software Center.

![youtube-dl](/assets/youtube-dl3.png "youtube-dl")

Atau menggunakan terminal.

<div class="console">
<pre>
<span class="ps1">$</span> sudo apt-get install youtube-dl
</pre>
</div>

Untuk distro lain seperti Fedora, menyesuaikan paket manajemennya. Terimakasih infonya [Mas Mashudi](http://mashudisudonym.github.io/ "Mas Mashudi") :D

### Cara Menggunakan youtube-dl
Menggunakan youtube-dl juga sangat mudah anda tinggal menjalankan perintah

<div class="console">
<pre>
<span class="ps1">$</span> youtube-dl [url video youtube]
</pre>
</div>

di terminal dan videopun akan terdownload.

![youtube-dl](/assets/youtube-dl.png "youtube-dl")

youtube-dl juga bisa mendownload video di YouTube dengan kulaitas dan format sesuai dengan apa yang anda inginkan.

Untuk melihat kualitas dan format apa saja yang tersedia.

<div class="console">
<pre>
<span class="ps1">$</span> youtube-dl -F [url video youtube]
</pre>
</div>

Untuk mendownload videonya.

<div class="console">
<pre>
<span class="ps1">$</span> youtube-dl -f [nomor kualitas atau format video] [url video youtube]
</pre>
</div>

![youtube-dl](/assets/youtube-dl2.png "youtube-dl")

Untuk informasi lebih lengkap mengenai youtube-dl anda bisa pergi ke [https://rg3.github.io/youtube-dl/](https://rg3.github.io/youtube-dl/ "youtube-dl")

Happy Learning! and keep <3 FOSS
