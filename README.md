# NotDefteri

C# ve Windows Forms kullanılarak geliştirdiğim kişisel not yönetim uygulaması.

## Özellikler

* Kullanıcı girişi
* Not oluşturma
* Not düzenleme
* Not silme
* Notları listeleme
* Kategori oluşturma
* Kategori düzenleme
* Kategori silme
* Kullanıcı adı değiştirme
* Şifre değiştirme
* SQL Server üzerinde veri saklama

## Kullanılan Teknolojiler

* C#
* .NET
* Windows Forms
* SQL Server
* ADO.NET
* Git / GitHub

## Mimari

Projede veritabanı işlemleri servisler üzerinden yönetilmektedir.

* Interface kullanımı
* Dependency Injection
* OOP prensipleri
* Katmanlı yapıya uygun servis ayrımı

## Veritabanı

Uygulama SQL Server kullanmaktadır.

Temel tablolar:

* `Kullanici`
* `Kategori`
* `Not`

## Proje Durumu

Bu proje benim C#, SQL Server, OOP ve Windows Forms öğrenme sürecimde geliştirdiğim **V1 sürümüdür**.

İlerleyen aşamada projeyi ASP.NET Core Web API kullanarak geliştirmeyi ve istemci ile backend'i birbirinden ayırmayı planlıyorum.

## Not

Bu sürüm yerel SQL Server üzerinde çalışacak şekilde geliştirilmiştir. Connection string içerisindeki `.\SQLEXPRESS` ifadesi uygulamanın çalıştığı bilgisayardaki SQL Server Express instance'ını belirtir.
