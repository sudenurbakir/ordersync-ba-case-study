# Business Requirements Document (BRD)

## 1. Doküman Bilgisi

- **Proje Adı:** OrderSync – E-ticaret Çok Kanallı Sipariş & Stok Yönetim Sistemi
- **Doküman Türü:** Business Requirements Document
- **Versiyon:** 1.0
- **Tarih:** 2026

---

## 2. Amaç

Bu doküman, OrderSync sisteminin iş ihtiyaçlarını yüksek seviyede tanımlar.  
Teknik detaylara girmeden, sistemin **ne yapması gerektiğini** iş bakış açısıyla ortaya koyar.

---

## 3. İş Problemi Özeti

Orta ölçekli e-ticaret satıcıları, birden fazla satış kanalını yönetirken şu sorunlarla karşılaşmaktadır:

- Siparişlerin dağınık takibi
- Stokların senkronize olmaması
- Yüksek manuel iş yükü
- Overselling riski
- İade süreçlerinin karmaşıklığı

OrderSync, bu sorunları tek bir merkezden yöneterek azaltmayı hedefler.

---

## 4. İş Gereksinimleri (Business Requirements)

| ID | Gereksinim | Açıklama | Öncelik |
|----|------------|----------|---------|
| BR-01 | Merkezi Sipariş Görünümü | Tüm kanallardan gelen siparişler tek bir listede görülebilmelidir. | Yüksek |
| BR-02 | Stok Senkronizasyonu | Ürün stokları kanallar arasında tutarlı ve güncel tutulabilmelidir. | Yüksek |
| BR-03 | Overselling Önleme | Stok yetersiz olduğunda ilgili üründen yeni satış yapılmasını engelleyebilmelidir. | Yüksek |
| BR-04 | Sipariş Durum Yönetimi | Sipariş durumu tek yerden güncellenebilmeli ve ilgili kanallara yansıyabilmelidir. | Yüksek |
| BR-05 | İade / İptal Yönetimi | İade ve iptal talepleri standart bir süreç ile yönetilebilmelidir. | Orta |
| BR-06 | Temel Görünürlük | İşletme sahibi temel operasyonel durumu (sipariş, stok, iade) hızlıca görebilmelidir. | Orta |
| BR-07 | Manuel İş Yükünü Azaltma | Mevcut manuel adımların bir kısmı sistem tarafından desteklenmeli veya otomatikleştirilmelidir. | Yüksek |
| BR-08 | Kullanıcı Rolleri | Farklı kullanıcı rollerine (İşletme Sahibi, Operasyon, Depo) uygun yetkilendirme olabilmelidir. | Orta |

---

## 5. Kapsam

### Kapsam İçinde
- Çok kanallı siparişlerin merkezi takibi
- Stok yönetimi ve temel senkronizasyon
- Sipariş durum güncelleme
- İade / iptal süreci
- Temel raporlama ve görünürlük

### Kapsam Dışında (Şimdilik)
- Muhasebe ve faturalama entegrasyonu
- Gelişmiş kargo API otomasyonları
- Yapay zeka ile talep tahmini
- Çoklu depo / gelişmiş lojistik yönetimi
- Mobil uygulama

---

## 6. Varsayımlar

- Satıcının en az 2 farklı satış kanalı kullanıyor olduğu varsayılır.
- Stok bilgisi sisteme düzenli olarak girilebilecek veya güncellenebilecektir.
- Kullanıcılar temel düzeyde dijital araç kullanabilmektedir.
- İlk aşamada sınırlı sayıda kanal ile çalışılacaktır.

---

## 7. Kısıtlar

- İlk versiyonda (MVP) çok karmaşık entegrasyonlar yapılmayacaktır.
- Sistem, küçük ve orta ölçekli satıcıların kullanımına uygun sade tutulacaktır.
- Bütçe ve geliştirme süresi sınırlı kabul edilir.

---

## 8. Başarı Kriterleri (Yüksek Seviye)

Sistem başarılı sayılır eğer:

- Siparişler tek ekrandan takip edilebiliyorsa
- Stok kaynaklı hatalar belirgin şekilde azalıyorsa
- Operasyon ekibinin manuel eforu azalıyorsa
- İşletme sahibi temel durumu daha hızlı görebiliyorsa
