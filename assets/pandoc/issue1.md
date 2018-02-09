---
layout: splash
title:  "Bitcoin'in şifreleme yöntemine giriş"
date:   2017-12-20
author: Kutay B. Sezginel
mainfont: AvenirNextLTPro-Regular.otf
mainfontoptions:
- BoldFont=AvenirNextLTPro-Bold.otf
- ItalicFont=AvenirNextLTPro-It.otf
- BoldItalicFont=AvenirNextLTPro-BoldCnIt.otf
---

Bitcoin'in ve tüm kriptoparaların çalışması için kriptografik (şifreli) fonksiyonların önemi çok büyüktür.
Peki ama neden kriptografi bu iş için bu kadar gerekli? Bu yazıda biraz bundan bahsedeceğiz...

Kriptografi'ye giriş
====================

Tarih boyunca kriptografi bilgiyi korumak ve şifreli mesajlar yollamak için kullanılmıştır.
Mesajlar karşı tarafın çözmeyi bildiği bir yöntemle sistematik bir şekilde *karıştırılarak* gönderilmiştir.
Sistemi bilmeyen biri için mesaj karman çorman bir şey olarak gözükürken şifreleme sistemini bilenler
için savaş taktikleri gibi çok değerli şeyler içeriyor olabilir. Bilgisayarların icadı ve şifrelemenin
kolaylaşmasıyla kriptograki sadece gizli mesaj yollamaktan çok daha fazlası için kullanılmaya başlamıştır.
Mesela kullanıcı adı ve parola isteyen sitelere giriş yapmak ya da lisanslı bilgisayar programları
kullanmak buna birkaç örnek olabilir. Modern kriptografi gizli mesaj yollamaya ek olarak, bilgi doğrulama
(kriptografik *hash* fonksiyonları sayesinde) ve kimlik doğrulama (dijital imzalar sayesinde) için çok
yaygın olarak kullanılmaktadır. Bunları anlatmadan önce modern kriptografinin en önemli araçlarından
biri olan tek yönlü fonksiyonlardan bahsedelim.

Tek Yönlü Fonksiyonlar
----------------------
Tek yönlü fonksiyonlar bir veriyi kullanarak sonucu elde etmenin kolay olduğu fakat sonucu kullanarak
giriş verisini bulmanın zor olduğu matematiksel fonksiyonlardır.
Bu tip fonksiyonların en meşhur örneklerinden biri **asal çarpanlara ayırma**dır.

### Asal Çarpanlara Ayırma (Integer Factorization)

Asal çarpanlara ayırma basitçe verilen bir tamsayının asal çarpanlarını bulmaktır.
Mesela 30 sayısının asal çarpanları 2, 3 ve 5'tır: `2 x 3 x 5 = 30`.

Küçük sayılar için bunu yapmak belki kolay gözükebilir ama sayılar büyüdükçe bu problemi çözmenin
gittikçe zorlaştığını görebiliriz. Fakat, bu problemin tersi, yani asal çarpanları kullanarak çarpımı
bulma, sadece çarpım işlemi kullanılarak yapılabilir.

Büyük sayılar için asal çarpanları bulmanın en basit yöntemi ise farklı asal sayı kombinasyonlarını
tek tek çarparak denemekten ibarettir. Tahmin edebileceğiniz üzere sayı büyüdükçe bu işlemin süresi
de gittikçe artmaktadır. Örnek olarak, normal bir dizüstü bilgisayar 60-80 haneli bir sayının çarpanlarını
saniyeler içinde bulabilirken 300 haneli bir sayının çarpanlarını bulmak modern bir süperbilgisayar
ile onlarca yıl sürebilir...

Örnek:
```
Asal çarpanlar: (3, 3, 5, 7, 13) -> 3x3x5x7x13 -> Sonuç sayı:     4095             (kolay)
Sonuç sayı:     4095             -> ?????????? -> Asal çarpanlar: (3, 3, 5, 7, 13) (zor)
```
Tek yönlü fonksiyonlara bir diğer örnek de *ayrık logaritmadır (discrete logarithm)*.

Hash Fonksiyonları
------------------

Kriptografik *hash* fonksiyonları herhangi bir veriyi (numara, resim, mesaj ya da tüm Orhun Yazıtları gibi...) kullanarak sabit uzunlukta (128-bit ya da 256-bit sayı) bir sonuç veren tek yönlü matematiksel fonksiyonlardır.

Aşağıda sıkça kullanılan *hash* fonksiyonlarından biri olan MD5 (mesaj düzenleme algoritması, beşinci yineleme) ile bir şifreleme örneği verilmiştir. Görüldüğü üzere bu şifreleme sistemi ile tek bir harf değişikliği bile tamamen farklı bir *hash* elde edildiği için şifreden veriye geri dönüş neredeyse imkansızdır.

```
MD5('blokzin')  =  6e3dfce0376d7e713fd9934b04fe80ff
MD5('blokzon')  =  c7b1cb01593dec30fbf7a340cde9de1d
```

SHA-256

```
SHA-256('blokzin')  =  b3b095f7af26dec743b8771132ca54663368251da2a8e9dcc3ab782526c1dd8a
SHA-256('blokzon')  =  7f9c831c36db813c2a64dac46f83ea36f45e16f2868fb8d4fbff8143adb5aad2
```

RIPEMD160('blokzin') = 974ca6c7ba7d76863bc11ab61b45937e96ed6d42

Bitcoin SHA256 ve RIPEMD160 *hash* fonksiyonlarını kullanmaktadır. Bitcoin madenciliğinin büyük bir
kısmı ise SHA256 hash fonksiyonu kullanılmaktadır.

http://www.md5calc.com/

[MD5](http://www.miraclesalad.com/webtools/md5.php)

[SHA256](http://www.miraclesalad.com/webtools/sha256.php)
