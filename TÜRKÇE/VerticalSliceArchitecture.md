# 🧩 Vertical Slice Architecture Nedir?

**Vertical Slice Architecture**, yazılımı geleneksel katmanlara (UI, Business Logic, Data Access) ayırmak yerine, **özelliklere ve işlevselliğe göre** yapılandırmayı hedefleyen modern bir mimari yaklaşımdır. Bu modelde sistem, her bir özelliğin uçtan uca (end-to-end) tüm bileşenlerini içeren bağımsız dilimlere ayrılır.

## 🎯 Örnek: E-Ticaret Sitesi

Bir e-ticaret sitesindeki ürünlerle ilgili sayfayı ele alalım:

- **[Katmanlı Mimari](https://github.com/tunahankilic48/DICTIONARY-SOZLUK/blob/main/T%C3%9CRK%C3%87E/KatmanliMimari.md)**'de: Yapı, `UI`, `Business Logic` ve `Data Access` gibi **teknik sorumluluklara göre katmanlara** ayrılır. Her katman, farklı modüllerin ortak kullanımına hizmet eder.
  
- **Vertical Slice Architecture**'da: Yapı, `GetProducts`, `CreateProduct`, `UpdateProduct` gibi **özellik bazlı (feature-based)** dilimlere ayrılır. Her dilim, UI, iş mantığı ve veri erişimi gibi bileşenleri kendi içinde barındırır ve bağımsız çalışabilir.

---

## 🔍 Vertical Slice Architecture’ın Temel Özellikleri

- **Feature-Based Yapı**: Her özellik (örneğin `GetProducts`, `CreateProduct`) kendi klasöründe yer alır. Bu klasör UI, iş mantığı ve veri erişimini kapsar.
- **Bağımsız Geliştirme**: Her slice, diğerlerinden bağımsız olarak geliştirilebilir, test edilebilir ve deploy edilebilir.
- **Katmanlı Yapıdan Farklıdır**:
  - Katmanlı mimaride kod, **sorumluluklara göre** organize edilir.
  - Vertical Slice Architecture’da kod, **özelliklere göre** bölünür.

---

## ✅ Avantajları

- **Esneklik**: Yeni özelliklerin eklenmesi veya mevcutların değiştirilmesi kolaydır.
- **Anlaşılabilirlik**: Geliştiriciler sadece ilgili slice’a odaklanarak karmaşıklığı azaltabilir.
- **Test Edilebilirlik**: Slice’lar bağımsız test edilebilir; bu durum otomasyon ve entegrasyonu kolaylaştırır.
- **Ölçeklenebilirlik**: Sadece ihtiyaç duyulan slice’lar üzerinde işlem yapılarak sistem daha verimli çalıştırılabilir.
- **Paralel Geliştirme**: Farklı takımlar bağımsız olarak çalışabilir.
- **CQRS Uyumluluğu**: Command ve Query işlemleri ayrı ayrı yönetilebilir.

---

## ❌ Dezavantajları

- Başlangıçta yapıyı öğrenmek zor olabilir.
- Uygulama genelindeki ortak işlemleri (örneğin `logging`, `validation`) yönetmek karmaşık olabilir.
- Slice sayısı arttıkça yönetimi için stratejik planlama gerekir.
- Kod tekrarına neden olabilir (özellikle ortak yapıların her slice içinde kullanılması durumunda).

---

## 🧮 Mimari Karşılaştırma Tablosu

| Özellik / Mimari Yaklaşım       | [Katmanlı Mimari (Layered)](https://github.com/tunahankilic48/DICTIONARY-SOZLUK/blob/main/T%C3%9CRK%C3%87E/KatmanliMimari.md)             | Clean Architecture                         | Vertical Slice Architecture                 |
|----------------------------------|----------------------------------------|---------------------------------------------|----------------------------------------------|
| **Yapılandırma Ölçütü**          | Teknik katmanlara göre (UI, BL, DAL)   | Domain merkezli, soyutlamaya dayalı         | Özellik ve işlevlere göre (feature-based)    |
| **Sorumluluk Ayrımı**            | Katmanlara göre                        | Katmanlara göre ama domain odaklı           | Özellik bazlı, uçtan uca                     |
| **Bağımlılık Yönü**              | UI → Business → Data                   | Dış → İç (Dependency Inversion)             | Slice içinde kendi bağımlılıkları            |
| **Geliştirilebilirlik**          | Katmanlar arası etki olabilir          | Esnek ama yapı karmaşık olabilir            | Yeni özellikler hızlı ve izole eklenebilir   |
| **Test Edilebilirlik**           | Katman bazlı test                      | Yüksek test edilebilirlik                   | Slice bazlı kolay test imkanı                |
| **Kod Organizasyonu**            | Katman klasörleri                      | Katman ama domain odaklı klasörler          | Özellik klasörleri (GetX, CreateY, vs.)      |
| **Uygulama Karmaşıklığı**        | Basit projeler için uygun              | Büyük/kritik sistemler için                 | Her ölçekte kullanılabilir                   |
| **Yaygın Kullanım Alanı**        | Geleneksel kurumsal projeler           | Büyük ve domain odaklı sistemler            | Modern API’ler, mikroservis yaklaşımı        |
| **Avantajı**                     | Öğrenmesi kolay, yaygın                | Domain esnekliği, sürdürülebilirlik         | Hızlı geliştirme, bağımsızlık                |
| **Dezavantajı**                  | Sıkı bağımlılıklar                     | Başlangıçta öğrenme eğrisi yüksek           | Ortak kod tekrarı, slice yönetimi gerekebilir|

---

