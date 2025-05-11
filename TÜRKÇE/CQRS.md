# ⚙️ CQRS (Command Query Responsibility Segregation)

**CQRS**, yazılım mimarisinde kullanılan bir tasarım desenidir. Temel amacı, **veri üzerinde işlem yapma (Command)** ile **veri sorgulama (Query)** işlemlerini birbirinden ayırmaktır.

---

## 📖 Tanım

CQRS, bir uygulamanın **okuma (read)** ve **yazma (write)** işlemlerini farklı yollarla ele almasını sağlar.

Geleneksel mimarilerde veri okuma ve yazma genellikle aynı model veya nesne üzerinden yapılır.  
**CQRS** ise bu iki sorumluluğu **ayrı katmanlara** veya **sistemlere** bölerek daha:

- ✅ Esnek  
- ✅ Ölçeklenebilir  
- ✅ Bakımı kolay  

bir yapı sağlar.

---

## 🔄 CQRS'nin Temel Yapısı

### 🔧 Command (Yazma İşlemleri)
- Sistemde bir **değişiklik** (insert, update, delete) yapmak için kullanılır.
- **Sonuç döndürmez** (genellikle `void` ya da `Result` döner).
- 🧪 Yan etki yaratır.
- 📌 Örnekler:
  - `CreateOrderCommand`
  - `UpdateProfileCommand`

### 🔍 Query (Okuma İşlemleri)
- **Veri getirir**, ancak asla değişiklik yapmaz.
- 🌱 Yan etkisiz (idempotent) olmalıdır.
- 📌 Örnekler:
  - `GetOrderByIdQuery`
  - `GetCustomerListQuery`

---

## 🧠 Neden CQRS Kullanılır?

### ✅ Sorumluluk Ayrımı
- Kod daha düzenli hale gelir.
- Her bileşen **tek bir işi** yapar (SRP - SOLID uyumlu).

### ✅ Performans Optimizasyonu
- Okuma ve yazma için **farklı veri modelleri** veya **veritabanları** kullanılabilir.
- Özellikle yoğun okuma trafiği farklı yöntemlerle **ölçeklenebilir**.

### ✅ Kolay Test Edilebilirlik
- Command ve Query'ler ayrıldığı için **bağımsız olarak test edilebilir**.

### ✅ Kolay Bakım ve Genişleme
- Sistem daha kolay **büyütülebilir**.
- Karmaşık domain mantığı daha kolay **yönetilir**.

---

## 🚫 Ne Zaman Kullanılmamalı?

- Basit **CRUD** uygulamalarda CQRS **gereksiz karmaşıklık** yaratır.
- Küçük ekiplerde, **aşırı ayrım** geliştirme sürecini yavaşlatabilir.

---

## 🧰 CQRS Genellikle Şu Yapılarla Kullanılır:

- 🔄 **MediatR** – (C# tarafında popüler bir CQRS kütüphanesi)
- 🗃️ **Event Sourcing** – (Veri değişikliklerini olay olarak takip eder)
- 🧠 **Domain Driven Design (DDD)** – ile entegre şekilde kullanılır
- ⚙️ **Microservices** – mimarilerinde servis ayrımı için idealdir

---

## 🔚 Özet Karşılaştırma

| Özellik     | Command                   | Query                        |
|-------------|----------------------------|-------------------------------|
| Amaç        | Veriyi değiştirir          | Veriyi okur                   |
| Sonuç       | `void` / durum döner       | Veri döner                    |
| Model       | Yazma modeli               | Okuma modeli                  |
| Özellik     | Yan etkili olabilir        | Yan etkisiz (idempotent) olmalı |

---

> 🧩 **Not:** CQRS, karmaşık iş süreçlerinin yönetimi ve yüksek performans gereksinimleri için güçlü bir çözümdür. Ancak her projede kullanılması gerekmez — doğru yerde, doğru mimariyle kullanılmalıdır.
