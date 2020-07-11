---
layout: post
title: "MYSQL Komutları ve Kullanımı"
tags:
  - mysql
  - database
---

MYSQL komutları ve kullanımı,php mysql komutlarını ve Mysql komutlarını örneklerle beraber açıklamaya çalışacağım.Mysql komutları ve kodlarının ne anlamlara geldiklerini detaylı
bir şekilde bakacağız.

### MySQL Komutlarına Giriş

MySQL tarafında kullanılan temel SQL komutlarını kullanılarak oluşturulmuştur.Genel olarak diğer veritabanlarının da kullandığı komutları içerir.

### Veritabanı ile bağlantı kurma

Local sunucuda kurulu olan MySQL komut satırı aracılığı ile bağlanabilmek için aşağıdaki komutu kullanmanız yeterlidir.

```bash
mysql -u root -h 127.0.0.1
```

Local IP’niz değişik olabilir kendi Ip adresini yazmanız gerekir.Ip ile uğraşmak istemiyorsanız aşağıdaki komutlada bağlanabilirsiniz.

```bash
mysql -u root -p
```

### Oluşturulan Veritabanlarını Listeleme

Aşağıdaki komut aracılığı ile veritabanındaki mevcut veritabalarını listeleyebilirsiniz.

```bash
SHOW DATABASES;
```

### Tablo Detaylandırma

Veritabanı içerisindeki tabloları ve bu tablolara ait olan değerlerin tanımlamalarını göstermektedir.



```bash
DESCRIBE [tabloadı];
```

### Tabloya Veri Ekleme

Veritabanı içerisinde bulunan herhangi bir tabloya veri girişine imkan tanır.

```sql
INSERT INTO [tabloadı] ([kolon], [birsonrakikolon]) VALUES ('[deger1]', [deger2]');
```

### Tabloya kolon Ekleme

Veritabanı içerisinde bulunan ve seçtiğiniz tabloya kolon eklenilmesine imkan verir.

```sql
ALTER TABLE [tabloadı] ADD COLUMN [kolon] VARCHAR(120);
```

Veritabanı içerisinde benzersiz kimlikli ve otomatik artan kolonlar oluşturmanıza imkan tanır.

```sql
ALTER TABLE [table] ADD COLUMN [column] int NOT NULL AUTO_INCREMENT PRIMARY KEY;
```