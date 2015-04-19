---
layout: post
title: Tugas Struktur (Struct)
comments: true
permalink: tugas-struktur-atau-struct
---

1. Buat program untuk mencatat data mahasiswa yang terdiri dari field : Nama, Alamat, Tempat Tanggal Lahir, Jenis Kelamin
2. Buatlah struct untuk data buku yang berisi tentang : Kode Buku, Nama Buku, Tahun Terbit, Pengarang dan Harga

Note : Gunakan Array Of Struct

## Mencatat Data Mahasiswa
{% highlight c %}
#include<iostream>
#include<iomanip>
using namespace std;
int main () {
	struct mahasiswa {
		char nama[99];
		char alamat[99];
		char ttl[99];
		char jk[99];
	};
	mahasiswa mhs [3];
	cout<<"---------------------------------------------"<<endl;
	cout<<"Input (3 Data)"<<endl;
	cout<<"---------------------------------------------"<<endl;
	for (int i=0; i<3; i++) {
		cout<<"Nama		: "; cin.getline(mhs[i].nama, 99);
		cout<<"Alamat		: "; cin.getline(mhs[i].alamat, 99);
		cout<<"TTL		: "; cin.getline(mhs[i].ttl, 99);
		cout<<"Jenis Kelamin	: "; cin.getline(mhs[i].jk, 99);
		cout<<"---------------------------------------------"<<endl;
	}
	cout<<"\n\n\n";
	cout<<setfill('-')<<setw(1)
		<<"+"<<setw(81)<<"-"<<setw(1)<<"+"<<endl;
	cout<<setfill(' ')
		<<setw(1)<<"|"<<setw(41)<<"Output"<<setw(41)<<"|"<<endl;
	cout<<setfill('-')
		<<setw(1)<<"+"<<setw(16)<<"-"
		<<setw(1)<<"+"<<setw(16)<<"-"
		<<setw(1)<<"+"<<setw(30)<<"-"
		<<setw(1)<<"+"<<setw(16)<<"-"
		<<setw(1)<<"+"<<endl;
	cout<<setfill(' ')
		<<setw(1)<<"|"<<setw(16)<<left<<"Nama"
		<<setw(1)<<"|"<<setw(16)<<left<<"Alamat"
		<<setw(1)<<"|"<<setw(30)<<left<<"Tempat Tanggal Lahir"
		<<setw(1)<<"|"<<setw(16)<<left<<"Jenis Kelamin"
		<<setw(1)<<"|"<<endl;
	cout<<setfill('-')
		<<setw(1)<<"+"<<setw(16)<<"-"
		<<setw(1)<<"+"<<setw(16)<<"-"
		<<setw(1)<<"+"<<setw(30)<<"-"
		<<setw(1)<<"+"<<setw(16)<<"-"
		<<setw(1)<<"+"<<endl;
	for (int i=0; i<3; i++) {
		cout<<setfill(' ')
			<<setw(1)<<"|"<<setw(16)<<left<<mhs[i].nama
			<<setw(1)<<"|"<<setw(16)<<left<<mhs[i].alamat
			<<setw(1)<<"|"<<setw(30)<<left<<mhs[i].ttl
			<<setw(1)<<"|"<<setw(16)<<left<<mhs[i].jk
			<<setw(1)<<"|"<<endl;
		cout<<setfill('-')
			<<setw(1)<<"+"<<setw(16)<<"-"
			<<setw(1)<<"+"<<setw(16)<<"-"
			<<setw(1)<<"+"<<setw(30)<<"-"
			<<setw(1)<<"+"<<setw(16)<<"-"
			<<setw(1)<<"+"<<endl;
	}
}
{% endhighlight %}
{% highlight html %}
[~]-> cd tugas/
[~/tugas]-> ./struct1
---------------------------------------------
Input (3 Data)
---------------------------------------------
Nama		: Eka Putra
Alamat		: Cileuya
TTL		: Kuningan, 14 November 1995
Jenis Kelamin	: Laki-laki
---------------------------------------------
Nama		: Suryana
Alamat		: Cileuya
TTL		: Kuningan, 9 Maret 1995
Jenis Kelamin	: Laki-laki
---------------------------------------------
Nama		: Dodi Riyanto
Alamat		: Cileuya
TTL		: Kuningan, 26 Januari 1995
Jenis Kelamin	: Laki-laki
---------------------------------------------

+---------------------------------------------------------------------------------+
|                                   Output                                        |
+----------------+----------------+------------------------------+----------------+
|Nama            |Alamat          |Tempat Tanggal Lahir          |Jenis Kelamin   |
+----------------+----------------+------------------------------+----------------+
|Eka Putra       |Cileuya         |Kuningan, 14 November 1995    |Laki-laki       |
+----------------+----------------+------------------------------+----------------+
|Suryana         |Cileuya         |Kuningan, 9 Maret 1995        |Laki-laki       |
+----------------+----------------+------------------------------+----------------+
|Dodi Riyanto    |Cileuya         |Kuningan, 26 Januari 1995     |Laki-laki       |
+----------------+----------------+------------------------------+----------------+
{% endhighlight %}

## Data Buku
{% highlight c %}
#include<iostream>
#include<iomanip>
using namespace std;
int main () {
	struct dbuku {
		char kbuku[99];
		char nbuku[99];
		char tt[99];
		char pg[99];
		char hrg[99];
	};
	dbuku dbk [3];
	cout<<"---------------------------------------------"<<endl;
	cout<<"Input (3 Data)"<<endl;
	cout<<"---------------------------------------------"<<endl;
	for (int i=0; i<3; i++) {
		cout<<"Kode Buku	: "; cin.getline(dbk[i].kbuku, 99);
		cout<<"Nama Buku	: "; cin.getline(dbk[i].nbuku, 99);
		cout<<"Tahun Terbit	: "; cin.getline(dbk[i].tt, 99);
		cout<<"Pengarang	: "; cin.getline(dbk[i].pg, 99);
		cout<<"Harga		: "; cin.getline(dbk[i].hrg, 99);
		cout<<"---------------------------------------------"<<endl;
	}
	cout<<"\n\n\n";
	cout<<setfill('-')
		<<setw(1)<<"+"<<setw(75)<<"-"<<setw(1)<<"+"<<endl;
	cout<<setfill(' ')
		<<setw(1)<<"|"<<setw(38)<<"Output"<<setw(38)<<"|"<<endl;
	cout<<setfill('-')
		<<setw(1)<<"+"<<setw(10)<<"-"
		<<setw(1)<<"+"<<setw(23)<<"-"
		<<setw(1)<<"+"<<setw(14)<<"-"
		<<setw(1)<<"+"<<setw(14)<<"-"
		<<setw(1)<<"+"<<setw(10)<<"-"
		<<setw(1)<<"+"<<endl;
	cout<<setfill(' ')
		<<setw(1)<<"|"<<setw(10)<<left<<"Kode Buku"
		<<setw(1)<<"|"<<setw(23)<<left<<"Nama Buku"
		<<setw(1)<<"|"<<setw(14)<<left<<"Tahun Terbit"
		<<setw(1)<<"|"<<setw(14)<<left<<"Pengarang"
		<<setw(1)<<"|"<<setw(10)<<left<<"Harga"
		<<setw(1)<<"|"<<endl;
	cout<<setfill('-')
		<<setw(1)<<"+"<<setw(10)<<"-"
		<<setw(1)<<"+"<<setw(23)<<"-"
		<<setw(1)<<"+"<<setw(14)<<"-"
		<<setw(1)<<"+"<<setw(14)<<"-"
		<<setw(1)<<"+"<<setw(10)<<"-"
		<<setw(1)<<"+"<< endl;
	for (int i=0; i<3; i++) {
		cout<<setfill(' ')
			<<setw(1)<<"|"<<setw(10)<<left<<dbk[i].kbuku
			<<setw(1)<<"|"<<setw(23)<<left<<dbk[i].nbuku
			<<setw(1)<<"|"<<setw(14)<<left<<dbk[i].tt
			<<setw(1)<<"|"<<setw(14)<<left<<dbk[i].pg
			<<setw(1)<<"|"<<setw(10)<<left<<dbk[i].hrg
			<<setw(1)<<"|"<<endl;
		cout<<setfill('-')
			<<setw(1)<<"+"<<setw(10)<<"-"
			<<setw(1)<<"+"<<setw(23)<<"-"
			<<setw(1)<<"+"<<setw(14)<<"-"
			<<setw(1)<<"+"<<setw(14)<<"-"
			<<setw(1)<<"+"<<setw(10)<<"-"
			<<setw(1)<<"+"<<endl;
	}
}
{% endhighlight %}
{% highlight html %}
[~]-> cd tugas/
[~/tugas]-> ./struct2
---------------------------------------------
Input (3 Data)
---------------------------------------------
Kode Buku	: B001
Nama Buku	: Debian
Tahun Terbit	: 2015
Pengarang	: Eka Putra
Harga		: IDR 50K       
---------------------------------------------
Kode Buku	: B002
Nama Buku	: Slackware
Tahun Terbit	: 2015
Pengarang	: Suryana
Harga		: IDR 50K
---------------------------------------------
Kode Buku	: B003
Nama Buku	: Gentoo
Tahun Terbit	: 2015
Pengarang	: Dodi Riyanto
Harga		: IDR 50K
---------------------------------------------

+---------------------------------------------------------------------------+
|                                Output                                     |
+----------+-----------------------+--------------+--------------+----------+
|Kode Buku |Nama Buku              |Tahun Terbit  |Pengarang     |Harga     |
+----------+-----------------------+--------------+--------------+----------+
|B001      |Debian                 |2015          |Eka Putra     |IDR 50K   |
+----------+-----------------------+--------------+--------------+----------+
|B002      |Slackware              |2015          |Suryana       |IDR 50K   |
+----------+-----------------------+--------------+--------------+----------+
|B003      |Gentoo                 |2015          |Dodi Riyanto  |IDR 50K   |
+----------+-----------------------+--------------+--------------+----------+
{% endhighlight %}

Happy Programming!
