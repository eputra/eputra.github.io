---
layout: post
title: Memasang Google Analysticst di Jekyll Github Pages
comments: true
permalink: google-analystics-jekyll-github-pages
---

Google Analystics adalah layanan gratis dari Google yang menampilkan statistik pengunjung sebuah situs web. Google Analystics dapat menelusuri pengunjung berdasarkan informasi halaman pengacu, termasuk mesin pencari, iklan, jaringan pay-per-click, email marketing, dan juga tautan yang terkandung dalam dokumen PDF. Dengan Google Analystics, pengguna dapat mengetahui iklan dan kata kunci apa yang paling banyak merujuk ke situs web pengguna.

> Sumber: [http://id.wikipedia.org/wiki/Google_Analystics](http://id.wikipedia.org/wiki/Google_Analystics)

## Cara Memasang Google Analysticst di Blog Jekyll Github Pages ##
- Daftar Google Analystics [disini](http://www.google.com/analytics/) (harus menggunakan Gmail)

- Edit file `head.html` dan tambahkan kode Google Analystics sebelum `</head>`

{% highlight html %}
{% raw %}
<head>
  <link href="http://gmpg.org/xfn/11" rel="profile">
  <meta http-equiv="content-type" content="text/html; charset=utf-8">

  <!-- Enable responsiveness on mobile devices-->
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1">

  <title>
    {% if page.title == "Home" %}
      {{ site.title }} &middot; {{ site.tagline }}
    {% else %}
      {{ page.title }} &middot; {{ site.title }}
    {% endif %}
  </title>

  <!-- CSS -->
  <link rel="stylesheet" href="{{ site.baseurl }}public/css/poole.css">
  <link rel="stylesheet" href="{{ site.baseurl }}public/css/syntax.css">

  <!-- Icons -->
  <link rel="apple-touch-icon-precomposed" sizes="144x144" href="{{ site.baseurl }}public/eka-putra.png">
  <link rel="shortcut icon" href="{{ site.baseurl }}public/eka-putra2.png">

  <!-- RSS -->
  <link rel="alternate" type="application/rss+xml" title="RSS" href="{{ site.baseurl }}atom.xml">

  <script type="text/javascript">
    var _gaq = _gaq || [];
    _gaq.push(['_setAccount', 'ID Pelacakan']);
    _gaq.push(['_setDomainName','github.io']);
    _gaq.push(['_trackPageview']);

    (function() {
      var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
      ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js';
      var s = document.getElementsByTagName('script')[0]; s.parentNode.insertBefore(ga, s);
    })();
  </script>
</head>
{% endraw %}
{% endhighlight %}

- Ganti `ID Pelacakan` dengan ID Pelacakan anda yang didapat dari situs web Google analystics, dan tunggu sekitar 24 jam.

Jika anda menggunakan kode yang didapat dari situs web Google Analystics blog Jekyll anda yang di hosting di Github Pages tidak akan pernah terlacak `Status: Pelacakan Tidak Dipasang`, saya sendiri tidak tahu kenapa. Tapi menurut pendapat mas [@SunDi3yansyah](http://twitter.com/SunDi3yansyah) itu mungkin masalahnya di cache, karena jekyll adalah blog/situs web berupa halaman HTML statis, jadi google belum membaca halaman update blog jekyll kita.

**Hasilnya**

![](/assets/IMG_1409191.png)

![](/assets/IMG_1409192.png)

Happy Jekylling!

{% include twitter.html %}
