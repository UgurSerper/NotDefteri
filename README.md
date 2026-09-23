# 📝 NotDefteri - Gelişmiş WinForms Not Yönetim Uygulaması

![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![.NET](https://img.shields.io/badge/.NET-8.0-5C2D91?style=for-the-badge&logo=.net&logoColor=white)
![SQL Server](https://img.shields.io/badge/MS_SQL_Server-CC292B?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)

**NotDefteri**, C# WinForms ortamında Katmanlı Mimari (Clean Architecture) ve Nesne Yönelimli Programlama (OOP) tasarım kalıplarına uygun olarak geliştirilmiş, dinamik filtreleme ve görsel süre/durum takibi sunan bir masaüstü not alma uygulamasıdır.

---

## ✨ Öne Çıkan Özellikler

* **🔍 Çoklu ve Eş Zamanlı Filtreleme:**
  * Metin Arama (Başlık/İçerik), Kategori ve Süre filtresi birbiriyle uyumlu biçimde **aynı anda** çalışır.
  * Kart nesneleri silinip yeniden oluşturulmadan `.Visible` toggle yöntemiyle gizlendiği için UI seçim durumları korunur.
* **🎭 State Pattern (Durum Tasarım Kalıbı):**
  * Kartların tıklanma ve tamamlanma durumları (`VarsayilanDurum`, `SeciliDurum`, `TamamlandiDurum`) `IKartDurumu` arayüzü üzerinden esnek bir state yapısıyla yönetilir.
* **⏱️ Enum Tabanlı Süre & Pastel Renk Yönetimi:**
  * `SureEnum` (`Kisa`, `Orta`, `Uzun`) değerleri veritabanında `tinyint` olarak saklanır.
  * `SureEnumExtensions` ile renk ve font kararları tamamen enum türü üzerine kapsüllenmiştir (`Encapsulation`).
* **👤 Kullanıcı ve Oturum Yönetimi:**
  * Kullanıcı girişi (`LoginForm`), aktif kullanıcı oturum takibi (`Oturum`) ve kullanıcıya özel not izolasyonu sağlanır.
* **🔒 Katmanlı Servis Mimarisi:**
  * Servis katmanı (`Servisler`) ile veritabanı işlemleri arayüzlerden (`Arayuzler`) tamamen ayrılmıştır. SQL Injection'a karşı parametreli sorgular kullanılır.

---

## 📁 Proje Mimarisi

```text
NotDefteri/
│
├── 📂 Arayuzler/               # Servis sözleşmeleri (Interface)
│   ├── IKategoriServis.cs
│   ├── IKullaniciServis.cs
│   └── IVeritabaniServis.cs
│
├── 📂 Durumlar/                # State Pattern (Kart UI durum yönetimi)
│   ├── IKartDurumu.cs
│   ├── SeciliDurum.cs
│   ├── TamamlandiDurum.cs
│   └── VarsayilanDurum.cs
│
├── 📂 Enum/                    # Enum tanımları ve Genişletme Metotları
│   ├── SureEnum.cs
│   └── SureEnumExtensions.cs
│
├── 📂 Modeller/                # Veri modelleri (Domain Entities)
│   ├── Kategori.cs
│   ├── Kullanici.cs
│   └── Not.cs
│
├── 📂 Servisler/               # İş mantığı ve Veritabanı servisleri
│   ├── KategoriServis.cs
│   ├── KullaniciServis.cs
│   └── VeritabaniServis.cs
│
├── 🖼️ AnaForm.cs               # Ana liste, arama ve filtreleme ekranı
├── ⚙️ AyarlarForm.cs            # Kategori ve sistem ayarları
├── 🔐 LoginForm.cs              # Kullanıcı giriş ekranı
├── ✏️ NotEkleDuzenleForm.cs    # Not ekleme ve güncelleme formu
├── 🧩 NotKarti.cs              # Custom UserControl kart bileşeni
├── 🔑 Oturum.cs                # Aktif kullanıcı oturum nesnesi
└── 🚀 Program.cs               # Uygulama başlangıç noktası

🛠️ Kullanılan Teknolojiler ve Desenler
Dil / Platform: C# / .NET 8.0 Windows Forms

Veritabanı: Microsoft SQL Server

Tasarım Kalıpları: State Pattern, Service Layer Pattern, Dependency Inversion

OOP Prensipleri: Encapsulation, Extension Methods, Polymorphism
