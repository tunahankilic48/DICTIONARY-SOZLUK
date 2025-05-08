# Katmanlı Mimari Nedir?

**Katmanlı mimari**, yazılım geliştirme sürecinde yazılımın daha **modüler**, **bakımı kolay**, **test edilebilir** ve **yeniden kullanılabilir** olmasını sağlayan bir mimari yaklaşımdır. Uygulama, farklı sorumluluklara sahip katmanlara ayrılarak geliştirilir.

Genellikle 3 temel katmandan oluşur, ancak ihtiyaçlara göre bu katmanlar artırılabilir.

---

## 1. Sunum Katmanı (Presentation Layer)

- Kullanıcının sistemle etkileşime geçtiği katmandır.
- Kullanıcıdan veri alır ve sonuçları kullanıcıya sunar.
- Arayüz bileşenleri bu katmanda yer alır.

**Örnekler:**
- Web arayüzü (HTML, CSS, JavaScript)
- Mobil uygulama arayüzleri
- Masaüstü kullanıcı arayüzleri

---

## 2. İş Katmanı (Business Logic Layer)

- Uygulamanın iş kurallarını ve mantığını barındırır.
- Verilerin nasıl işleneceğini ve uygulamanın nasıl çalışacağını belirler.

**Örnekler:**
- Sipariş hesaplama
- Doğrulama işlemleri
- İş akışı yönetimi

---

## 3. Veri Erişim Katmanı (Data Access Layer)

- Uygulamanın veritabanı ile iletişim kurduğu katmandır.
- CRUD (Create, Read, Update, Delete) işlemleri burada gerçekleştirilir.

**Örnekler:**
- SQL sorguları
- ORM araçları (Entity Framework, Hibernate, vb.)

---

## Katmanlı Mimarinin Avantajları

- **Modülerlik:** Her katman bağımsız olarak geliştirilebilir.
- **Bakım Kolaylığı:** Hatalar izole edilerek daha kolay tespit ve düzeltme yapılabilir.
- **Yeniden Kullanılabilirlik:** Katmanlar farklı projelerde tekrar kullanılabilir.
- **Test Edilebilirlik:** Katmanlar birbirinden bağımsız olarak test edilebilir.

---

## Dezavantajları

- **Performans Kaybı:** Katmanlar arası iletişim gecikmelere neden olabilir.
- **Karmaşıklık:** Çok sayıda katman, projenin yapısını karmaşık hale getirebilir.
- **Daha Fazla Zaman:** Geliştirme süresi uzayabilir, çünkü daha fazla yapı ve kod gerekir.
