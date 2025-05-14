# API Gateway Nedir?

**API Gateway**, **[mikroservis mimarilerinde](https://github.com/tunahankilic48/DICTIONARY-SOZLUK/blob/main/T%C3%9CRK%C3%87E/MikroservisMimarisi.md)** istemciler (clients) ile arka uç servisler (backend services) arasında bir **tek giriş noktası (single entry point)** sağlayan bir bileşendir. Gelen istekleri alır, doğrular, yönlendirir, dönüştürür ve sonuçları istemciye iletir.

---

## 🔧 API Gateway Ne İşe Yarar?

- Tüm API isteklerini merkezi olarak karşılar
- İstekleri uygun servislere yönlendirir (Routing)
- Kimlik doğrulama ve yetkilendirme uygular (Authentication/Authorization)
- **Rate limiting**, throttling, logging ve monitoring işlemleri yapar
- Yanıtları önbelleğe alabilir (Caching)
- Farklı servislerden gelen verileri birleştirebilir (Response Aggregation)
- Protokol dönüşümü yapabilir (ör. HTTP → gRPC)

---

## 🎯 Neden Kullanılır?

- **Merkezi Erişim**: Tüm mikroservisler tek bir uç noktadan erişilebilir olur
- **Güvenlik**: JWT, OAuth gibi güvenlik protokolleri merkezi şekilde uygulanabilir
- **Soyutlama**: İstemciler servislerin iç yapısını bilmek zorunda kalmaz
- **Performans**: Önbellekleme, rate limit ve yük dengeleme ile iyileştirme sağlar

---

## 🚧 Dezavantajları

- **Tek hata noktası** olabilir (redundancy ile önlenebilir)
- **Performans darboğazı** oluşturabilir (yüksek trafik durumlarında)
- Ek bir yapılandırma ve bakım yükü getirir

---

## ✅ Avantajları

- Güvenlik politikaları merkezi uygulanabilir
- Tüm API yönetimi tek yerden izlenebilir
- Mikroservisleri dış dünyadan izole eder
- Ölçeklenebilirlik ve bakım kolaylığı sağlar

---

## 📌 Sonuç

**API Gateway**, mikroservis tabanlı mimarilerde kritik bir rol oynar. İstemciler ile servisler arasında tüm trafiği yöneten merkezi bir nokta sunar. Güvenlik, performans ve yönetilebilirlik açısından güçlü avantajlar sağlar. Ancak tek hata noktası olmaması ve iyi yapılandırılması önemlidir.

