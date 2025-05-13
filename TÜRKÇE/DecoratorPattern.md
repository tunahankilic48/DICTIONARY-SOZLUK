# 🎨 Decorator Pattern

## 📌 Tanım
Decorator Pattern, bir nesnenin yapısını değiştirmeden ona dinamik olarak yeni sorumluluklar veya işlevsellikler eklemeye yarayan yapısal bir tasarım desenidir.

---

## 🎯 Amaç
Mevcut bir sınıfa miras almadan yeni davranışlar kazandırmak ve bu davranışları esnek biçimde yönetmek.

---

## 🧱 Yapı

- **Component**: Ortak arayüz veya soyut sınıf.
- **ConcreteComponent**: Genişletilecek gerçek sınıf.
- **Decorator**: `Component` arayüzünü uygulayan ve içinde bir `Component` nesnesi tutan soyut sınıf.
- **ConcreteDecorator**: Davranışları genişleten sınıflar; `Decorator` sınıfını genişletir.

---

## 🔧 Kullanım Durumları

- Çalışma zamanında bir nesneye özellik/davranış eklenmesi gerekiyorsa.
- Kalıtım yoluyla davranış eklemek sınıf sayısını arttırıyorsa.
- Davranışların farklı kombinasyonlarla uygulanması isteniyorsa.

---

## ✅ Avantajlar

- Açık/Kapalı Prensibi'ne uygundur.
- Bileşim yoluyla esneklik sağlar.
- Sınıfı değiştirmeden yeni işlevsellik eklenebilir.

---

## ❌ Dezavantajlar

- Çok sayıda dekoratör sınıfı oluşabilir.
- Yapının karmaşıklığı artabilir.
- Katmanlar arasında takip zor olabilir.

---

## 🔄 İlgili Prensipler

- **[Open/Closed Principle](https://github.com/tunahankilic48/DICTIONARY-SOZLUK/blob/main/T%C3%9CRK%C3%87E/SOLIDPrensipleri.md)**
- **[Single Responsibility Principle](https://github.com/tunahankilic48/DICTIONARY-SOZLUK/blob/main/T%C3%9CRK%C3%87E/SOLIDPrensipleri.md)**
- **Composition Over Inheritance**
