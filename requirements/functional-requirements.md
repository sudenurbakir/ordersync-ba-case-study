# Functional Requirements

## 1. Amaç

Bu doküman, OrderSync sisteminin **ne yapması gerektiğini** daha net ve uygulanabilir seviyede tanımlar.  
Business Requirements (BRD) ve User Story’lerden yola çıkılarak hazırlanmıştır.

---

## 2. Fonksiyonel Gereksinimler

### 2.1. Sipariş Yönetimi

| ID | Gereksinim | Açıklama | Öncelik |
|----|------------|----------|---------|
| FR-01 | Merkezi sipariş listesi | Sistem, farklı kanallardan gelen siparişleri tek bir listede gösterebilmelidir. | Yüksek |
| FR-02 | Sipariş filtreleme | Kullanıcı siparişleri duruma, tarihe, kanala veya müşteriye göre filtreleyebilmelidir. | Yüksek |
| FR-03 | Sipariş detay görüntüleme | Kullanıcı bir siparişin detaylarını (ürünler, adet, adres, kanal bilgisi vb.) görüntüleyebilmelidir. | Yüksek |
| FR-04 | Sipariş durum güncelleme | Kullanıcı sipariş durumunu sistem üzerinden güncelleyebilmelidir. | Yüksek |
| FR-05 | Durum geçmişi | Sistem, bir siparişin durum değişiklik geçmişini tutabilmelidir. | Orta |

---

### 2.2. Stok Yönetimi

| ID | Gereksinim | Açıklama | Öncelik |
|----|------------|----------|---------|
| FR-06 | Stok listesi | Sistem, ürünlerin güncel stok bilgisini listeleyebilmelidir. | Yüksek |
| FR-07 | Stok güncelleme | Yetkili kullanıcı stok miktarını manuel olarak güncelleyebilmelidir. | Yüksek |
| FR-08 | Kritik stok uyarısı | Stok belirlenen seviyenin altına düştüğünde sistem uyarı üretebilmelidir. | Orta |
| FR-09 | Stok düşümü | Sipariş onaylandığında ilgili ürünlerin stok miktarı azaltılabilmelidir. | Yüksek |
| FR-10 | Stok iadesi | İptal veya iade durumunda stok miktarı tekrar artırılabilmelidir. | Yüksek |

---

### 2.3. Overselling Kontrolü

| ID | Gereksinim | Açıklama | Öncelik |
|----|------------|----------|---------|
| FR-11 | Stok kontrolü | Yeni sipariş oluşturulurken veya onaylanırken sistem stok yeterliliğini kontrol edebilmelidir. | Yüksek |
| FR-12 | Yetersiz stok uyarısı | Stok yetersizse sistem kullanıcıyı uyarmalı veya işlemi engelleyebilmelidir. | Yüksek |

---

### 2.4. İade ve İptal Yönetimi

| ID | Gereksinim | Açıklama | Öncelik |
|----|------------|----------|---------|
| FR-13 | İade talebi kaydı | Sistem üzerinden iade talebi oluşturulabilmeli ve takip edilebilmelidir. | Orta |
| FR-14 | İptal işlemi | Sipariş iptal edilebilmeli ve ilgili stok güncellemesi yapılabilmelidir. | Yüksek |
| FR-15 | İade durumu takibi | İade sürecinin aşamaları (talep alındı, ürün geldi, tamamlandı vb.) takip edilebilmelidir. | Orta |

---

### 2.5. Görünürlük ve Raporlama

| ID | Gereksinim | Açıklama | Öncelik |
|----|------------|----------|---------|
| FR-16 | Özet gösterge paneli | Sistem; günlük sipariş sayısı, bekleyen siparişler, kritik stoklar gibi özet bilgileri gösterebilmelidir. | Orta |
| FR-17 | Temel listeler | Kullanıcı sipariş, stok ve iade listelerini görüntüleyebilmelidir. | Yüksek |

---

### 2.6. Kullanıcı ve Yetkilendirme

| ID | Gereksinim | Açıklama | Öncelik |
|----|------------|----------|---------|
| FR-18 | Kullanıcı rolleri | Sistem en az şu rolleri desteklemelidir: İşletme Sahibi, Operasyon, Depo. | Orta |
| FR-19 | Yetki kontrolü | Kullanıcılar sadece yetkili oldukları işlemleri yapabilmelidir. | Orta |

---

## 3. Öncelik Özeti

**Yüksek Öncelikli (MVP için kritik):**
- FR-01, FR-02, FR-03, FR-04
- FR-06, FR-07, FR-09, FR-10
- FR-11, FR-12
- FR-14
- FR-17

**Orta Öncelikli:**
- FR-05, FR-08, FR-13, FR-15, FR-16, FR-18, FR-19

---

## 4. Notlar

- Bu gereksinimler ilk versiyon (MVP) odaklıdır.
- Teknik nasıl yapılacağı (API, veritabanı tasarımı vb.) bu dokümanın kapsamı dışındadır.
- Her fonksiyonel gereksinim, ilgili User Story’ler ile ilişkilidir.
