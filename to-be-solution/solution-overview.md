# Solution Overview (To-Be)

## 1. Çözümün Amacı

OrderSync, orta ölçekli e-ticaret satıcılarının çok kanallı sipariş ve stok yönetimini  
tek bir merkezden, daha az hata ve daha az manuel efor ile yapmasını sağlayan bir sistemdir.

Temel yaklaşım:
- Dağınık süreçleri merkezileştirmek
- Manuel adımları azaltmak
- Stok ve sipariş verisini daha tutarlı hale getirmek

---

## 2. Çözümün Temel Bileşenleri

### 2.1. Merkezi Sipariş Yönetimi
- Tüm kanallardan gelen siparişler tek listede toplanır
- Sipariş detayları tek ekrandan görüntülenir
- Sipariş durumu tek yerden güncellenir

### 2.2. Stok Yönetimi
- Ürün stokları merkezi olarak tutulur
- Sipariş onaylandığında stok otomatik veya yarı otomatik düşülür
- İade/iptal durumunda stok geri artırılır
- Kritik stok seviyeleri takip edilebilir

### 2.3. Overselling Kontrolü
- Sipariş işlenirken stok yeterliliği kontrol edilir
- Stok yetersizse kullanıcı uyarılır veya işlem engellenir

### 2.4. İade ve İptal Yönetimi
- İade ve iptal talepleri sistem üzerinden kayıt altına alınır
- Süreç daha standart hale getirilir
- Stok güncellemeleri bu süreçlere bağlanır

### 2.5. Görünürlük
- İşletme sahibi ve operasyon ekibi temel durumu tek bakışta görebilir
- Bekleyen siparişler, kritik stoklar ve özet bilgiler sunulur

---

## 3. Çözümün Getirdiği Değişiklikler

| Alan | Eski Durum | Yeni Durum |
|------|------------|------------|
| Sipariş takibi | Birden fazla panel | Tek merkezi liste |
| Stok yönetimi | Excel / dağınık sistemler | Merkezi stok kaydı |
| Overselling | Manuel kontrol | Sistem destekli kontrol |
| Durum güncelleme | Her panelde ayrı | Tek yerden yönetim |
| İade süreci | Dağınık ve standart değil | Daha standart akış |
| Görünürlük | Manuel takip | Özet gösterge paneli |

---

## 4. Çözüm Prensipleri

- **Sadelik:** İlk versiyon karmaşık olmayacak
- **Merkezileşme:** Bilgi ve işlemler tek yerde toplanacak
- **Kontrol:** Kritik hatalar (özellikle stok) azaltılacak
- **Ölçeklenebilirlik:** İleride yeni kanallar ve özellikler eklenebilecek şekilde düşünülecek

---

## 5. Hedef Kullanıcılar

- İşletme Sahibi → Genel kontrol ve görünürlük
- Operasyon Sorumlusu → Sipariş yönetimi
- Depo / Stok Sorumlusu → Stok işlemleri
- Müşteri Hizmetleri → İade ve iptal süreçleri

---

## 6. Özet

OrderSync’in To-Be çözümü;  
mevcut dağınık ve manuel süreçleri daha merkezi, kontrollü ve izlenebilir hale getirmeyi hedefler.

Bu çözüm, hem operasyonel yükü azaltmayı hem de işin daha sağlıklı büyümesini desteklemeyi amaçlar.
