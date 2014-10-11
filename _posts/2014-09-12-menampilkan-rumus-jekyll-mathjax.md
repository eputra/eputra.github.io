---
layout: post
title: Menampilkan Rumus di Jekyll dengan MathJax
comments: true
permalink: menampilkan-rumus-jekyll-mathjax
---

Dengan menggunakan MathJax kita bisa menampilkan rumus matematika, fisika dan kimia di blog Jekyll offline (localhost) maupun online. MathJax sendiri adalah sebuah proyek opensource yang menggunakan JavaScript untuk menampilkan persamaan matematika di browser. Dengan menambahkan script dari MathJax kita bisa menampilkan lambang-lambang, persamaan, fungsi dan grafik matematika di blog kita dengan mudah.

## Blog Jekyll Offline (localhost)
Cara menampilkan rumus di blog jekyll offline (localhost) dengan mathjax:

- Download mathjax [disini](http://docs.mathjax.org/en/latest/installation.html "Download MathJax"), ekstrak mathjax di folder blog jekyll anda dan rename menjadi `math`

- Buat file `math.html` simpan di folder `_includes` 

{% highlight html %}
<script type="text/javascript"
src="http://localhost:4000/math/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
{% endhighlight %}

- Edit file `default.html` dan tambahkan kode `{% raw %}{% include math.html %}{% endraw %}`

{% highlight html %}
{% raw %}
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en-us">

  {% include head.html %}
  {% include math.html %}

  <body>

    <div class="container content">
      <div class="masthead">
        <h3 class="masthead-title">
          <a href="{{ site.baseurl }}" title="Home">{{ site.title }}</a>

          {% for page in site.pages_list %}
              &nbsp;&nbsp;&nbsp;<small><a href="{{ page[1]  }}">{{ page[0] }}</a></small>
          {% endfor %}
          
        </h3>
      </div>

      {{ content }}

      {% include comments.html %}

      <div class="footer">
        <p>
          &copy; {{ site.time | date: '%Y' }}. All rights reserved.
        </p>
      </div>
    </div>

  </body>
</html>
{% endraw %}
{% endhighlight %}

## Blog Jekyll Online
Untuk menampilkan rumus di blog jekyll online dengan mathjax anda tidak perlu mendownload mathjax, anda hanya perlu membuat file `math.html` simpan di folder `_includes`

{% highlight html %}
<script type="text/javascript"
src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
{% endhighlight %}

Edit file `defaul.html` dan tambahkan kode `{% raw %}{% include math.html %}{% endraw %}` seperti di blog jekyll offline (localhost).

## Contoh: Relativitas (Albert Einstein)
$$E=mc^2$$
Untuk menampilkan rumus seperti di atas saya menulis `$$E=mc^2$$` di markdown editor, contoh yang lain bisa anda lihat [disini](http://mathjax.org/demos/tex-samples/ "TeX Samples").

Happy Jekylling!
