# Data Model (Temel)

## 1. Amaç

Bu doküman, OrderSync sisteminin temel veri yapısını yüksek seviyede tanımlar.  
Amaç; sistemde hangi ana varlıkların (entity) tutulacağını ve bunlar arasındaki ilişkileri netleştirmektir.

Not: Bu bir teknik veritabanı tasarımı değil, **iş odaklı temel veri modelidir**.

---

## 2. Ana Varlıklar (Entities)

### 2.1. Product (Ürün)
Sistemde satılan ürünleri temsil eder.

**Temel Alanlar:**
- Ürün ID
- Ürün Adı
- SKU / Stok Kodu
- Güncel Stok Miktarı
- Kritik Stok Seviyesi
- Birim Fiyat (opsiyonel)
- Durum (Aktif / Pasif)

---

### 2.2. Channel (Satış Kanalı)
Siparişin geldiği kanalı temsil eder.

**Temel Alanlar:**
- Kanal ID
- Kanal Adı (Örn: Kendi Site, Pazaryeri A, Pazaryeri B)
- Durum (Aktif / Pasif)

---

### 2.3. Order (Sipariş)
Müşteriden gelen siparişi temsil eder.

**Temel Alanlar:**
- Sipariş ID
- Kanal ID
- Müşteri Bilgisi (ad, iletişim - basit)
- Sipariş Tarihi
- Sipariş Durumu (Yeni, Onaylandı, Hazırlanıyor, Kargoda, Tamamlandı, İptal)
- Toplam Tutar (opsiyonel)

---

### 2.4. Order Item (Sipariş Kalemi)
Bir siparişin içindeki ürün satırlarını temsil eder.

**Temel Alanlar:**
- Sipariş Kalemi ID
- Sipariş ID
- Ürün ID
- Adet
- Birim Fiyat

---

### 2.5. Stock Movement (Stok Hareketi)
Stokta artma veya azalma yaratan işlemleri temsil eder.

**Temel Alanlar:**
- Hareket ID
- Ürün ID
- Hareket Tipi (Sipariş Düşümü, İade Girişi, Manuel Güncelleme, İptal İadesi)
- Miktar
- Tarih
- İlişkili Sipariş ID (varsa)
- Açıklama

---

### 2.6. Return / Cancellation (İade / İptal)
İade ve iptal taleplerini temsil eder.

**Temel Alanlar:**
- Kayıt ID
- Sipariş ID
- Tip (İade / İptal)
- Durum (Talep Alındı, İnceleniyor, Tamamlandı, Reddedildi)
- Talep Tarihi
- Açıklama

---

### 2.7. User (Kullanıcı)
Sistemi kullanan kişileri temsil eder.

**Temel Alanlar:**
- Kullanıcı ID
- Ad Soyad
- Rol (İşletme Sahibi, Operasyon, Depo, Müşteri Hizmetleri)
- Durum (Aktif / Pasif)

---

## 3. Temel İlişkiler

- Bir **Channel**, birden fazla **Order** içerebilir.
- Bir **Order**, birden fazla **Order Item** içerebilir.
- Bir **Order Item**, bir **Product** ile ilişkilidir.
- Bir **Product**, birden fazla **Stock Movement** içerebilir.
- Bir **Order**, bir **Return / Cancellation** kaydı ile ilişkilenebilir.
- Bir **User**, sistemdeki işlemlere yetkisi oranında erişir.

---

## 4. Basit İlişki Özeti

Channel 1───* Order 1───* Order Item *───1 Product
│
└─── Stock Movement
Order 1───0..1 Return/Cancellation
User (Rol bazlı erişim)


---

## 5. Notlar

- Bu model ilk versiyon (MVP) için sade tutulmuştur.
- İleride müşteri, adres, kargo, ödeme gibi ek varlıklar eklenebilir.
- Teknik implementasyon sırasında alan tipleri ve zorunluluklar detaylandırılmalıdır.
