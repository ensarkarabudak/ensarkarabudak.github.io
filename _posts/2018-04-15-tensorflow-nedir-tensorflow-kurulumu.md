---
layout: post
title: "Tensorflow Nedir? Tensorflow Kurulumu"
---

**Tensorflow**,Google’ın açık kaynak kodlu sunduğu makina öğrenmesi kütüphanesidir.Makine öğrenmesinin bir parçası olan [derin öğrenme](http://ensarkarabudak.com/yapay-zeka/derin-ogrenme-nedir-deep-learning-nedir/) için kullanılıyor.

Bu kurulum **Ubuntu 16.04,Ubuntu 17.04** veya **debian** tabanlı çoğu dağıtım için uygundur.ben bu işletim sistelerine **TensorFlow’u** kurmaya anlatacağım.

##### Neden TensorFlow?

TensorFlow açık kaynak kodlu olmasının yanı sıra,arkasında **Google** gibi bir şirketin bulunması ve **Python**programlama dilini kullandığı için oldukça tercih edilir.Birçok makine öğrenmesi kütüphanesi ile geliştirilen projeler genelde Python kullanarak geliştirilir.Python,**hızlı geliştirme** olanağı ve topluluk desteği yüzünden oldukça tercih edilme nedenleri arasında.

Python kurulumunu gerçekleştirelim ve güncelleme yapalım.(Python kurulu olanlar bu adımı atlayabilir)

```
sudo apt-get install python3-pip python3-dev -ysudo pip3 install --upgrade pip
```

> Eğer harici bir Nvidia ekran kartınız varsa GPU destekli olanları yoksa CPU versiyonunu tercih ediniz. Derin öğrenmede daha iyi sonuçlar almak için çok büyük veri setleri kullanıldığı için GPU destekli kullanmanız şiddetle önerilir.

```
$ sudo pip3 install tensorflow -y // Sadece CPU destekli kurulum için
```

GPU destekli kurulum için CUDA kurulumu gereklidir.Eğer ekran kartı driverı kurulu değilse aşağıdaki kodları yazarak kurulumu yapın.

```
sudo add-apt-repository ppa:graphics-drivers/ppa -ysudo apt-get update
```

TensorFlow’u CUDA desteği ile çalıştırabilmek için 3.0 ve üzeri bir **Compute Capability** değerine sahip bir ekran kartına sahip olmanız gerekmektedir.[Bu listeden](https://developer.nvidia.com/cuda-gpus) bakarak kontrol ediniz.

[Buraya tıklayarak](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1604&target_type=deblocal) 1.2Gb dosya boyutundaki CUDA Toolkit 9.1 dosyasını indirin.

Daha sonra indirdiğiniz dosya yoluna gidip terminalden aşağıdaki komutları yazın.

```
sudo dpkg -i cuda-repo-ubuntu1604-9-1-local_9.1.85-1_amd64.debsudo apt-get updatesudo apt-get install cuda
```

CUDA kurulumunun son aşaması olarak PATH sistem değişkenini tanımlayalım.

```
export PATH=/usr/local/cuda-9.1/bin${PATH:+:${PATH}}
```

cuDNN adında bir kütüphane daha mevcut. cuDNN CUDA’nın derin öğrenmeye göre optimizasyon edilmiş bir versiyonudur.Çok katmanlı yapay sinir ağlarındaki karmaşık katmanların performanslı bir şekilde çalışmasını sağlar. cuDNN’ı kullanabilmek için şuradan Nvidia geliştirici hesabı oluşturmanız gerekiyor. Ardından cuDNN’ı [şuradan](https://developer.nvidia.com/compute/machine-learning/cudnn/secure/v5.1/prod_20161219/8.0/libcudnn5-dev_5.1.10-1%2Bcuda8.0_ppc64el-deb) indirebilirsiniz. İndirdiğimiz debian paketini GDebi ile kurabilirsiniz.

Ardından TensorFlow’un GPU versiyonunu kuralım.

```
sudo pip3 install tensorflow-gpu -y //pip3 kurulu olanlar içinsudo pip install tensorflow-gpu -y
```

Yeni bir sürüm çıkığında versiyonu son sürüme güncellemek için aşağıdaki adımları uygulayın;

```
pip install tensorflow-gpu (Python 2.7 için, GPU destekli)pip3 install tensorflow-gpu (Python 3.x için, GPU destekli)
```

> Not:Pip3 kurulu olmayanlar pip olarak deneyin eğer çalışmazsa aşağıdaki komutla pip kurulumunu yapın.

Pip kurulumu:

```
sudo apt-get install python-pip python-dev
```

NVIDIA CUDA Profil Araçları Arabirimi ve CUDA uygulamalarını için gerekli araçların oluşturulmasını ve profil oluşturmayı sağlayan libcupti-dev kütüphanesini yükleyin.

```
sudo apt-get install libcupti-dev
```

Kurulum başarıyla tamamlandı aşağıdaki komutu çalıştırın:

```
python3
```

Ardından Tensorflow ile basit bir “Merhaba Dünya” uygulaması yapalım.

```
>>> import tensorflow as tf>>> txtHello = tf.constant('Merhaba Dünya')>>> sess = tf.Session()>>> print(sess.run(txtHello))
```



Eğer çıktısında **“Merhaba Dünya”** alıyorsanız kurulum tamamlanmıştır.

##### UNUTMAYIN!

Tensorflow’un çalışması için aşağıdaki şartlar gerekmektedir:

1.CUDA Toolkit 9.1(Detaylar ve kurum için [tıkayın.](https://developer.nvidia.com/cuda-downloads))

2.cuDNN(Detaylar ve kurulum için [tıklayın.](https://developer.nvidia.com/cudnn))

3.CUDA Hesaplama kapasitesi 3.0 ve üzeri GPU kartı.(Detaylar ve kurum için [tıklayın.](https://developer.nvidia.com/cuda-gpus))