---
layout: post
title: Use Case Bisnis dan Use Case Sistem
categories: uml
description: Perbedaan use bisnis dan use case sistem. Use case bisnis adalah model yang digunakan untuk menggambarkan proses bisnis organisasi. Dan use case sistem adalah bagian tingkat tinggi dari fungsionalitas yang disediakan oleh sistem.
date: 2016-03-16
author: Eka Putra
comments: true
permalink: /use-case-bisnis-dan-use-case-sistem/
---

Use case adalah fungsi yang ada di dalam sebuah sistem. Itulah definisi use case dikebanyakan buku tentang UML dalam bahasa Indonesia. Namun dalam kenyataannya ternyata use case tidak hanya digunakan untuk memodelkan fungsi-fungsi yang ada di dalam sebuah sistem. Sekitar satu minggu kebelakang saya sempat dibingungkan oleh use case ini.

<h3 class="message">
	Sebenarnya use case itu fungsi yang ada di dalam sistem atau aplikasi?
</h3>

Saya sempat membaca beberapa buku tentang UML dalam bahasa Indonesia dari perpustakaan, dari empat buku yang saya baca hanya satu buku yang dapat menjawab pertanyaan saya. Tiga buku yang lainnya mendefinisikan use case seperti di paragraf awal, bahwa use case adalah fungsi yang ada di dalam sebuah sistem.

Dalam buku yang berjudul Pemodelan Sistem Informasi Berorientasi Objek dengan UML tulisan Bapak Sholiq disebutkan bahwa use case itu dibagi menjadi dua, yaitu use case bisnis (yang selama ini saya sangka sebagai use case sistem) dan use case sistem (yang selama ini saya sangka sebagai use case aplikasi).

Dalam buku tersebut use case bisnis didefinisikan sebagai model yang digunakan untuk menggambarkan proses bisnis organisasi. Dengan kata lain, use case bisnis memberitahukan kepada pembaca tentang aktivitas bisnis utama apa saja yang organisasi lakukan.

Dan use case sistem didefinisikan sebagai bagian tingkat tinggi dari fungsionalitas yang disediakan oleh sistem. Dengan kata lain, use case sistem menggambarkan bagaimana seseorang menggunakan sistem.

### Perbedaan Antara Pemodelan Bisnis dan Pemodelan Sistem

Item | Pemodelan Bisnis | Pemodelan Sistem
--- | --- | ---
Use Case | Menjelaskan apa yang bisnis kerjakan. Tidak mempedulikan apakah proses dilakukan secara otomatis menggunakan teknologi informasi atau manual. | Menjelaskan apa yang sistem lakukan di dalam bisnis. Hanya proses-proses yang direncanakan dilakukan secara otomatis yang disebut use case.
Aktor | Eksternal terhadap organisai. Berada diluar organisasi tetapi berpartisipasi terlibat dalam proses bisnis organisasi. | Eksternal terhadap sistem (mungkin internal terhadap organisasi).
Pekerja Bisnis | Internal terhadap organisasi. | Tidak digunakan.

<span class="box warning small">Note</span> Pekerja bisnis juga termasuk aktor, hanya berbeda istilah saja. Contoh dalam sebuah use case bisnis bank, **aktor** nasabah (eksternal) dan **pekerja bisnis** teller (internal). Teller sebagai pekerja bisnis (internal) di use case bisnis bisa menjadi aktor (eksternal) di use case sistem.

### Singkatnya
**Use case bisnis** menjelaskan apa yang bisnis kerjakan. Dan **use case sistem** menjelaskan apa yang sistem lakukan di dalam bisnis atau bisa juga disebut use case sistem adalah **otomatisasi dari beberapa use case yang ada di dalam proses bisnis** (tidak semua use case bisnis harus diotomatisasi).

Jadi dalam membuat sebuah use case yang harus pertama dibuat adalah use case bisnis, selanjutnya analisis kembali use case bisnis yang telah dibuat, cari use case bisnis mana yang harus diotomatisasi, lalu buat use case sistem dari use case bisnis yang harus diotomatisasi tersebut.

Happy Learning!

---

### Referensi
1. Sholiq. 2006. *Pemodelan Sistem Informasi Berorientasi Objek dengan UML*. Yogyakarta: Graha Ilmu.