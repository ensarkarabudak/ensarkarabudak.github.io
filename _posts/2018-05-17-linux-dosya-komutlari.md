---
layout: post
title: "Linux Dosya Komutları"
---

##### ls

Dosya listeleme komutudur.Bir dosya içindeki dosyaları ve alt-alanları listeler.

```
$ ls
```

------

##### more

Dosya içeriklerini görme komutudur.Dosya içerisindeki verileri sayfa sayfa gösterir.Boşluk ile bir sonraki sayfaya,’q’ tuşu ile de çıkabilirsiniz.

```
$ more *dosya_adı*
```

------

##### cp

Dosya kopyalama komutudur.Bir dosyayı belirtilen bir dizine kopyalamayı sağlar.

```
$ cp dosya.txt *dosya_yolu*
```

------

##### rm

Dosya silme komutudur.Dikkatli kullanılmalıdır.Silinen dosya birdaha geri gelmez.

```
$ rm *dosya_adı* | dosya_yolu
```

------

##### mv

Dosya taşıma ve ad değiştirme komutudur.

```
$ mv index.html *taşınıcak_adres_yolu*
```

------

##### chmod

Dosya erişim izni değiştirme komutudur.

```
chmod { a u g o } {+ - } {r w x} dosya_adi
```

------

##### cmp veya diff

Dosya karşılaştırma komutlarıdır.Diff satır satır karşılaştırır.Cmp komutu ise iki dosya arasındaki farkı belirler.

```
cmp [-option] dosya1 dosya2 `
`diff [-option] dosya1 dosya2
```

------

##### file

Dosya tipi sorgulama komutudur.Dosyanın ne tür veri içerdiği hakkında bilgi verir.

```
file *dosya_adı*
```

------

##### grep

Dosya içerisinde bir sözcük arama komutudur.

```
grep [-option] sözcük *dosya_adı*
```

------

##### sort

dosya içerisindeki verileri alfabetik olarak sıralanmasını sağlar.

```
sort *dosya_adı*
```

------

##### wc

Dosyanın satır,sayfa,sözcük sayıları gibi nümerik bilgileri hesaplar ver çıktı olarak basar.

```
wc *dosya_adı*
```

------

##### cat

Dosya içeriğini okuma,yeni dosya oluşturma,dosyalar arasında veri transfer etmek gibi çeşitli amaçla kullanılır.

```
cat *dosya_adı* //Dosya içeriğini gösterir.`
`cat dosya1 dosya2 > dosya3 // Dosyaları birbirine ekleyerek dosya3 üzerine yazar
```

------

##### split

Büyük boyutlu dosyaları parçalayarak küçük boyutlarda saklanmasını sağlar.

```
split *dosya_adı*parcala
```

------

##### cut

Dosya içerisinde bölüm bölüm girilmiş bir dosyada istediğimiz alanlar ile listeleme,kopyalama gibi işlemleri yapmamızı sağlar.

```
cut -cSütuBilgisi *dosya_adı*
```

------

##### paste

Sütunlar halinde bulunan iki dosyayı birleştirerek yeni bir dosyaya yazar.

```
paste dosya1 dosya2 > dosya3
```

------

##### n1

Dosya içindeki her bir satıra numara verir.

```
n1 -v1 *dosya_adı*
```

------

##### uniq

Dosya içindeki tekrarlanan satırları silmek için kullanılır.

```
uniq *dosya_adı* > *sonuc_dosya*
```

------

##### tr

Karakter dönüşümü yapar.Belirli bir karakter üzerinde işlemler yapmak için kullanılır.

```
tr "[a-z]" "[A-Z]" < ilkDosya > sonuc
```

------

##### tail,head

Dosyanın belirli bir kısmını gösterir.Tail sondan,head baştan gösterir.

```
tail *dosya_adı*`
`head *dosya_adı*
```

------

##### ln

Dosyaları ilişkilendirmeyi sağlar.Bir dosyayı başka bir isim ile ilişkilendirip kullanımlasını sağlar.

```
ln /etc/passwd sifre
```

------

##### find

Dosya veya dosyaların hangi alanlarda bulunduğu aramak için kullanılır.

```
find / -name *.txt -print
```