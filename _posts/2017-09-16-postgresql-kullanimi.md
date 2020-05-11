---
layout: post
title: "PostgreSQL Kullanımı"
---

#### 1- Veritabanı oluşturma

```sql
create database ogrencidb
```

#### 2 – Tablo Oluşturma

```sql
CREATE TABLE ogrenci (
ogrno int,
isim VARCHAR,
soyisim VARCHAR,
girisyili int,
dogumtarihi DATE,
dogumyeri VARCHAR,
PRIMARY KEY(ogrno));
```

#### 3- Tabloya veri aktarma

**1. Yöntem:** Dosyadan verileri okuyup tabloya aktarma
Aşağıdaki verileri C’de ogr.txt adında bir dosyaya kopyalayın:

1	Ali	Demir	2007	1994-11-29	Elazig
2	Veli	Bakir	2008	1990-01-29	Malatya
3	Cumali	Tunc	2009	1991-11-01	Sivas
4	Ayse	Bulut	2007	1989-12-11	Istanbul
5	Fatma	Kaya	2008	1991-03-23	Kirikkale

Daha sonra şu SQL komutunu çalıştırın:

```sql
COPY ogrenci FROM 'C:/ogr.txt';
```

**2.Yöntem:** SQL komutları ile veri doldurma
Her bir veri satırı için SQL editöründe aşağıdaki gibi bir komut çalıştırmak gerekir:

```sql
INSERT INTO ogrenci VALUES (1,'Ali','Demir',2007,'1994-11-29','Elazig');
INSERT INTO ogrenci VALUES (2,'Veli','Bakir',2008,'1990-01-29','Malatya');
INSERT INTO ogrenci VALUES (3,'Cumali','Tunc',2009,'1991-11-01','Sivas');
```

Burada dikkat edilecek nokta, VARCHAR ve DATE tipindeki veriler tek tırnak içerisinde yazılırlar.

#### 4- Verileri sorgulama

Tablodaki tüm verileri sorgulama:

```sql
select * from ogrenci
```

Adı Ali olan öğrencileri bul:

```sql
select * from ogrenci where isim='Ali'
```

Adı Ali ve giriş yılı 2007 olan öğrencileri listele:

```sql
select * from ogrenci where isim='Ali' and girisyili=2007
```

Tüm öğrencilerin sadece ad ve soyadlarını listele

```sql
select isim, soyisim from ogrenci
```

Öğrencilerin yaşını bulma:
Öğrencilerin gün olarak yaşını bulabilmek için şu andaki tarihten doğum tarihlerini çıkarmamız gerekir. PostgreSQL şu anki zamanı NOW terimi ile veriyor. Buna göre öğrencilerin yaşlarını now-dogumtarihi ifadesi ile bulabiliriz. Ancak yaşlarını sonuç tablosunda görebilmek için sorgu sonuçlarına yeni bir sanal sütün eklememiz gerekir. Bunu da As anahtar kelimesi ile yapıyoruz:

```sql
select isim, soyisim, ('now'-dogumtarihi)as yas from ogrenci
```

Bu sorguda öğrenci tablosundan isim, soyisim sütünlarını ayrıca öğrenci yaşlarının hesaplanıp bize yas adında bir sütün olarak verilmesini istiyoruz. Sorguyu çalıştırdığımızda isim, soyisim ve öğrencilerin yaşlarının olduğu bir tablo geliyor.

Belirli bir yaştan büyük öğrencilerin listelenmesi
Önceki örnekte öğrencilerin yaşlarını gün olarak bulmuştuk, yıl olarak yaş hesaplamak için gün sonucunu 365’e bölebiliriz. Buna göre mesela öğrencilerin tüm bilgilerini ve yaşlarını şu şekilde listeleyebiliriz:

```sql
select *, ('now'-dogumtarihi)/365 as yas from ogrenci
```

18 yaşından büyük olan öğrencileri sorgulamak için de yine aynı şekilde:

```sql
select * from ogrenci where ('now'-dogumtarihi)/365>18 
```

yazabiliriz.