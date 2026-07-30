# To-Be Process

## 1. Amaç

Bu doküman, OrderSync ile birlikte hedeflenen yeni operasyon sürecini tanımlar.  
Amaç; mevcut dağınık ve manuel akışı daha merkezi ve kontrollü hale getirmektir.

---

## 2. Yeni Süreç Adımları

### 2.1. Sipariş Alma ve Görüntüleme
1. Müşteri farklı kanallardan sipariş verir.
2. Siparişler OrderSync sistemine düşer (manuel aktarım veya entegrasyon ile).
3. Operasyon sorumlusu tüm siparişleri **tek listeden** görür.
4. Gerekirse siparişleri kanal, durum veya tarihe göre filtreler.

### 2.2. Stok Kontrolü ve Onay
1. Sistem sipariş üzerindeki ürünlerin stok durumunu kontrol eder.
2. Stok yeterliyse sipariş onaylanabilir.
3. Stok yetersizse sistem uyarı verir veya işlemi engeller.
4. Onaylanan siparişte stok düşümü yapılır.

### 2.3. Sipariş Hazırlama
1. Onaylanan sipariş depo/stok sorumlusu tarafından görülür.
2. Ürünler hazırlanır ve paketlenir.
3. Kargo süreci başlatılır.
4. Sipariş durumu OrderSync üzerinden güncellenir (örnek: Hazırlanıyor → Kargoya Verildi).

### 2.4. İade / İptal Süreci
1. İade veya iptal talebi sisteme kaydedilir.
2. İlgili ekip talebi inceler.
3. İade ürün depoya ulaştığında stok geri artırılır.
4. Süreç durumu sistem üzerinden takip edilir ve kapatılır.

---

## 3. To-Be Süreç Akışı 

Müşteri Sipariş Verir
↓
Sipariş OrderSync’e Düşer
↓
Operasyon Tek Listeden Görür
↓
Sistem Stok Kontrolü Yapar
↓
Stok Varsa → Sipariş Onaylanır + Stok Düşülür
Stok Yoksa → Uyarı / Engelleme
↓
Depo Hazırlık Yapar
↓
Kargo Süreci Başlar
↓
Durum OrderSync’ten Güncellenir
↓
İade/İptal olursa → Sistem Üzerinden Standart Süreç İşler


---

## 4. As-Is ile To-Be Karşılaştırması

| Adım | As-Is | To-Be |
|------|-------|-------|
| Sipariş görme | Birden fazla panele girme | Tek listeden görme |
| Stok kontrolü | Excel / manuel | Sistem destekli kontrol |
| Stok düşümü | Manuel | Sistem üzerinden |
| Durum güncelleme | Her panelde ayrı | Tek yerden |
| İade süreci | Dağınık | Daha standart ve izlenebilir |
| Görünürlük | Zayıf | Daha net ve merkezi |

---

## 5. Süreçten Beklenen İyileşmeler

- Sipariş kaçırma riskinin azalması
- Overselling oranının düşmesi
- Manuel işlem süresinin azalması
- Stok bilgisinin daha güncel olması
- Operasyon ekibinin daha az panel arasında geçiş yapması
- Yönetimin süreci daha kolay takip edebilmesi

---

## 6. Not

Bu To-Be süreç, ilk versiyon (MVP) için sade tutulmuştur.  
İlerleyen aşamalarda otomatik entegrasyonlar ve daha gelişmiş akışlar eklenebilir.
