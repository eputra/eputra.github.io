---
layout: post
title: Tugas Struktur Perulangan (Looping) WHILE dan DO-WHILE
description: Tugas cara membuat struktur perulangan atau looping while dan do while menggunakan bahasa pemrogramman c++
categories: c++
date: 2015-02-01
author: Eka Putra
comments: true
permalink: tugas-while-dan-do-while
---

1. Buatlah program untuk menjumlahkan n buah data, dengan n merupakan masukan dari piranti masukan kemudian hitungah rata-ratanya menggunakan intruksi WHILE
2. Buatlah program untuk menjumlahkan n buah data, tetapi yang dijumlahkan hanya data ganjil menggunakan intruksi DO-WHILE

### Menjumlahkan n Buah Data dan Menghitung Rata-ratanya Menggunakan WHILE
{% highlight c %}
//Menjumlahkan data dan menghitung rata-ratanya
#include<stdio.h>
int main()
{
	int e,data,angka[100];
	float k,a;
	printf ("Masukan banyaknya data = ");
	scanf ("%d", &data);
	e=1;
	k=0;
	while (e<=data)
	{
		printf ("Masukan data ke %d = ", e);
		scanf ("%d", &angka[e]);
		k=k+angka[e];
		e++;
	}
	a=k/data;
	printf ("Rata-rata data = %f\n", a);
	return 0;
}
{% endhighlight %}

<div class="console">
<pre>
<span class="ps1">$</span> ./while
Masukan banyaknya data = 2
Masukan data ke 1 = 3
Masukan data ke 2 = 4
Rata-rata data = 3.500000
</pre>
</div>

### Menjumlahkan n Buah Data Ganjil Menggunakan DO-WHILE
{% highlight c %}
//Menjumlahkan data ganjil
#include<stdio.h>
int main()
{
	int e,k,data,angka[100];
	printf ("Masukan banyaknya data = ");
	scanf ("%d", &data);
	e=1;
	k=0;
	do
	{
		printf ("Masukan data ke %d = ", e);
		scanf ("%d", &angka[e]);
		if (angka[e] % 2 != 0)
		{
			k=k+angka[e];
		}
		e++;
	}
	while (e<=data);
	printf ("Jumlah data ganjil = %d\n", k);
	return 0;
}
{% endhighlight %}

<div class="console">
<pre>
<span class="ps1">$</span> ./do_while
Masukan banyaknya data = 3
Masukan data ke 1 = 1
Masukan data ke 2 = 2
Masukan data ke 3 = 3
Jumlah data ganjil = 4
</pre>
</div>

Happy Programming!
