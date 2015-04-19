---
layout: post
title: Tugas Fungsi (Function)
comments: true
permalink: tugas-fungsi-atau-function
---

Buatlah program untuk menentukan bilangan yang terbesar dan terkecil dari 2 buah bilangan yang diinputkan

## Menentukan Bilangan Terbesar dan Terkecil Menggunakan Fungsi atau Function
{% highlight c %}
#include<stdio.h>
int findmax (int max1, int max2);
int findmin (int min1, int min2);
void printmax (int pmax);
void printmin (int pmin);
int main()
{
	int e,k,a,p;
	printf ("Masukan nilai pertama	: ");
	scanf ("%d", &e);
	printf ("Masukan nilai kedua	: ");
	scanf ("%d", &k);
	if (e==k)
	{
		printf ("Nilai yang anda masukan bernilai sama\n");
	}
	else
	{
	a=findmax(e,k);
	p=findmin(e,k);
	printmax(a);
	printmin(p);
	}
}
int findmax (int max1, int max2)
{
	if (max1>max2)
	{
		return max1;
	}
	else
	{
		return max2;
	}
}
int findmin (int min1, int min2)
{
	if (min1<min2)
	{
		return min1;
	}
	else
	{
		return min2;
	}
}
void printmax (int pmax)
{
	printf ("Nilai terbesar adalah : %d\n", pmax);
}
void printmin (int pmin)
{
	printf ("Nilai terkecil adalah : %d\n", pmin);
}
{% endhighlight %}
{% highlight html %}
[~]-> cd tugas/
[~/tugas]-> ./fungsi
[~]-> ./fungsi
Masukan nilai pertama	: 1
Masukan nilai kedua	: 2
Nilai terbesar adalah	: 2
Nilai terkecil adalah	: 1
[~]-> ./fungsi
Masukan nilai pertama	: 2
Masukan nilai kedua	: 1
Nilai terbesar adalah	: 2
Nilai terkecil adalah	: 1
[~]-> ./fungsi
Masukan nilai pertama	: 1
Masukan nilai kedua	: 1
Nilai yang anda masukan bernilai sama
{% endhighlight %}

Happy Programming!
