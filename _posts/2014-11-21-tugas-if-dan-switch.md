---
layout: post
title: Tugas IF dan SWITCH
comments: true
permalink: tugas-if-dan-switch
---

1. Buatlah program untuk mengkonversi nilai huruf menjadi nilai angka dengan ketentukan masukan berupa nilai huruf, menggunakan inturksi IF dan SWITCH.
	* Nilai huruf : A -> Nilai angka : 4
	* Nilai huruf : B -> Nilai angka : 3
	* Nilai huruf : C -> Nilai angka : 2
	* Nilai huruf : D -> Nilai angka : 1
	* Nilai huruf : E -> Nilai angka : 0
2. Buatlah program untuk menseleksi suatu bilangan menggunakan intruksi IF dan SWITCH.
	* 0 <= nilai < 30 : Nilai rendah
	* 30 <= nilai < 60 : Nilai sedang
	* 60 <= nilai <= 100 : Nilai tinggi

#### Konversi Nilai Huruf Menjadi Nilai Angka Menggunakan IF
{% highlight c %}
//Konversi huruf ke angka
#include <stdio.h>
int main()
{
	char khuruf;
	printf ("Masukan huruf [A - E] = ");
	scanf ("%c", &khuruf);
	if (khuruf == 'A')
		printf ("Nilai = 4\n");
	else
		if (khuruf == 'B')
			printf ("Nilai = 3\n");
		else
			if (khuruf == 'C')
				printf ("Nilai = 2\n");
			else
				if (khuruf == 'D')
					printf ("Nilai = 1\n");
				else
					if (khuruf == 'E')
						printf ("Nilai = 0\n");
					else
						printf ("Dibaca ya perintahnya\n");
	return 0;
}
{% endhighlight %}
{% highlight html %}
[~]-> cd tugas/
[~/tugas]-> ./if
Masukan huruf [A - E] = A
Nilai = 4
{% endhighlight %}

#### Konversi Nilai Huruf Menjadi Nilai Angka Menggunakan SWITCH
{% highlight c %}
//Konversi huruf ke angka
#include <stdio.h>
int main()
{
	char khuruf;
	printf ("Masukan huruf [A - E] : ");
	scanf ("%c", &khuruf);
	switch (khuruf)
	{
		case 'A' : printf ("Nilai 4\n"); break;
		case 'B' : printf ("Nilai 3\n"); break;
		case 'C' : printf ("Nilai 2\n"); break;
		case 'D' : printf ("Nilai 1\n"); break;
		case 'E' : printf ("Nilai 0\n"); break;
		default  : printf ("Dibaca ya perintahnya\n");
	}
	return 0;
}
{% endhighlight %}
{% highlight html %}
[~]-> cd tugas/
[~/tugas]-> ./switch
Masukan huruf [A - E] = A
Nilai = 4
{% endhighlight %}

#### Menseleksi Suatu Bilangan Menggunakan IF
{% highlight c %}
//Menseleksi suatu bilangan
#include <stdio.h>
int main()
{
	int nilai;
	printf ("Masukan angka [0 - 100] : ");
	scanf ("%d", &nilai);
	if (nilai <= 0 || nilai < 30)
		printf ("Nilai rendah\n");
	else
		if (nilai <= 30 || nilai < 60)
			printf ("Nilai sedang\n");
		else
			if (nilai <= 60 || nilai <= 100)
				printf ("Nilai tinggi\n");
			else
				printf ("Dibaca ya perintahnya\n");
	return 0;
}
{% endhighlight %}
{% highlight html %}
[~]-> cd tugas/
[~/tugas]-> ./if2
Masukan angka [0 - 100] : 99
Nilai tinggi
{% endhighlight %}

#### Menseleksi Suatu Bilangan Menggunakan SWITCH
{% highlight c %}
//Menseleksi suatu bilangan
#include <stdio.h>
int main()
{
	int nilai;
	printf ("Masukan nilai [0 - 100] : ");
	scanf ("%d", &nilai);
	switch (nilai)
	{
		case 0 ... 29 : printf ("Nilai rendah\n"); break;
		case 30 ... 59 : printf ("Nilai sedang\n"); break;
		case 60 ... 100 : printf ("Nilai tinggi\n"); break;
		default : printf ("Dibaca ya perintahnya\n");
	}
	return 0;
}
{% endhighlight %}
{% highlight html %}
[~]-> cd tugas/
[~/tugas]-> ./switch2
Masukan angka [0 - 100] : 99
Nilai tinggi
{% endhighlight %}

Happy Programming!
