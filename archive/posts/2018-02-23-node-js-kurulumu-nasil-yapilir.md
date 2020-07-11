---
layout: post
title: "Node.js Kurulumu Nasıl Yapılır?"
tags:
  - nodejs
  - kurulum
---

## Node.js Nedir?

**Node.js**,kullanıcıların hızlı ve kolay bir şekilde server tarafıda dahil olmak üzere başta web uygulamaları olmak üzere birçok uygulamada genel amaçlı program yazılabilen bir **JavaScript** platformudur.

Şimdi Linux üzere Node.js’in nasıl kurulacağına geçelim.

Ubuntu,Mint,Debian,Elementary OS,Kali Linux gibi dağıtımlarda varsayılan depolarda hali hazırda zaten **Node.js deposu** bulunur.Şuan 9.5.0 versiyonu mevcut.Bu sürümü kurmak için paket yöneticisi kullanarak kurmamız yeterli olacaktır.İlk başta paketlerimizi güncellememiz gerekiyor.Ardından **Node.js**‘i kurabiliriz.

```bash
$ sudo apt-get update
$ sudo apt-get install nodejs
```

Node.js için olmassa olmazlardan npm kurulumuda yapalım.

```
$ sudo apt-get install npm
```

Npm sayesinde Node.js için modülleri veya paketleri kolayca yükleyebiliriz.

Yükleme işlemimizin başarıyla tamamlandığı anlamamız için şu komutu girelim.

```
$ nodejs -v$ npm -v
```

Size çıktı olarak yüklediğiniz sürümü veriyorsa başarılı bir şekilde kurmuşsunuz demektir.

### PPA(Personal Package Archive) Kullanarak Kurulumu

Alternatif Çözümlerden ikincisi PPA ekleyerek Node.js kurulumudur.Bu sayede **en güncel Node.js** sürümünü depodan yükleyebiliriz.

Node.js **v4.x** 2018 Nisan ayına kadar desteklenmektedir.
Node.js **v6.x** 2019 Nisan ayına kadar desteklenmektedir.
Node.js **v8.x** yani mevcut LTS sürümü 2019 Aralık ayına kadar desteklenecek.

Şimdi Kuruluma başlayalım.İlk olarak **Home** dizinine geçelim.Ardından Node.js’i indirelim.

```bash
$ cd ~$ curl -sL https://deb.nodesource.com/setup_8.x -o nodesource_setup.sh
```

İndirdiğimiz script’i çalıştıralım.

```
$ sudo bash nodesource_setup.sh
```

PPA lokal paket deponuza ekledik ve bundan sonra otomatik güncellenecektir.Daha sonrasında aşağıdaki gibi **Node.js** paketini kurabiliriz.

```
$ sudo apt-get install nodejs
```

Ardından npm paketlerinin de sorun çıkartmaması için build-essential paketini yükleyelim.

```
$ sudo apt-get install build-essential
```

### NVM Kullanarak Kurulum

Diğer bir kurulum yöntemi ise NVM’dir.**Node.js** sürüm yöneticisi(node.js version manager) olarak adlandırılan özel tasarlanmış bir araçtır.

Nvm kullanarak Node.js versiyonlarında çoklu kurulum ve versiyonlar arası geçiş yapabilirsiniz.
NVM sürümlerin daha kolay kontrol edebilme imkanı sağlayacaktır.
Başlangıç olarak Ubuntu paketlerimizi güncellememiz ve nvm paketlerimizi kaynak koddan derleyebilmek için gerekli ön bileşenleri kurmamız gerekmektedir.

```
$ sudo apt-get update$ sudo apt-get install build-essential libssl-dev
```

Şimdi NVM’i kuracağız siz güncelle sürüme bakarak uygun yeri değiştirebilirsiniz.

```
$ curl -sL https://raw.githubusercontent.com/creationix/nvm/v0.31.0/install.sh -o install_nvm.sh
```

Çalıştıralım

```
$ bash install_nvm.sh
```

Yazılımı, adresindeki ev dizininizin bir alt dizinine yükleyecektir **~/.nvm.** Ayrıca, **~/.profile** dosyayı kullanmak için dosyanıza gerekli satırları ekleyecektir .

```
$ source ~/.profile
```

Bu işlem sonunda **nvm kurulumu tamamlanmıştır**.Bu işlemden sonra kullanabileceğiniz Node.js sürümlerini listeleyerek kurulumları tamamlayabilirsiniz.

Uygun Node.js sürümlerini **listelemek** için:

```
nvm ls-remote
```

Şöyle bir çıktı alacaksınız:

```
...v8.5.0v8.6.0v8.7.0v8.8.0v8.8.1v8.9.0v8.9.1v8.9.2v8.9.3-> v8.9.4 (Latest LTS: Carbon)
```

Buradan istediğiniz versiyonu şu şekilde kurabilirsiniz.Örneğin ben 8.9.4’ü kurdum.

```
nvm install 8.9.4
```

Kullanmak istediğiniz sürümüde şu şekilde yazarak yapabilirsiniz:

```
nvm use 8.9.4
```

Birden fazla Node.js sürümünüz varsa, aşağıdakileri yazarak neyin yüklü olduğunu görebilirsiniz:

```
nvm ls
```

Sürümlerden birini varsayılan yapmak isterseniz şunu yazabilirsiniz:

```
nvm alias default 8.9.4
```

ya da

```
nvm use default
```

### Node.js Kaldırma

Paket yöneticisiyle kolaylıkla kaldırabilirsiniz.

```bash
sudo apt-get remove nodejs
```

Eğer yapılandırma dosyalarını da silmek istiyorsanız şöyle yapmalısınız.

```
sudo apt-get purge nodejs
```

Bu, paketi kaldırır ve onunla ilişkili yapılandırma dosyalarını kaldırır.
Son adım olarak, kaldırılan pakette otomatik olarak yüklenen kullanılmayan paketleri kaldırabilirsiniz.



```
sudo apt-get autoremove
```

**İkinci kaldırma yöntemini** NVM ile yapabilirsiniz.

```
nvm current
```

Yazarak etkin sürümü öğrenin ardından pasif yapmamız gerekli.

```
nvm deactivate
```

Daha sonra öğrendiğimiz **mevut sürümü** sona yazarak kaldırabilirsiniz.

```bash
nvm uninstall node_version
```

Node.js kurulumu bu şekildeydi herkese iyi çalışmalar..