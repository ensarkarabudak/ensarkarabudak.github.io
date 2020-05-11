---
layout: post
title: "SQL Komutları,SQL Sorguları,SQL Ders Notları"
tags:
  - sql
  - bilgisayar bilimleri
  - database
---

SQL Komutları,SQL Sorguları,SQL Ders Notları,SQL nedir?,SQL komutları ve örneklerini inceleyeceğiz.

Temel SQL komutları genel hatlarıyla bir bakalım.

**CREATE DATABASE**: Yeni bir veritabanı üretir
**CREATE TABLE**: Yeni bir tablo üretir
**INSERT INTO**: Veritabanına yeni kayıt ekler
**SELECT FROM**: Veritabanından bilgi okumaya yarar
**WHERE**: Yapılan işlemin etkileyeceği sütunları belirtir
**ORDER BY**: Seçim işleminde sıralama veya tersten sıralama yapar
**UPDATE SET**: Veritabanında değişiklik yapar
**DELETE FROM**: Bilgi siler
**SHOW TABLE**: Tabloların listesini verir
**DESCRIBE**: Tablo sütunlarının adını yazar
**DROP DATABASE**: Veritabanını komple siler
**DROP TABLE**: Tabloyu komple siler
**TRUNCATE TABLE**: Tablodaki bilgileri siler, Tablo ayarlarını sıfırlar
**ALTER DATABASE**: Veri tabanının öz niteliklerini değiştirir.
**ALTER TABLE**: Tabloya alan ekleme, tablodaki alanı düzenleme ve silme işlemlerini yapar.
**ALTER VIEW**: Görünüm değiştirmede kullanılır.
**CREATE DATABASE**: Yeni bir veritabanı oluşturur.
**CREATE INDEX**: Yeni bir index oluşturur.
**CREATE TABLE**: Yeni bir tablo oluşturur.
**DELETE**: Belirtilen tablodan yeri WHERE deyimi ile saptanan satırı siler.
**DROP DATABASE**: Belirtilen veritabanını siler.
**DROP INDEX**: Belirtilen indexi siler.
**DROP TABLE**: Belirtilen tabloyu siler.
**INSERT**: Tabloya Yeni bir satır ekler.
**RENAME TABLE**: Var olan tablonun adını değiştirir.
**SELECT**: Veri tabanındaki tablonun tamamını yada WHERE ile belirtilen alanı gösterir.

## Tablodaki Kayıtları Gösterme

Veritabanı içerisinde bulunan tablolar içerisindeki kayıtları ekrana getirir.

```
SELECT * FROM [tabloadı];
```

Veritabanında bulunan tablolar içerisinde ki kayıtları parça parça ekrana getirirmenize olanak sağlar

```
SELECT [kolon], [birsonrakikolon] FROM [tabloadı];
```

## Tablodaki Kayıtların Sayısını Gösterme

Tablo içerisinde belirtilen kolona ait kaç adet kayıt olduğunu gösterir

```
SELECT COUNT([kolon]) FROM [tabloadı];
```

## Tablodaki Kayıtları Sayma ve gruplandırılmış kayıtları seçme

Kayıtları sayar ve gruplandırılmış bir şekilde kayıtları gösterir.

```
SELECT *, (SELECT COUNT([kolon]) FROM [tabloadı]) AS count FROM [tabloadı] GROUP BY [kolon];
```

## İçeren kayıtları getir

```
SELECT * FROM [tabloadı] WHERE [kolon] LIKE '%[deger]%';
```

## [deger] ile başlayanları getir

```
SELECT * FROM [tabloadı] WHERE [kolon] LIKE '[deger]%';
```

## deg ile başlayan ve er ile bitenleri getir

```
SELECT * FROM [tabloadı] WHERE [kolon] LIKE '[deg_er]';
```

## Bir Aralık Seçme

```
SELECT * FROM [tabloadı] WHERE [kolon] BETWEEN [deger1] and [deger2];
```

## Özel Sırayla ve Limitli Bir Şekilde Seçim

```
SELECT * FROM [tabloadı] WHERE [kolon] ORDER BY [kolon] ASC LIMIT [deger];
```

## Kayıt Güncelleme

```
UPDATE [tabloadı] SET [kolon] = '[guncellenencek-deger]' WHERE [kolon] = [deger];
```

## Kayıt Silme

```
DELETE FROM [tabloadı] WHERE [kolon] = [deger];
```

## Tablonun kolonunu silme

```
ALTER TABLE [tabloadı] DROP COLUMN [kolon];
```

## Tablo silme

```
DROP TABLE [tabloadı];
```

## Veritabanı Silme

```bash
DROP DATABASE [veritabanıadı];
```

## Özel Kolon isimleri tanımlama

```bash
SELECT [kolon] AS [özel-kolon-adı] FROM [tabloadı];
```

## Veritabanının Yedeğini Alma

```bash
mysqldump -u [kullanıcıadı] -p [veritabanıadı] > yedekadi.sql
```

## Veritabanının Yedeğini Yükleme

```bash
mysql -u [kullanıcıadı] -p -h localhost [veritabanıadı] < yedekadi.sql
```

# Matematiksel Fonksiyonlar

## Yineleme Olmadan Seçim

```sql
SELECT distinct name, email, acception FROM owners WHERE acception = 1 AND date >= 2015-01-01 00:00:00
```



## Kayıtların Toplam Sayısını Hesaplama

```sql
SELECT SUM([kolon]) FROM [tabloadı];
```

## Toplam [sütun] sayısını alma ve grublama [ara kolonlu]

```sql
SELECT [arakolon], SUM([kolon]) FROM [tablo] GROUP BY [arakolon];
```

## Kolondaki en büyük değer

```sql
SELECT MAX([kolon]) FROM [tabloadı];
```

## Kolondaki en küçük değer

```sql
SELECT MIN([kolon]) FROM [tabloadı];
```

## Kolon Ortalaması

```sql
SELECT AVG([kolon]) FROM [tabloadı];
```

## Yuvarlanmış ortalama değer ile gruplama

```sql
SELECT [carakolon], ROUND(AVG([kolon]), 2) FROM [tabloadı] GROUP BY [arakolon];
```

# #Kullanıcı Komutları

## Kullanıcı Oluşturma

```sql
CREATE USER 'kullanıcı_adı'@'localhost' IDENTIFIED BY 'şifresi';
```

## Kullanıcı Yetkilendirme

```sql
GRANT ALL PRIVILEGES ON * . * TO 'kullanıcı_adi'@'localhost';
```

veya

```sql
GRANT ALL ON veritabanı_adı.* TO 'kullanıcı_adı'@'localhost';
```