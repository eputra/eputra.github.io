---
layout: post
title: Catatan Menginstall Ruby 2.0.0, Jekyll, dan GitHub di Xubuntu 14.04
comments: true
permalink: install-ruby-jekyll-github-di-xubuntu-1404
---

Ini hanya sekedar catatan saya karena saya suka lupa langkah-langkah menginstall ketiga aplikasi ini, padahal saya sangat butuh ketiga aplikasi ini untuk megurus blog ini. Dan mohon maaf jika saya tidak menjelaskan untuk apa saja perintah yang akan dijalankan karena saya juga masih belajar jadi tidak tau semua untuk apa fungsi perintah tersebut, tapi alhamdulillah berhasil di Xubuntu saya :D

Biasanya saya menjalankan perintah `sudo apt-get install ruby ruby-dev make gcc nodejs` untuk menginstall Ruby dan `sudo gem install jekyll` untuk menginstall Jekyll tapi waktu kemarin saya mau menginstall Jekyll ternyata error karena Jekyll membutuhkan Ruby versi 2.0.0 sedangkan Ruby yang ada di repository Xubuntu versi 1.9 atau 1.8 kalau tidak salah yang pasti versinya di bawah 2.0.0 jadi saya harus menginstall Ruby secara manual.

# Instalasi Ruby versi 2.0.0
- Menjalankan perintah `sudo apt-get install build-essential zlib1g-dev libssl-dev libreadline6-dev libyaml-dev`
- Mendownload Ruby versi 2.0.0 di [https://www.ruby-lang.org](https://www.ruby-lang.org "Ruby")
- Mengekstrak file Ruby-nya
- Masuk ke folder file Ruby yang tadi diekstrak menggunakan terminal
- Menjalankan perintah `./configure --prefix=/usr/local` lalu `make` terakhir `sudo make install`

# Instalasi Jekyll
Menjalankan perintah `sudo gem install jekyll` ketika saya menginstall Jekyll ini, Jekyll ada di versi 2.5.3

![Ruby Jekyll](/assets/ruby-jekyll.png "Ruby Jekyll")

# Instalasi GitHub
- Menjalankan perintah `sudo apt-get install git-core git-gui git-doc gitg`
- `git config --global user.name "Full Name"` Full Name diganti dengan nama yang digunakan di GitHub
- `git config --global user.email "your_email@youremail.com"` your_email@youremail.com diganti dengan email yang digunakan di GitHub
- `git config --global color.ui true`
- `ssh-keygen -t rsa -C "your_email@youremail.com"` your_email@youremail.com diganti dengan email yang digunakan di GitHub, disini saya menekan enter-enter saja, karena saya juga kurang tau artinya :D
- Membuka file `id_rsa.pub` yang ada di folder `/home/x43u/.ssh/`
- Mengcopy semua isi `id_rsa.pub` ke web GitHub, masuk ke web GitHub lalu masuk ke `Account Settings -> SSH Keys -> Add SSH Key` paste semua isi `id_rsa.pub` ke bagian Key dan Title diisi terserah sesuai keinginan
- Terakhir klik `Add key`

Happy Learning!

> Sumber :[http://stackoverflow.com/questions/16222738/how-do-i-install-ruby-2-0-0-correctly-on-ubuntu-12-04](http://stackoverflow.com/questions/16222738/how-do-i-install-ruby-2-0-0-correctly-on-ubuntu-12-04 "How do I install ruby 2.0.0 correctly on Ubuntu 12.04?"), [http://michaelchelen.net/81fa/install-jekyll-2-ubuntu-14-04/](http://michaelchelen.net/81fa/install-jekyll-2-ubuntu-14-04/ "Install Jekyll 2 on Ubuntu 14.04"), [http://www.panduaji.net/2014/02/belajar-menggunakan-git-bagian-1.html](http://www.panduaji.net/2014/02/belajar-menggunakan-git-bagian-1.html "Belajar Menggunakan GitHub Bagian 1")
