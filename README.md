# CurrencyTracker – Döviz Takip Konsol Uygulaması

Bu proje, anlık döviz kurlarını harici bir API (`frankfurter.app`) üzerinden çekip konsol ekranında listeleyen, filtreleyen ve istatistiksel analiz yapan bir **C# konsol uygulamasıdır**.

---

## 👨‍💻 Proje Sahibi

| Bilgi | Değer |
| :--- | :--- |
| **Ad Soyad** | Samet ERDOĞAN |
| **Öğrenci Numarası** | 20230108039 |
| **Bölüm** | Bilgisayar Programcılığı |
| **Ders Adı** | Görsel Programlama |
| **Ders Kodu** | BIP2033 |
| **Öğretim Görevlisi** | Emrah SARIÇİÇEK |
| **Teslim Tarihi** | 13/01/2026 |

---

## 📌 Proje Hakkında

Bu **C#** uygulaması, `System.Net.Http` kütüphanesini kullanarak **HTTP GET** isteği yapar ve **Türk Lirası (TRY)** bazlı döviz verilerini alır.

Alınan veriler `System.Text.Json` ile `CurrencyResponse` modeline deserialize edilir ve LINQ işlemleri için bellekte `List<Currency>` formatında tutulur. Uygulama, **LINQ (Language Integrated Query)** yapısını yoğun bir şekilde kullanarak veriler üzerinde sorgulama, sıralama ve analiz işlemleri gerçekleştirir.

### Kullanılan Veri Kaynağı:

* **API Sağlayıcısı:** Frankfurter API (Open Source)
* **Endpoint:** `https://api.frankfurter.app/latest?from=TRY`
* **Veri Yapısı:** Base (Kaynak Para Birimi) ve Rates (Döviz Kurları Sözlüğü)

---

## 🚀 Özellikler

| İşlem | Açıklama |
| :--- | :--- |
| **Tüm Dövizleri Listele** | API'den çekilen tüm döviz çiftlerini (Kod ve Kur değeri) ekrana yazdırır. (LINQ `Select`) |
| **Koda Göre Ara** | Kullanıcının girdiği döviz kodunu (Örn: USD, EUR) büyük/küçük harf duyarsız olarak arar. (LINQ `Where`) |
| **Değere Göre Filtrele** | Belirli bir kur değerinden (Örn: 0.50) büyük olan tüm para birimlerini listeler. (LINQ `Where`) |
| **Sıralama İşlemi** | Dövizleri kur değerine göre **Artan** veya **Azalan** şekilde sıralar. (LINQ `OrderBy`, `OrderByDescending`) |
| **İstatistiksel Özet** | Toplam döviz sayısı, en yüksek kur, en düşük kur ve ortalama kur bilgisini hesaplar. (LINQ `Count`, `Max`, `Min`, `Average`) |

---

## ⚙️ Gereksinimler

* **.NET SDK 8.0** veya üzeri
* **Tavsiye Edilen ve Geliştirilen IDE:** Visual Studio 2022 
* **Kütüphaneler:** `System.Net.Http`, `System.Text.Json`, `System.Linq`

---

## ▶️ Nasıl Çalıştırılır?

1.  Bu repoyu bilgisayarınıza **indirin**.
2.  Projeyi **Visual Studio 2022** içerisinde açın.
3.  `Program.cs` dosyasının başlangıç projesi olduğundan emin olun.
4.  İnternet bağlantınızın aktif olduğunu kontrol edin (API isteği için gereklidir).
5.  Projeyi çalıştırın (`F5` veya `Ctrl+F5`).

### ✅ Örnek Kullanım Senaryosu

```text
Veriler API'den alınıyor, lütfen birkaç saniye bekleyin...

===== CurrencyTracker =====
1. Tüm dövizleri listele
2. Koda göre döviz ara
3. Belirli bir değerden büyük dövizleri listele
4. Dövizleri değere göre sırala
5. İstatistiksel özet göster
0. Çıkış
Seçiminiz Lütfen: 5

--- İstatistiksel Özet ---
Toplam Döviz Sayısı: 32
En Yüksek Kur    : 4.1523
En Düşük Kur     : 0.0268
Ortalama Kur     : 0.8942

===== CurrencyTracker =====
1. Tüm dövizleri listele
...
Seçiminiz Lütfen: 2
Aranacak Döviz Kodunu yazınız (Örnek: USD): eur
Bulundu -> EUR: 0.0271
