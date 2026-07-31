# Overselling Prevention

## 1. Amaç

Bu doküman, OrderSync sisteminde overselling (aşırı satış) riskinin nasıl azaltılacağını tanımlar.  
Amaç; stok yetersizken satış yapılmasını engellemek veya en aza indirmektir.

---

## 2. Overselling Nedir?

Overselling, bir üründen stokta bulunan miktardan daha fazla satış yapılmasıdır.

**Örnek:**
- Güncel stok: 3
- Kanal A’dan 2 sipariş
- Kanal B’den 2 sipariş
- Toplam satış: 4  
→ 1 adet fazla satılmış olur.

Bu durum:
- Müşteri memnuniyetsizliği
- İptal / iade artışı
- Operasyonel yük
- Güven kaybı

yaratır.

---

## 3. Temel Prensip

OrderSync’te overselling önleme yaklaşımı şudur:

> Satışa konu olan her işlemde, sistem satılabilir stok miktarını kontrol eder.  
> Stok yetersizse işlem engellenir veya kullanıcı uyarılır.

---

## 4. MVP Yaklaşımı (İlk Versiyon)

### 4.1. Kullanılacak Model
- Tek stok havuzu (tüm kanallar aynı stoku kullanır)
- Sipariş onay anında stok kontrolü
- Onay ile birlikte stok düşümü
- İptal veya iade olursa stokun geri eklenmesi

### 4.2. Temel Kural

```text
EĞER satılabilir_stok >= istenen_adet  İSE
    stok düşülür
    sipariş onaylanır
DEĞİLSE
    işlem engellenir veya kullanıcı uyarılır

### 4.3. MVP’de Yapılacaklar

- Sipariş onayından önce stok kontrolü
- Yetersiz stokta uyarı / engelleme
- Onay sonrası stok düşümü
- İptal ve iade sonrası stok iadesi

### 4.4. MVP’de Yapılmayacaklar

- Gelişmiş rezervasyon motoru
- Kanal bazlı stok ayırma
- Gerçek zamanlı pazaryeri stok senkronu
- Karmaşık tahminleme algoritmaları

---

## 5. Gelişmiş Yaklaşım: Rezervasyon (Soft Reservation)

İlerleyen versiyonlarda daha güvenli model kullanılabilir.

### 5.1. Stok Alanları

- `toplam_stok`
- `rezerve_stok`
- `satilabilir_stok = toplam_stok - rezerve_stok`

### 5.2. Akış

1. Sipariş geldiğinde stok **rezerve** edilir
2. Sipariş kesinleşince rezervasyon **kalıcı düşüme** çevrilir
3. Sipariş iptal edilirse rezervasyon **serbest bırakılır**

### 5.3. Avantajı

Aynı anda birden fazla kanaldan gelen siparişlerde çakışma riski azalır.

---

**## 6. Ek Önlemler
**
**### 6.1. Güvenlik Stoğu (Safety Stock)
**
Gerçek stokun tamamı satışa açılmaz.

**Örnek:**
- Gerçek stok: 20
- Güvenlik stoğu: 2
- Satılabilir stok: 18

Bu yöntem; sayım farkı, hasar, gecikmeli iade gibi durumlara karşı tampon oluşturur.

**### 6.2. Kritik Stok Uyarısı
**
Stok belirlenen seviyenin altına düştüğünde sistem uyarı üretir.  
Bu doğrudan overselling’i engellemez ama riski erken gösterir.

---

**## 7. İade ve İptalin Etkisi
**
Overselling sadece satış anında oluşmaz.

- İptal edilen siparişin stoğu geç geri eklenirse
- İade ürün stoğa geç yansırsa

yeni satışlar yanlış stok bilgisiyle yapılabilir.

Bu yüzden:
- İptal → stok iadesi hızlı olmalı
- İade → ürün depoya girince stok güncellenmeli

---

**## 8. Başarı Kriteri
**
Overselling önleme özelliği başarılı sayılır eğer:

1. Stok yetersizken yapılan satışlar belirgin şekilde azalır
2. Operasyon ekibi stok çakışmalarını daha az yaşar
3. Sistem, kritik anlarda uyarı veya engelleme yapabilir
4. İptal/iade sonrası stok güncellemesi aksatılmadan ilerler

---

**## 9. Uygulama Notu
**
- Overselling’i %100 bitirmek zordur, özellikle çok kanallı ve yarı manuel ortamlarda.
- Hedef: riski kontrol altına almak ve belirgin şekilde azaltmak.
- Stok verisi kalitesizse hiçbir algoritma yeterli olmaz.
- Bu yüzden stok giriş/güncelleme disiplini de çözümün parçasıdır.

---

## 10. Özet

OrderSync’te overselling önleme stratejisi:

1. **MVP:** Onay anında stok kontrolü + düşüm
2. **Sonraki aşama:** Rezervasyon modeli
3. **Destekleyici:** Güvenlik stoğu + kritik stok uyarısı
4. **Süreç:** İptal ve iade ile stok iadesinin hızlı yapılması

