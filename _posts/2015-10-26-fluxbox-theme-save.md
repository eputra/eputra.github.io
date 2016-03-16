---
layout: post
title: Fluxbox Theme Save
categories: linux
description: Menyimpan config tema fluxbox (style, init, apps, gtk theme, icon, and wallpaper)
date: 2015-10-26
author: Eka Putra
comments: true
---

<div class="message">
	Fluxbox theme (style, init, apps, gtk theme, icon, and wallpaper)
</div>

Memang ketika kita mengganti style di windows manager fluxbox tampilan fluxbox tidak tampil maksimal, kita harus menyesuaikan file init fluxbox dengan style sekarang yang kita gunakan.

Selain menyesuaikan file init kita juga harus menyesuaikan tema gtk, icon, dan wallpaper agar tampilan fluxbox kita benar-benar maksimal dan selaras dengan style yang sekarang kita gunakan.

Nah setelah kita mendapatkan tampilan fluxbox yang maksimal dengan menggunakan style yang sekarang dan ingin mencoba style yang baru tentu itu sebuah dilema.

Kita ingin mencoba style yang baru namun takut style yang baru itu kurang bagus tampilannya dari style yang sekarang, dan ketika kita ingin kembali ke style yang sebelumnya kita harus kembali menyesuaikan file init, tema gtk, icon, dan wallpaper.

Tentu itu lumayan menyita waktu kita dan kegiatan yang kurang menyenangkan, karena kita harus melakukan hal yang sama dua kali, ingat pepatah mengatakan, jangan melakukan config yang sama dua kali :3

Untuk itu saya mencoba membuat bash script untuk membackup/save dan merestore theme fluxbox.

{% highlight bash %}
#!/bin/sh
# fluxbox-ts
# ----------
# Fluxbox Theme Save (style, init, apps, gtk theme, icon, and wallpaper)

user=`whoami`
style=`grep session.styleFile /home/$user/.fluxbox/init | awk -F/ '{print $6}'`
mkdir /home/$user/.fluxbox/themes/$style
cp /home/$user/.fluxbox/init /home/$user/.fluxbox/themes/$style/init
cp /home/$user/.fluxbox/apps /home/$user/.fluxbox/themes/$style/apps
cp /home/$user/.gtkrc-2.0 /home/$user/.fluxbox/themes/$style/.gtkrc-2.0
cp /home/$user/.config/gtk-3.0/settings.ini /home/$user/.fluxbox/themes/$style/settings.ini
cp /home/$user/.fehbg /home/$user/.fluxbox/themes/$style/.fehbg
cat > /home/$user/.fluxbox/themes/$style/$style <<++
#!/bin/sh
cp /home/$user/.fluxbox/themes/$style/init /home/$user/.fluxbox/init
cp /home/$user/.fluxbox/themes/$style/apps /home/$user/.fluxbox/apps
cp /home/$user/.fluxbox/themes/$style/.gtkrc-2.0 /home/$user/.gtkrc-2.0
cp /home/$user/.fluxbox/themes/$style/settings.ini /home/$user/.config/gtk-3.0/settings.ini
cp /home/$user/.fluxbox/themes/$style/.fehbg /home/$user/.fehbg
++
chmod +x /home/$user/.fluxbox/themes/$style/$style
{% endhighlight %}

- Simpan script di atas dengan nama `fluxbox-ts` 
- Buat `fluxbox-ts` executable dengan menjalankan perintah `chmod +x fluxbox-ts` 
- Simpan `fluxbox-ts` di folder `/usr/bin`

### Cara Menggunakan `fluxbox-ts`
- Buat folder `themes` di folder `/home/user_name/.fluxbox` dengan menjalankan perintah `mkdir /home/user_name/.fluxbox/themes`
- Setting tampilan fluxbox semaksimal mungkin
- Dan jalankan perintah `fluxbox-ts` untuk menyimpan theme yang sekarang digunakan

Misalkan kita mengganti style fluxbox kita dan mengedit file init, mengganti tema gtk, icon, dan wallpaper. Dan kita ingin kembali ke theme sebelumnya yang sudah di save, kita tinggal menjalan bash script yang ada di folder `/home/user_name/.fluxbox/themes/style_name`.

Selanjutnya kita tinggal log out lalu log in kembali ke fluxbox dan tampilan fluxbox kita akan sama dengan theme fluxbox yang telah kita save sebelumnya tanpa harus mengedit file init, mengganti tema gtk, icon, dan wallpaper.

`fluxbox-ts` juga ada di [GitHub](https://github.com/eka-putra/fluxbox-ts "fluxbox-ts"), jika ada yang salah atau kurang dari `fluxbox-ts` anda bisa open issue atau pull request.

Happy Learning!