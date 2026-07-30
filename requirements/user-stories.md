# User Stories

## 1. Amaç

Bu dokümanda, OrderSync sisteminin temel kullanıcı ihtiyaçları **User Story** formatında yazılmıştır.  
Her story, “Kim – Ne istiyor – Neden” yapısına uygun şekilde hazırlanmıştır.

---

## 2. User Story Formatı

**Format:**  
Bir **[rol]** olarak, **[amaç]** istiyorum, böylece **[fayda]** sağlarım.

---

## 3. User Stories

### 3.1. Sipariş Yönetimi

**US-01**  
Bir **Operasyon Sorumlusu** olarak, tüm kanallardan gelen siparişleri tek listede görmek istiyorum,  
böylece her panele tek tek girmek zorunda kalmam.

**US-02**  
Bir **Operasyon Sorumlusu** olarak, sipariş durumunu (hazırlanıyor, kargoya verildi, tamamlandı vb.) tek yerden güncellemek istiyorum,  
böylece her kanalda ayrı ayrı işlem yapmak zorunda kalmam.

**US-03**  
Bir **Operasyon Sorumlusu** olarak, yeni gelen siparişleri hızlıca filtreleyip önceliklendirmek istiyorum,  
böylece kritik siparişleri kaçırmam.

---

### 3.2. Stok Yönetimi

**US-04**  
Bir **Depo / Stok Sorumlusu** olarak, ürün stoklarını tek yerden görüp güncellemek istiyorum,  
böylece Excel ve farklı sistemler arasında kaybolmam.

**US-05**  
Bir **Operasyon Sorumlusu** olarak, stok yetersiz olduğunda sistemin beni uyarmasını veya satışı engellemesini istiyorum,  
böylece overselling yaşamam.

**US-06**  
Bir **Depo Sorumlusu** olarak, iade gelen ürünü stoka kolayca geri eklemek istiyorum,  
böylece stok bilgisi güncel kalsın.

---

### 3.3. İade ve İptal

**US-07**  
Bir **Müşteri Hizmetleri** sorumlusu olarak, iade taleplerini standart bir akış ile yönetmek istiyorum,  
böylece her kanal için farklı süreç takip etmek zorunda kalmam.

**US-08**  
Bir **Operasyon Sorumlusu** olarak, iptal edilen siparişin stoka otomatik veya kolay şekilde geri yansımasını istiyorum,  
böylece stok hatası oluşmasın.

---

### 3.4. Görünürlük ve Yönetim

**US-09**  
Bir **İşletme Sahibi** olarak, günlük sipariş, stok ve iade durumunu özet olarak görmek istiyorum,  
böylece operasyonun genel sağlığını hızlıca anlayabilirim.

**US-10**  
Bir **İşletme Sahibi** olarak, kritik stok seviyesine düşen ürünleri görmek istiyorum,  
böylece tedarik kararlarını zamanında alabilirim.

---

### 3.5. Yetkilendirme

**US-11**  
Bir **İşletme Sahibi** olarak, farklı kullanıcılara farklı yetkiler verebilmek istiyorum,  
böylece herkes sadece kendi işiyle ilgili ekranları görsün.

---

## 4. Story Önceliklendirme (Basit)

| Öncelik | Story ID | Gerekçe |
|---------|----------|---------|
| Yüksek | US-01, US-02, US-04, US-05 | Temel değeri oluşturuyor |
| Orta | US-03, US-06, US-07, US-08 | Operasyonu güçlendiriyor |
| Orta-Düşük | US-09, US-10, US-11 | Yönetim ve kontrol sağlıyor |

---

## 5. Not

Bu User Story’ler ilk versiyon (MVP) için yazılmıştır.  
Geliştirme sürecinde detaylandırılarak Acceptance Criteria eklenebilir.
