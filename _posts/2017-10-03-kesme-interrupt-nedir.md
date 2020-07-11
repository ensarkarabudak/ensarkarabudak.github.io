---
layout: post
title: "Kesme(Interrupt) Nedir?"
tags:
  - mikroişlemci
  - bilgisayar bilimleri
---

Kesme,mikrodenetleyicinin işlemekte olduğu **program kodlarını** bırakıp başka bir
işlevi yerine getirmesine neden olan,yazılım ve donanımsal olaydır.

Kese işlemini anlayabilmek için günlük hayatımızdan bir **örnek** verelim.
Örneğin,DVD’de bir film seyrediyorsunuz ve telefon çaldı.Telefonun cevaplanması filmden daha
öncelikli bir olaylduğu için filmi durdurur,telefona bakarsınız,sonra filme kaldığı yerden devam edersiniz.İşte kesme de böyle bir şeydir.

Ana program çalışırken,kesme kaynaklarından herhangi biri bir kesmeye sebep oluyorsa program normal çalışmasını durdurur,kesme alt programına dallanarak buradaki komutları işler,**kesme alt programı** bitince ana programda kaldığı yere geri döner.