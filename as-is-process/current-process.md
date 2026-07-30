# Current Process (As-Is)

## 1. Genel Bakış

Orta ölçekli bir e-ticaret satıcısının mevcut sipariş ve stok yönetim süreci genellikle şu şekilde işlemektedir:

- Siparişler birden fazla kanaldan ayrı ayrı gelmektedir.
- Her kanalın kendi paneli vardır.
- Stok takibi çoğu zaman Excel veya basit bir stok programı ile yapılmaktadır.
- Süreçlerin büyük kısmı manuel ilerler.

---

## 2. Mevcut Süreç Adımları

### 2.1. Sipariş Alma
1. Müşteri farklı kanallardan (kendi site, pazaryeri, sosyal medya) sipariş verir.
2. Her kanal kendi sisteminde siparişi oluşturur.
3. Operasyon sorumlusu gün içinde birden fazla panele girerek yeni siparişleri kontrol eder.

### 2.2. Stok Kontrolü
1. Sipariş geldikten sonra stok Excel'den veya stok programından kontrol edilir.
2. Stok varsa sipariş onaylanır.
3. Stok yoksa veya yetersizse sipariş iptal edilir ya da müşteri bilgilendirilir.
4. Stok düşümü çoğu zaman manuel yapılır.

### 2.3. Sipariş Hazırlama
1. Onaylanan siparişler depo/stok sorumlusuna iletilir (WhatsApp, Excel listesi veya sözlü).
2. Ürün raftan alınır ve paketlenir.
3. Kargo etiketi ilgili pazaryeri panelinden veya kargo programından kesilir.
4. Sipariş kargoya verilir.
5. Sipariş durumu ilgili panellerde tek tek güncellenir.

### 2.4. İade / İptal Süreci
1. Müşteri iade talebi oluşturur (pazaryeri üzerinden veya doğrudan iletişime geçerek).
2. İade talebi operasyon veya müşteri hizmetleri tarafından kontrol edilir.
3. Ürün depoya geri geldiğinde stok Excel'e manuel eklenir.
4. İade onaylanır ve gerekli ise iade tutarı işlenir.
5. Süreç farklı kanallarda farklı işlediği için standart değildir.

---

## 3. Mevcut Süreçte Kullanılan Araçlar

| Süreç | Kullanılan Araç |
|-------|------------------|
| Sipariş takibi | Pazaryeri panelleri + kendi site paneli |
| Stok takibi | Excel veya basit stok programı |
| İletişim | WhatsApp, telefon, e-posta |
| Kargo | Kargo firması paneli / pazaryeri entegrasyonu |
| Raporlama | Manuel Excel listeleri |

---

## 4. Süreç Özellikleri (As-Is Özeti)

- **Merkezi bir sistem yok**
- **Yüksek manuel efor var**
- **Stok bilgisi gerçek zamanlı değil**
- **Sipariş durumları dağınık**
- **İade süreçleri standart değil**
- **Hata yapma ihtimali yüksek**

---

## 5. Basit Süreç Akışı 

Müşteri Sipariş Verir
↓
Farklı Kanallardan Sipariş Düşer
↓
Operasyon Panele Tek Tek Bakar
↓
Stok Excel'den Kontrol Edilir
↓
Stok Varsa → Hazırlık Başlar
Stok Yoksa → İptal / Bilgilendirme
↓
Paketleme + Kargo
↓
Durum Güncellemesi (Manuel)
↓
İade olursa → Manuel Süreç Tekrar Başlar
