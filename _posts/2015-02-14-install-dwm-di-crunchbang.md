---
layout: post
title: Install DWM di CrunchBang
description: Cara menginstall windows manager dwm di linux cruncbang
categories: linux
date: 2015-02-14
author: Eka Putra
comments: true
---

DWM singkatan dari Dynamic Windows Manager adalah sebuah tiling yang dibuat menggunakan bahasa pemrograman C, itu salah satu alasan kenapa saya memilih DWM untuk tiling di CrunchBang selain berukuran kecil juga karena dibuat menggunakan bahasa pemrograman C, karena kemarin di semester 1 bahasa pemrograman yang dipelajari yaitu C++ hampir miriplah dengan C, saya tidak ingin ilmu itu sia-sia ya walaupun masih ngedit-ngedit config punya orang :3

### Instalasi
- Pertama install `acpi` terlebih dahulu `acpi` ini berguna untuk menampilkan status battery di statusbar DWM nanti `sudo apt-get install acpi`
- Download DWM dan confignya yang saya gunakan [disini](http://moeenn.deviantart.com/art/DWM-October-14-Shot-491561778 "Download DWM"), untuk `config.h`-nya ganti dengan config punya saya [disini](https://gist.github.com/eka-putra/10a43bc8745469b79aa9 "Download config.h")
- Ekstrak lalu install DWMnya `sudo make clean install`

### Startup Script
Buat file dengan nama `dwm-startup` buat file ini executable `chmod +x dwm-starup` simpan di `/usr/bin`
{% highlight bash %}
#!/usr/bin/env bash

# Set `nitrogen` to change the wallpaper
nitrogen --restore &

# Start `dwm` with a modified status bar
while true; do
  bat=$(acpi -b | awk '{ print $4 }' | sed 's/,//g');
  dwm_bat=$(echo -e "\x06$bat\x08//");
  time=$(date '+%a, %d %b %I:%M %p');
  dwm_time=$(echo -e "\x06$time");
  dwm_stat="$dwm_bat$dwm_time";
  xsetroot -name "$dwm_stat";
  sleep 10s
done & exec dwm
{% endhighlight %}

### X
Buat file dengan nama `.xinitrc` buat file ini executable `chmod +x .xinitrc` simpan di `/home/username/`
{% highlight bash %}
#!/usr/bin/env bash

# Set the default window manager
DEFAULT=openbox-session

# Start `Openbox`/`dwm`
case $1 in
  openbox-session)
    exec openbox-session
  ;;
  dwm)
    exec dwm-startup
  ;;
  *)
    exec $DEFAULT
  ;;
esac
{% endhighlight %}

### SLiM
Sekarang atur SLiM agar ketika boot mengexecute `.initrc`

- Buka `slim.conf` di folder `/etc`
- Hilangkan tanda komentar dibagian `login_cmd exec /bin/sh - ~/.xinitrc %session`
- Berikan tanda komentar dibagian `login_cmd exec /bin/bash -login /etc/X11/Xsession %session`
- Tambahkan `dwm` dibagian `sessions`

Kurang lebih `slim.conf` jadi seperti ini (kalau di saya dari line 36-55)
{% highlight bash %}
login_cmd           exec /bin/sh - ~/.xinitrc %session
# login_cmd           exec /bin/bash -login /etc/X11/Xsession %session

# Commands executed when starting and exiting a session.
# They can be used for registering a X11 session with
# sessreg. You can use the %user variable
sessionstart_cmd	/usr/share/crunchbang/cb-user-setup %user
# sessionstop_cmd	some command

# Start in daemon mode. Valid values: yes | no
# Note that this can be overriden by the command line
# options "-d" and "-nodaemon"
# daemon	yes

# Available sessions (first one is the default).
# The current chosen session name is replaced in the login_cmd
# above, so your login command can handle different sessions.
# see the xinitrc.sample file shipped with slim sources
# sessions            default,startxfce4,openbox,ion3,icewm,wmaker,blackbox,awesome
sessions            openbox-session,dwm
{% endhighlight %}

Terakhir silahkan `reboot` lalu waktu `login` pilih `dwm` dengan cara menekan `F1` hasilnya kurang lebih seperti dibawah ini :D

![CrunchBang DWM](/assets/dwm1.png "CrunchBang DWM")

Happy Learning! and keep <3 Open Source
