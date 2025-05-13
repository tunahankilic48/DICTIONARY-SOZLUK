# MediatR Pattern

**MediatR**, .NET uygulamalarında kullanılan bir **saycı** (mediator) desenidir. Bu desen, uygulama içindeki bileşenlerin birbirleriyle doğrudan iletişim kurmasını engelleyerek, her bileşenin sadece **MediatR** aracılığıyla iletişim kurmasını sağlar. MediatR, **[CQRS](https://github.com/tunahankilic48/DICTIONARY-SOZLUK/blob/main/T%C3%9CRK%C3%87E/CQRS.md)** (Command Query Responsibility Segregation) ve **Event-driven** mimarileriyle uyumlu bir yapıdır, ve özellikle **bağımlılıkların gevşetilmesi** ve **işlemlerin soyutlanması** açısından faydalıdır.

---

### 📖 **MediatR Pattern'ın Temel Amacı**

MediatR deseni, bir **komut** (command) ya da **sorgu** (query) gönderildiğinde, bunu işlemek için doğrudan bir **handler** (işleyici) kullanmanızı sağlar. Bu desende, uygulamanın uygulama mantığı ve veri erişimi gibi işlemler arasındaki bağımlılıkları gevşetmek amacıyla araya bir **mediator** katmanı eklenir.

Temel olarak, **MediatR** aracı, bir **komut** veya **sorgu** iletildiğinde, bu komutun doğru **handler**'a yönlendirilmesini sağlar.

---

### 🔄 **MediatR'ın Temel Bileşenleri**

1. **Request (İstek)**:
   - **Command** veya **Query** olarak iki farklı türde olabilir.
   - **Command**: Sistemde değişiklik yapacak işlemler (örneğin, bir kullanıcı kaydı oluşturmak).
   - **Query**: Sistemde veri alacak işlemler (örneğin, tüm kullanıcıları listelemek).

2. **Handler (İşleyici)**:
   - **Request** (komut veya sorgu) alır ve uygun iş mantığını işler.
   - Her komut veya sorgu için bir **handler** bulunur.

3. **Mediator (Arabulucu)**:
   - **MediatR** kütüphanesinin sağladığı bir bileşendir.
   - **Request** ve **Handler** arasında iletişim sağlar. Yani, bir **Request** gönderildiğinde, bunu ilgili **Handler**'a yönlendirir.

---

### 🧠 **MediatR Pattern'ın Avantajları**

- **Gevşek Bağımlılıklar**:
  - **MediatR**, bileşenler arasındaki doğrudan bağımlılığı ortadan kaldırır. Bir **handler**, başka bir **handler**’a doğrudan referans vermez, sadece **MediatR** aracılığıyla işlem yapılır.

- **Tek Sorumluluk Prensibi (SRP)**:
  - Her **handler** yalnızca belirli bir işlemle ilgilenir. Bu, kodun daha okunabilir ve bakımı kolay olmasını sağlar.

- **Kolay Test Edilebilirlik**:
  - **MediatR** sayesinde her bir komut veya sorgu kendi **handler**'ı ile ayrıldığından, testler her bir **handler** için kolayca yazılabilir.

- **Genişletilebilirlik ve Esneklik**:
  - Yeni komutlar veya sorgular eklemek, mevcut kodu değiştirmeden yapılabilir.

- **Yüksek Kapsülleme**:
  - İşlem ve veri mantığı birbirinden ayrılır. Bu da uygulamanın genişletilmesini ve bakımını kolaylaştırır.

---

### 🚫 **Ne Zaman Kullanılmamalı?**

- **Küçük ve Basit Uygulamalar**:
  - Eğer uygulama çok basitse, **MediatR** deseni ek bir karmaşıklık oluşturabilir.

- **Yüksek Performans Gereksinimleri**:
  - **MediatR**, her istek için ek bir katman ekler. Eğer çok fazla işlem yapılacaksa, bu durum **performans sorunlarına** yol açabilir.

---

### 🔚 **Özet**

**MediatR**, yazılımda **komutlar** ve **sorgular** arasındaki iletişimi **mediator** aracılığıyla sağlamak için kullanılan bir desendir. Bu desen, uygulama bileşenleri arasındaki bağımlılıkları azaltır, test edilebilirliği artırır ve bakım sürecini kolaylaştırır.

#### **Avantajları**:
- Bağımsızlık ve geliştirilebilirlik sağlar.
- Kodun yönetilebilirliğini artırır.
- Gelişmiş test senaryoları sunar.

#### **Dezavantajları**:
- Küçük projelerde **gereksiz karmaşıklık** oluşturabilir.
- **Performans** konusunda dikkatli olunmalıdır.

