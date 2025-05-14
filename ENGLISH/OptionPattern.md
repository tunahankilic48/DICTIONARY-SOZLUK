
# What is the Options Pattern? (ASP.NET Core)

The **Options Pattern** is a design pattern used in ASP.NET Core applications to manage configuration settings through Plain Old CLR Objects (POCOs). This pattern allows you to bind configuration data from files like `appsettings.json` directly to objects for easy and maintainable access.

---

## 🎯 Purpose

- Manage configuration settings centrally
- Improve code testability and maintainability
- Cleanly inject configuration dependencies into applications

---

## 🧱 Basic Usage

### 1. `appsettings.json` Example

```json
{
  "MySettings": {
    "SiteName": "E-Commerce",
    "MaxItems": 100
  }
}
```

### 2. Configuration Class (POCO)

```csharp
public class MySettings
{
    public string SiteName { get; set; }
    public int MaxItems { get; set; }
}
```

### 3. Binding in `Program.cs` or `Startup.cs`

```csharp
builder.Services.Configure<MySettings>(
    builder.Configuration.GetSection("MySettings"));
```

### 4. Usage via Dependency Injection

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

## 💡 Alternative Interfaces

| Interface               | Description |
|-------------------------|-------------|
| `IOptions<T>`           | Singleton, default usage |
| `IOptionsSnapshot<T>`   | Scoped — refreshed per HTTP request |
| `IOptionsMonitor<T>`    | Dynamic — auto-updates when configuration changes |

---

## ✅ Advantages

- **Type safety**: Access settings via strongly-typed objects.
- **Centralized management**: Store all settings in `appsettings.json` or similar files.
- **Testability**: Configuration classes can easily be mocked.
- **Improved readability**: Avoids using `Configuration["Key"]` string-based access.

---

## 🔚 Conclusion

The Options Pattern simplifies configuration management and provides a safer, more testable, and maintainable structure for software projects. It's especially recommended for medium to large-scale ASP.NET Core applications.
