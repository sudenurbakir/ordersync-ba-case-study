# Order Status State Machine

## 1. Amaç

Bu doküman, OrderSync sistemindeki sipariş durumlarını ve bu durumlar arasındaki geçiş kurallarını tanımlar.  
Amaç; sipariş yaşam döngüsünü net, izlenebilir ve stok kurallarıyla uyumlu hale getirmektir.

---

## 2. Temel Durumlar

| Durum | Açıklama |
|-------|----------|
| `Yeni` | Sipariş sisteme düşmüştür, henüz işlenmemiştir |
| `Onaylandi` | Stok kontrolü yapılmış ve sipariş onaylanmıştır |
| `Hazirlaniyor` | Ürün hazırlık / paketleme aşamasındadır |
| `Kargoda` | Sipariş kargoya verilmiştir |
| `Tamamlandi` | Sipariş teslim edilmiş / süreç tamamlanmıştır |
| `Iptal` | Sipariş iptal edilmiştir |
| `IadeSurecinde` | İade talebi alınmış, süreç devam etmektedir |
| `IadeEdildi` | İade tamamlanmış ve süreç kapanmıştır |

---

## 3. Durum Geçişleri

### 3.1. Ana Akış

Yeni
 └─→ Onaylandi
      └─→ Hazirlaniyor
           └─→ Kargoda
                └─→ Tamamlandi


**3.2. İptal Akışı**

Yeni            → Iptal
Onaylandi       → Iptal
Hazirlaniyor    → Iptal

Not: Kargoda ve Tamamlandi sonrası iptal yerine iade süreci kullanılır.

**3.3. İade Akışı**

Kargoda         → IadeSurecinde → IadeEdildi
Tamamlandi      → IadeSurecinde → IadeEdildi

## 4. Geçiş Kuralları ve Stok Etkisi

| Geçiş | Stok Etkisi | Açıklama |
|-------|-------------|----------|
| `Yeni → Onaylandi` | Stok düşülür veya rezervasyon kesinleşir | Overselling kontrolü bu adımda yapılır |
| `Onaylandi → Hazirlaniyor` | Stok değişmez | Operasyonel hazırlık başlar |
| `Hazirlaniyor → Kargoda` | Stok değişmez | Kargo süreci başlar |
| `Kargoda → Tamamlandi` | Stok değişmez | Sipariş tamamlanır |
| `Yeni/Onaylandi/Hazirlaniyor → Iptal` | Stok geri eklenir | Ürün tekrar satılabilir olur |
| `Kargoda/Tamamlandi → IadeSurecinde` | Stok henüz artmaz | Ürünün geri gelmesi beklenir |
| `IadeSurecinde → IadeEdildi` | Stok geri eklenir | Ürün depoya girdikten sonra |

**5. Durum Makinesi Özeti**

[Yeni]
   │
   ├─(stok uygun)→ [Onaylandi] → [Hazirlaniyor] → [Kargoda] → [Tamamlandi]
   │
   └─(iptal)→ [Iptal]

[Kargoda] / [Tamamlandi]
   └─→ [IadeSurecinde] → [IadeEdildi]

## 6. Tasarım Prensipleri

1. **Net son durumlar**
   - `Iptal` ve `IadeEdildi` kapalı durumlardır.

2. **Geriye dönüş sınırlıdır**
   - Örn. `Kargoda → Hazirlaniyor` gibi geri dönüşler varsayılan olarak yoktur.

3. **Stok etkisi duruma bağlıdır**
   - Hangi geçişte stok düşer / artar açıkça tanımlıdır.

4. **Kanal bağımsızdır**
   - Tüm satış kanalları aynı durum makinesini kullanır.

5. **Operasyonel müdahaleye açıktır**
   - Yetkili kullanıcı durum geçişlerini sistem üzerinden yapabilir.

---

## 7. MVP Kapsamı

İlk versiyonda aşağıdaki durum seti yeterlidir:

- `Yeni`
- `Onaylandi`
- `Hazirlaniyor`
- `Kargoda`
- `Tamamlandi`
- `Iptal`
- `IadeSurecinde`
- `IadeEdildi`

Daha fazla ara durum (ör. `OdemeBekliyor`, `EksikBilgi`) ihtiyaç doğarsa sonraki aşamalarda eklenebilir.

---

## 8. Overselling ile İlişkisi

- Overselling kontrolünün ana noktası: `Yeni → Onaylandi`
- Bu geçişte stok yetersizse:
  - sistem uyarı verir veya
  - geçişi engeller
- İptal ve iade geçişlerinde stok iadesi yapılarak yeni satışlara doğru stok bırakılır

---

## 9. Başarı Kriteri

Durum makinesi başarılı sayılır eğer:

1. Siparişlerin hangi aşamada olduğu net görülebiliyorsa
2. Durum geçişleri stok kurallarıyla uyumlu çalışıyorsa
3. İptal ve iade süreçleri stok iadesini doğru tetikliyorsa
4. Operasyon ekibi siparişleri bu durumlar üzerinden yönetebiliyorsa

---

## 10. Özet

OrderSync sipariş durum makinesi:

- Ana akış: `Yeni → Onaylandi → Hazirlaniyor → Kargoda → Tamamlandi`
- İptal: hazırlık öncesi aşamalarda
- İade: kargo sonrası aşamalarda
- Stok düşümü: onay anında
- Stok iadesi: iptal ve iade tamamlanınca
