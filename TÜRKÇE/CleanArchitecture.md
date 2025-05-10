# 🧱 Clean Architecture Nedir?

**Clean Architecture**, yazılım projelerinde **esneklik, sürdürülebilirlik ve test edilebilirlik** sağlayan bir mimari yaklaşımdır. Katmanlı mimariyi temel alır; ancak onu daha disiplinli hale getirerek, **bağımlılıkların yönünü ve yapısını kesin kurallara bağlar**.

> 🎯 **Ana felsefe:** Uygulama, içteki çekirdek kurallardan dıştaki teknik detaylara doğru inşa edilir; **iç katmanlar dış katmanlara asla bağımlı değildir.**

> 🔁 **Bağımlılıklar sadece dıştan içe doğru ilerler.**  
> Her katman yalnızca kendisinden daha içte olan katmanı referans alabilir.
---

# 📚 Clean Architecture Katmanları

## 1️⃣ Domain (Entities)
- Uygulamanın kalbidir.
- Temel iş kurallarını ve nesneleri içerir.
- Diğer tüm katmanlardan bağımsızdır.

## 2️⃣ Application (Use Cases)
- Uygulama iş mantığını yönetir.
- “Ne yapılacak?” sorusunu yanıtlar.
- Domain katmanını kullanır ama diğer dış katmanlara bağımlı değildir.

## 3️⃣ Interface Adapters
- Arayüzler ile uygulama mantığı arasında köprü kurar.
- Controller, Presenter, Mapper gibi bileşenleri barındırır.
- Verileri uygun biçime dönüştürür.

## 4️⃣ Frameworks & Drivers (UI, DB, Tools)
- En dış katmandır.
- Web framework’leri, veritabanları, API istemcileri bu katmanda yer alır.
- Kolay değiştirilebilir olmalıdır.

---

# 🚦 Bağımlılık Kuralı: Tek Yönlü ve Katı

> **Clean Architecture’ın en önemli prensibi:**  
>  
> **İç katmanlar, dış katmanlara asla bağımlı olamaz.**  
>  
> Bu yapı sayesinde;
> - Değişim dıştan içe etkisiz kalır.
> - Çekirdek iş kuralları korunur.
> - Test ve bakım kolaylaşır.

| ✅ İzin Verilen | ❌ Yasak |
|----------------|----------|
| UI → Application | Domain → Infrastructure |
| Application → Domain | Application → UI |
| Infrastructure → Application | Domain → Application |

---

# ✅ Clean Architecture’ın Avantajları

| Avantaj             | Açıklama |
|---------------------|----------|
| 🔧 **Modülerlik**     | Katmanlar izole olduğu için değişiklik diğerlerini etkilemez. |
| 🧪 **Test Edilebilirlik** | İş mantığı dış sistemlerden bağımsız test edilebilir. |
| 🔒 **Bağımlılık Kontrolü** | Bağımlılık yönü net ve tek yönlüdür. |
| 📖 **Okunabilirlik**     | Sorumluluklar net bir şekilde ayrıldığı için kod anlaşılırdır. |
| 🏗️ **Sürdürülebilirlik** | Büyük projelerde bile teknik borç azalır. |
