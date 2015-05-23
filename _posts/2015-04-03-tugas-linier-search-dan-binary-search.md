---
layout: post
title: Tugas Linier Search dan Binary Search
description: Tugas cara membuat linier search dan binary search menggunakan bahasa pemrogramman c++
categories: c++
date: 2015-04-03
author: Eka Putra
comments: true
permalink: tugas-linier-search-dan-binary-search
---

###Linier Search
{% highlight c %}
#include<iostream>
using namespace std;
int main()
{
	int cari, ketemu, index, data[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
	cout<<"Angka yang dicari : ";
	cin>>cari;
	for (int x=0; x<10; x++)
	{
		if (data[x] == cari)
		{
			ketemu = 1;
			index = x;
		}
	}
	if (ketemu == 1)
	cout<<"Angka "<<cari<<" ada di index "<<index<<endl;
	else
	cout<<"Angka "<<cari<<" tidak ada"<<endl;
	return 0;
}
{% endhighlight %}
{% highlight html %}
[~]-> cd tugas/
[~/tugas]-> ./linier
Angka yang dicari : 9
Angka 9 ada di index 8
[~/tugas]-> ./linier
Angka yang dicari : 99
Angka 99 tidak ada
{% endhighlight %}

###Binary Search
{% highlight c %}
#include<iostream>
using namespace std;
int main()
{
	int data[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
	int l, r, m, n, cari, ketemu, index;
	n = 10;
	l = 0;
	r = n-1;
	ketemu = 0;
	cout<<"Angka yang dicari : ";
	cin>>cari;
	while (l<=r && ketemu == 0)
	{
		m = (l+r)/2;
		if (data[m] == cari)
		{
			ketemu = 1;
			index = m;
		}
		else if (cari < data[m])
		r = m-1;
		else
		l = m+1;
	}
	if (ketemu == 1)
	cout<<"Angka "<<cari<<" ada di index "<<index<<endl;
	else
	cout<<"Angka "<<cari<<" tidak ada"<<endl;
	return 0;
}
{% endhighlight %}
{% highlight html %}
[~]-> cd tugas/
[~/tugas]-> ./binary
Angka yang dicari : 9
Angka 9 ada di index 8
[~/tugas]-> ./binary
Angka yang dicari : 99
Angka 99 tidak ada
{% endhighlight %}

Happy Programming!
