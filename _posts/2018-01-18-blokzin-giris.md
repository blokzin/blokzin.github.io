---
layout: splash
title:  "Blokzin'e hoşgeldiniz"
date:   2018-01-18
author: Kutay B. Sezginel
---

Blokzin'e hoşgeldiniz. Blokzin blokzinciri ve kriptoparalar üzerine açık kaynaklı
ve ücretsiz olarak internet üzerinden yayınlanan bir dergi hatta bir fanzindir.
Blokzin'in amacı blokzinciri teknolojisi hakkında tarafsız ve sansürsüz bilgi vermek,
bu teknolojinin Türkiye'de yayılmasına ve gelişmesine katkı sağlamaktır.

İlk sayı için öncelikle blokzinciri ve kriptoparalara kısa bir giriş yapmak istiyorum.
Kriptopara ve blokzinciri ilk kez 2008 yılında Satoshi Nakamoto takma adlı bir kişi ya da grup tarafından kaleme alınan Bitoin makalesi ile ortaya çıkıyor.
Satoshi bu makaleyi internet üzerinden kriptografi forumlarında paylaşıyor fakat başta
pek bir ilgi görmüyor. Daha sonra birkaç kişinin ilgilenmesiyle Bitcoin yazılımı 2009 yılında çalıştırılmaya başlıyor.
Zaman içinde Satoshi ortadan kayboluyor ve yıllar içinde 1 Bitcoin (BTC)
değeri 2017 yılının sonunda 20,000 $'a kadar çıkıyor. Bugün'e kadar Bitcoin'in çıkmasıyla
bu teknolojinin önemini fark edenler çeşitli kriptoparalar üzerinde çalışmaya başlıyorlar.
Bu şekilde *altcoin* olarak tabir edilen alternatif kriptoparalar ortaya çıkmaya başlıyor.
Aynı zamanda Bitcoin içindeki fikir ayrılıkları da Bitcoin'in kendi içinde farklı versiyonları (*fork*)
çıkıyor. Şu an itibariyle Bitcoin'in iki ana versiyonu bulunmakta: Bitcoin Core (BTC) ve Bitcoin Cash (BCH).

### Bitcoin Versiyonları ve Aralarındaki Farklar

#### Bitcoin Core (BTC)
Bitcoin Core blok boyutunu 1 MB olarak sınırlamaya karar vermiştir.
Blok boyutunun birim zamanda yapılabilecek işlem sayısının kısıtlanmasına sebep olmaktadır.
Blok arası zaman 10 dk olduğu için ve her bloğun boyutu sınırlı olduğu için her 10 dk
arayla onaylanacak (blokzincirine eklenecek) işlemlerin sayını yaklaşık 1000-2000 arasındadır.
Bu da yaklaşık saniyede 3 işleme denk gelmektedir.
Bitcoin'in kredi kartı şirketleri (VISA, MasterCard gibi) kadar işlemi onaylayabilmesi için
saniyede 20,000 işlem seviyelerine gelmesi gerekmektedir.

Bitcoin Core takımı bu işlem kapasitesinin artırılması için farklı çözümler sunmaktadır.
Bunlardan biri SegWit (segregated witness - ayrılmış tanık) işlem boyutunu küçülterek
1 MB'lık bir bloğa sığdırılabilecek toplam işlem sayısını artırmayı amaçlamaktadır.
Bir diğeri Lightning Network (Yıldırım Ağı) ise belirlenmiş adresler arasında blokzinciri
dışı işlemler yapılmasını sağlamaktadır. Bu şekilde sık para transferi yapan adresler arasında
ekstra bir işlem ağı kurulmaktadır ve istendiği zaman adresler arası hesap kapatılarak toplam
işlem blokzincirine eklenmektedir. Sonuç olarak blokzincirine eklenmesi gereken toplam işlem
sayısının azaltılması amaçlanmaktadır.

**Peki neden blok boyutu 1 MB olarak sınırlandırılmak zorunda?**
Bitcoin Core'a göre blok boyutunun artırılması blokzincirinin boyutunun fazla büyümesine ve ortalama
bir bilgisayar ve internet ağı kullanarak Bitcoin yazılımının çalıştırılmasının zorlaşıcağını düşünmektedir.
Blokzincirinin boyutunun artmasıyla yazılım için gerekli hafıza ve internet hızının artmasıyla masraf artacaktır.
Bitcoin Core bu artan masrafın Bitcoin yazılımının çoğunlukla madenciler tarafından kullanılacağını düşünmektedir.
Bu sebepler blok boyutunun büyültülmesinin Bitcoin'in daha merkezi bir hale gelmesine yol açacağına inanmaktadır.


Son zamanlarda blok boyutu sınırının sabit kalması işlem ücretlerinin çok artmasına ve işlemlerin çok uzun sürmesine sebep olmuştur.
Bu yazının tarihinde ortalama işlem ücreti 23 $ civarında ve işlemlerin onaylanması 1 aya kadar sürmektedir.
Bu da haliyle Bitcoin ile işlem yapmayı fazlasıyla olumsuz bir duruma sokmuştur.


#### Bitcoin Cash (BCH)
Bitcoin Cash 1 Ağustos 2017 yılında Bitcoin'in ayrılmasıyla ortaya çıkmıştır.
Bitcoin Cash blok boyutu sınırını artırarak 8 MB'a çıkarmıştır.
Aynı zamanda SegWit ve RBF (Replace by Fee - İşlemi Ücretle Değiştirme) kullanmamaktadır.

**İşlemi Ücretle Değiştirme (Replace by Fee - RBF):** İşlem ücreti değiştirme yapılan bir işlemin ücretinin ve adresinin onaylanmadan değiştirilebilmesine izin vermektedir.
Bu şekilde işlem ücreti artırılarak işlemin madenciler tarafından daha hızlı bir şekilde
onaylanması sağlanabilmektedir.
Fakat aynı zamanda RBF ile onlaylanmamış işlemlerin
değiştirilebilmesi işlem hızını sınırlamaktadır.
Blok arası zaman ortalama 10 dk olduğu için işlemlerin güvenilir olması için en az 10 dk beklenilmesi gerekmektedir.
Bitcoin Cash RBF kullanmayarak yapılan işlemlerin sonradan değiştirilmesini engellemiştir.
Bu şekilde işlemler blokzincirine eklenmese bile değiştirilmesi engellendiği için
daha güvenilirdir.
Aynı zamanda küçük işlemlerin saniyeler içinde yapılabilmesi amaçlanmaktadır.
Blokzincirine eklenmemiş işlemlere 0-onay (0-conf) işlemler denmektedir.
Her işlemin blokzincirine eklendiği blok itibariyle onay sayısı artmaktadır.
Yani bir işlem blokzincirine işlendiği anda 1-onay olmaktadır ve ondan sonra eklenen
her blok ile onay sayısı artmaktadır (2-onay, 3-onay, ...).
Bir işlemin onay sayısı ne kadar fazlaysa o işlem o kadar güvenilirdir.
RBF 0-onay işlemlerin güvenirliğini yok ettiği ve işlem hızını azalttığı için Bitcoin Cash tarafından kullanılmamaktadır.

Bitcoin Cash Satoshi Nakamoto'nun sunduğu Bitcoin fikrini savunmaktadır.
Bitcoin'in temel amacının kişiler arası ucuz ve hızlı işlem yapılmasını sağlamak olduğunu düşünmektedir.
Bitcoin'in bir yatırım amacı olarak kullanılmasını ikincil bir amaç olarak görmektedir.
Bu yazının tarihinde ortalama işlem ücreti 0.20 $ civarındadır.
