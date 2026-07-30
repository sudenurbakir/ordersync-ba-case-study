# Gap Analysis

## 1. Amaç

Gap Analysis, mevcut durum (As-Is) ile istenen durum (To-Be) arasındaki farkları net bir şekilde ortaya koyar.  
Bu sayede hangi alanlarda geliştirmeye ihtiyaç olduğu daha net görülür.

---

## 2. Gap Tablosu

| Alan | Mevcut Durum (As-Is) | İstenen Durum (To-Be) | Gap (Boşluk) | Öncelik |
|------|----------------------|-----------------------|--------------|---------|
| Sipariş Yönetimi | Siparişler farklı panellerden ayrı ayrı takip ediliyor | Tüm kanallardaki siparişler tek ekranda görülebiliyor | Merkezi sipariş görünümü yok | Yüksek |
| Stok Yönetimi | Stok Excel veya ayrı sistemlerde tutuluyor, senkron değil | Stoklar kanallar arasında gerçek zamanlı senkronize | Otomatik stok senkronizasyonu yok | Yüksek |
| Overselling Kontrolü | Manuel kontrol yapılıyor, hata riski yüksek | Stok yetersizse satış otomatik engelleniyor | Otomatik stok kontrolü yok | Yüksek |
| Sipariş Durum Güncelleme | Her panelde ayrı ayrı manuel güncelleniyor | Tek yerden durum güncellenince ilgili kanallara yansıyor | Merkezi durum yönetimi yok | Yüksek |
| İade / İptal Süreci | Her kanalda farklı ve dağınık işliyor | Standart bir iade/iptal akışı var | Standart süreç yok | Orta |
| Raporlama & Görünürlük | Manuel Excel listeleri ile takip ediliyor | Temel KPI'lar tek ekranda izlenebiliyor | Anlık dashboard yok | Orta |
| İletişim | WhatsApp, Excel ve sözlü iletişim yoğun | Sistem üzerinden net ve kayıtlı ilerliyor | Merkezi ve izlenebilir süreç yok | Orta |
| Hata Oranı | Manuel işlemlerden dolayı hata riski yüksek | Sistem kontrolleri ile hata oranı düşük | Otomatik kontroller yetersiz | Yüksek |

---

## 3. Gap'lerin Önceliklendirilmesi

### Yüksek Öncelikli Gap'ler
1. Merkezi sipariş görünümünün olmaması
2. Stok senkronizasyonunun olmaması
3. Overselling'i engelleyecek otomatik kontrolün olmaması
4. Sipariş durumlarının merkezi yönetilememesi

Bu dört gap çözülmeden sistemin temel değeri ortaya çıkmaz.

### Orta Öncelikli Gap'ler
- Standart iade/iptal süreci
- Anlık raporlama ve görünürlük
- İletişimin sistem üzerinden ilerlemesi

---

## 4. Gap'lerden Çıkan Sonuç

Mevcut sistem ile istenen sistem arasındaki en kritik farklar şunlardır:

- **Merkezileşme eksikliği**
- **Otomasyon eksikliği**
- **Gerçek zamanlı veri eksikliği**

OrderSync çözümünün temel amacı, bu üç alandaki boşlukları kapatmaktır.

---

## 5. Sonraki Adım

Bu gap'ler, `requirements` klasöründe yazılacak olan gereksinimlerin temelini oluşturur.  
Yani bundan sonra yazacağımız User Story ve Fonksiyonel Gereksinimler, doğrudan bu boşlukları kapatmaya yönelik olacaktır.
