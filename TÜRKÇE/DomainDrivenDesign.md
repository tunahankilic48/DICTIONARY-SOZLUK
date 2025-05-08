# 📘 Domain-Driven Design (DDD) Nedir?

**Domain-Driven Design (DDD)**, yazılım projelerinin merkezine gerçek dünyadaki iş problemlerini yerleştiren bir geliştirme yaklaşımıdır. Bu yaklaşım, yazılımın iş ihtiyaçlarına doğrudan karşılık verecek şekilde tasarlanması gerektiğini savunur.

Burada “**domain**”, çözülmek istenen iş probleminin kendisidir.  
Örneğin: “Bir aracın ortalama yakıt tüketimini hesaplamak” bir domain olabilir. Ancak bu domain’in daha **net** ve **sınırları belirgin** olması gerekir.  
Daha sağlıklı bir tanım şöyle olabilir:  
➡️ “Kamyonların ortalama yakıt tüketimini hesaplamak” veya  
➡️ “Yolcu uçaklarının ortalama yakıt tüketimini hesaplamak”.

Bu şekilde sınırları net çizilmiş iş problemlerine **domain** denir.  
**DDD**, bu domain'e uygun bir model geliştirerek yazılım ile iş ihtiyaçlarını aynı zeminde buluşturur.

---

# 🧱 Temel Kavramlar

## 1. Domain (Alan)
Yazılımın çözmeyi hedeflediği iş problemidir.  
**Örnek:** Bankacılık sisteminde domain, finansal işlemlerdir.

## 2. Model
Domain’i temsil eden kavramsal yapıdır.  
Sınıflar, ilişkiler, kurallar bu modeli oluşturur.

## 3. Ubiquitous Language (Ortak Dil)
Yazılımcılar ve iş birimlerinin ortaklaşa belirlediği, her yerde (kodda, dökümanda, toplantılarda) aynı şekilde kullanılan dildir.

## 4. Bounded Context (Sınırlı Bağlam)
Bir modelin geçerli olduğu bağlamsal sınırdır.  
Büyük sistemlerde her bounded context, bağımsız olarak tanımlanabilir ve kendi modeline sahip olabilir.

## 5. Entity (Varlık)
Kendine özgü kimliği olan ve zaman içinde durumu değişebilen nesnelerdir.  
**Örnek:** Kullanıcı, Sipariş, Ürün.

## 6. Value Object (Değer Nesnesi)
Kimliği olmayan, yalnızca değeriyle tanımlanan nesnelerdir.  
**Örnek:** Para, Adres, Koordinat.

## 7. Aggregate
İlişkili entity ve value object’lerin mantıksal kümesidir.  
Dış dünyadan yalnızca **aggregate root** üzerinden erişim sağlanır.

## 8. Repository
Veri erişimini soyutlayan katmandır.  
Uygulama doğrudan veritabanına değil, repository aracılığıyla veriyle iletişim kurar.

---

# 🧭 Stratejik Tasarım (Strategic Design)

Stratejik tasarım, yazılımın büyük resmiyle ilgilenir. Domain’i parçalara ayırır, bu parçaların sınırlarını çizer ve aralarındaki ilişkileri tanımlar.

### 🔹 Temel Kavramlar:

- **Bounded Context:**

- **Context Map:**  
  Farklı bounded context’ler arasındaki ilişkileri ve iletişim biçimlerini haritalar.

- **Ubiquitous Language:**

---

# 🛠️ Taktiksel Tasarım (Tactical Design)

Taktiksel tasarım, belirli bir bounded context içerisindeki domain modelinin detaylarına odaklanır. Yazılımın iç mimarisi bu düzeyde şekillenir.

### 🔸 Temel Kavramlar:

- **Entity**
- **Value Object**
- **Aggregate**
- **Repository**
- **Domain Service:** Herhangi bir entity’ye ait olmayan, domain’e özel iş kurallarını barındıran hizmetler.  
- **Factory:** Karmaşık nesneleri oluşturmak için kullanılan yapı.

---

# 🎯 Genel Karşılaştırma Tablosu

| Tasarım Seviyesi       | Amacı                                               | Ana Kavramlar                                              |
|------------------------|-----------------------------------------------------|-------------------------------------------------------------|
| **Stratejik Tasarım**  | Sistemin büyük resmini ve yapısal sınırlarını çizmek| Bounded Context, Context Map, Ubiquitous Language           |
| **Taktiksel Tasarım**  | Domain modelini detaylandırmak                      | Entity, Value Object, Aggregate, Repository, Service, Factory|
