# MVP Scope

## 1. Amaç

Bu doküman, OrderSync’in ilk yayınlanabilir versiyonunda (MVP) nelerin yer alacağını ve nelerin bilerek dışarıda bırakılacağını netleştirir.

Amaç; küçük ama değer üreten bir ilk versiyon çıkarmaktır.

---

## 2. MVP’nin Temel Hedefi

Orta ölçekli bir e-ticaret satıcısının:

- Tüm siparişlerini tek yerden görmesini
- Stokunu daha kontrollü yönetmesini
- Overselling riskini azaltmasını

sağlamak.

---

## 3. MVP Kapsamında Olanlar

### Sipariş Yönetimi
- Farklı kanallardan gelen siparişleri tek listede gösterme
- Sipariş detaylarını görüntüleme
- Sipariş durumu güncelleme
- Basit filtreleme (durum, tarih, kanal)

### Stok Yönetimi
- Ürün stok listesi
- Manuel stok güncelleme
- Sipariş onayında stok düşümü
- İptal/iade durumunda stok geri ekleme
- Basit kritik stok takibi

### Kontrol
- Stok yetersizse uyarı veya engelleme (overselling kontrolü)

### Görünürlük
- Basit özet ekran (bekleyen sipariş, kritik stok vb.)

### Kullanıcı
- Temel roller: İşletme Sahibi, Operasyon, Depo

---

## 4. MVP Kapsamı Dışında Olanlar

Aşağıdakiler ilk versiyona **dahil edilmeyecektir**:

- Gerçek zamanlı pazaryeri API entegrasyonları (otomatik sipariş çekme)
- Muhasebe / fatura entegrasyonu
- Gelişmiş kargo entegrasyonları
- Mobil uygulama
- Çoklu depo yönetimi
- Gelişmiş analitik ve tahminleme
- Otomatik fiyatlandırma
- Müşteri iletişim otomasyonları (e-posta/SMS)

---

## 5. MVP Başarı Kriteri

MVP başarılı sayılır eğer:

1. Kullanıcı siparişleri tek listeden yönetebiliyorsa
2. Stok düşümü ve iade/iptal ile stok güncellemesi yapılabiliyorsa
3. Overselling riski belirgin şekilde azalmışsa
4. Ana kullanıcılar sistemi günlük işlerinde kullanmaya başladıysa

---

## 6. MVP Yaklaşımı

- Önce temel değeri sun
- Karmaşık entegrasyonları sonraya bırak
- Kullanıcıdan hızlı geri bildirim al
- Sonraki versiyonları gerçek kullanıma göre şekillendir

---

## 7. Özet

MVP’nin özü:

> “Az özellik, net değer.”

OrderSync’in ilk versiyonu her şeyi çözmek zorunda değildir.  
Ama sipariş + stok yönetimindeki en can alıcı problemleri somut olarak iyileştirmelidir.
