
# Option Pattern Nedir? (ASP.NET Core)

**Option Pattern**, ASP.NET Core uygulamalarında yapılandırma (configuration) ayarlarını sınıflar (POCO sınıfları) aracılığıyla yönetmek için kullanılan bir tasarım desenidir. Bu desen, `appsettings.json` gibi konfigürasyon dosyalarındaki verilerin doğrudan nesnelere bağlanarak kolayca erişilmesini ve daha sürdürülebilir bir yapı kurulmasını sağlar.

---

## 🎯 Amaç

- Yapılandırma ayarlarını merkezi bir yerden yönetmek
- Kodun test edilebilirliğini ve sürdürülebilirliğini artırmak
- Konfigürasyon bağımlılıklarını temiz ve güvenli şekilde uygulamalara enjekte etmek

---

## 🧱 Temel Kullanım

### 1. `appsettings.json` Örneği

```json
{
  "MySettings": {
    "SiteName": "E-Commerce",
    "MaxItems": 100
  }
}
```

### 2. Ayar Sınıfı (POCO)

```csharp
public class MySettings
{
    public string SiteName { get; set; }
    public int MaxItems { get; set; }
}
```

### 3. Bağlama (`Program.cs` veya `Startup.cs`)

```csharp
builder.Services.Configure<MySettings>(
    builder.Configuration.GetSection("MySettings"));
```

### 4. Kullanımı (Dependency Injection ile)

```csharp
public class HomeController : Controller
{
    private readonly MySettings _settings;

    public HomeController(IOptions<MySettings> options)
    {
        _settings = options.Value;
    }

    public IActionResult Index()
    {
        ViewBag.SiteName = _settings.SiteName;
        return View();
    }
}
```

---

## 💡 Alternatif Kullanımlar

| Arayüz              | Açıklama |
|---------------------|----------|
| `IOptions<T>`        | Singleton, varsayılan kullanım şekli |
| `IOptionsSnapshot<T>`| Scoped — her HTTP isteği için yeniden okunur |
| `IOptionsMonitor<T>` | Dinamik — ayar değiştiğinde otomatik güncellenir |

---

## ✅ Avantajları

- **Tip güvenliği sağlar**: Doğrudan nesne üzerinden erişim.
- **Merkezi yönetim**: Tüm ayarları `appsettings.json` veya benzeri dosyalarda tutabilirsiniz.
- **Test edilebilirlik**: Ayar sınıfları kolayca taklit (mock) edilebilir.
- **Kod okunabilirliğini artırır**: `Configuration["Key"]` gibi string ifadelerden kaçınılır.

---

## 🔚 Sonuç

Option Pattern, yapılandırma yönetimini sadeleştirerek yazılım projelerinde daha güvenli, test edilebilir ve sürdürülebilir bir yapı sağlar. ASP.NET Core uygulamaları geliştirirken özellikle orta ve büyük ölçekli projelerde tercih edilmesi önerilir.
