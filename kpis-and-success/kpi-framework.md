# KPI Framework

## 1. Amaç

Bu doküman, OrderSync sisteminin başarısını ölçmek için kullanılacak temel KPI’ları tanımlar.  
KPI’lar hem operasyonel iyileşmeyi hem de iş sonuçlarını takip etmeye yönelik seçilmiştir.

---

## 2. KPI Seçim Prensipleri

KPI’lar şu sorulara cevap verecek şekilde seçilmiştir:

- Siparişler daha mı hızlı ve kontrollü yönetiliyor?
- Stok hataları azalıyor mu?
- Manuel iş yükü düşüyor mu?
- İşletme sahibi süreci daha iyi görebiliyor mu?

---

## 3. Temel KPI Grupları

### 3.1. Sipariş Yönetimi KPI’ları

| KPI | Açıklama | Neden Önemli? |
|-----|----------|----------------|
| Ortalama Sipariş İşleme Süresi | Siparişin sisteme düşmesinden kargoya verilmesine kadar geçen süre | Operasyonel hızı gösterir |
| Bekleyen Sipariş Sayısı | Henüz tamamlanmamış sipariş adedi | İş yükünü ve birikmeyi gösterir |
| Zamanında Kargoya Verilme Oranı | Planlanan sürede kargoya verilen siparişlerin oranı | Müşteri deneyimini etkiler |

---

### 3.2. Stok Yönetimi KPI’ları

| KPI | Açıklama | Neden Önemli? |
|-----|----------|----------------|
| Overselling Adedi | Stok yetersizken yapılan satış sayısı | En kritik hata göstergelerinden biri |
| Stok Uyuşmazlığı Oranı | Sistem stoku ile gerçek stok arasındaki fark | Veri kalitesini gösterir |
| Kritik Stok Ürün Sayısı | Belirlenen seviyenin altına düşen ürün adedi | Tedarik riskini gösterir |

---

### 3.3. Operasyonel Verimlilik KPI’ları

| KPI | Açıklama | Neden Önemli? |
|-----|----------|----------------|
| Manuel Müdahale Oranı | Sistemde elle düzeltilmesi gereken işlemlerin oranı | Otomasyon seviyesini gösterir |
| Panel Geçiş İhtiyacı | Operasyonun farklı panellere girme sıklığı (azalması hedeflenir) | Merkezileşme başarısını gösterir |

---

### 3.4. İade / İptal KPI’ları

| KPI | Açıklama | Neden Önemli? |
|-----|----------|----------------|
| Ortalama İade İşlem Süresi | İade talebinden sürecin kapanmasına kadar geçen süre | Süreç standartlaşmasını gösterir |
| İade Kaynaklı Stok Güncelleme Gecikmesi | İade ürün geldikten sonra stoğa yansıma süresi | Stok doğruluğunu etkiler |

---

### 3.5. Görünürlük KPI’sı (Nitel)

| KPI | Açıklama | Neden Önemli? |
|-----|----------|----------------|
| Yönetim Görünürlüğü | İşletme sahibinin temel durumu tek ekrandan görebiliyor olması | Karar alma hızını etkiler |

---

## 4. KPI Önceliklendirme

**Yüksek Öncelikli KPI’lar:**
- Overselling Adedi
- Ortalama Sipariş İşleme Süresi
- Stok Uyuşmazlığı Oranı
- Bekleyen Sipariş Sayısı

**Orta Öncelikli KPI’lar:**
- Zamanında Kargoya Verilme Oranı
- Ortalama İade İşlem Süresi
- Kritik Stok Ürün Sayısı
- Manuel Müdahale Oranı

---

## 5. Ölçüm Yaklaşımı (Basit)

- İlk aşamada veriler manuel veya yarı otomatik toplanabilir.
- Sistem geliştikçe KPI’lar doğrudan sistem üzerinden raporlanabilir hale getirilmelidir.
- Her KPI için başlangıç (baseline) değeri belirlenmeli, sonra iyileşme takip edilmelidir.

---

## 6. Not

Bu framework ilk versiyon içindir.  
İlerleyen dönemde daha detaylı finansal KPI’lar (örneğin stok kaynaklı kayıp tutarı) eklenebilir.
