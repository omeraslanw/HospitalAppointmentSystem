# Hastane Randevu Sistemi

<p align="center">
  <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/.NET%20Framework-512BD4?style=for-the-badge&logo=.net&logoColor=white" alt=".NET Framework">
  <img src="https://img.shields.io/badge/MS%20SQL%20Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white" alt="MS SQL Server">
  <img src="https://img.shields.io/badge/Entity%20Framework-4E267A?style=for-the-badge" alt="Entity Framework">
</p>

## Açıklama

Bu proje, bir hastane randevu sistemi uygulamasıdır. Hastalar kendi randevularını görüntüleyebilir. Sekreterler sistem üzerinden duyuru, doktor, randevu ekleme, çıkarma, güncelleme, listeleme işlemlerini yapabilir. Doktorlar ise duyuruları görüntüleyebilir ve aktif hasta randevularını kontrol edebilir.

## Kullanılan Teknolojiler

- **Platform:** .NET Framework 4.7.2
- **Programlama Dili:** C#
- **Veritabanı:** Microsoft SQL Server
- **ORM (Object-Relational Mapping):** Entity Framework 6 (Database First)
- **Arayüz:** Windows Forms (WinForms)
- **Geliştirme Ortamı:** Visual Studio 2022 (veya kullandığınız sürüm)

## Kurulum Anlatımı

Projeyi yerel makinenizde çalıştırmak için aşağıdaki adımları izleyin.

### Ön Gereksinimler

- Visual Studio (2019, 2022 veya üstü)
- .NET Framework (Proje ile uyumlu versiyon, genellikle Visual Studio ile birlikte gelir)
- Microsoft SQL Server (Express, Developer veya tam sürüm)
- SQL Server Management Studio (SSMS) (Tavsiye edilir)

### Kurulum Adımları

1.  **Projeyi Klonlayın veya İndirin:**
    ```sh
    git clone https://github.com/omeraslanw/HospitalAppointmentSystem.git
    ```

2.  **Veritabanını Script ile Oluşturun:**
    1.  SQL Server Management Studio'yu (SSMS) açın.
    2.  Proje klasörü içindeki `Database` altındaki `.sql` uzantılı script dosyasını SSMS'de açın.
    3.  `Execute` butonuna basarak script'i çalıştırın. Bu işlem, gerekli veritabanını ve tabloları sizin için oluşturacaktır.

3.  **SQL Bağlantısını Kod İçinde Yapılandırın:**
    Bu projede bağlantı bilgileri, merkezi bir yapılandırma dosyası yerine doğrudan kod içindeki `SqlConn` sınıfından yönetilmektedir.
    1.  Visual Studio'da Solution Explorer panelinden `SqlConn.cs` dosyasını bulun ve açın.
    2.  Aşağıdaki satırda bulunan bağlantı dizesini (`connection string`) kendi SQL Server bilgilerinize göre güncelleyin:

        ```csharp
        // SqlConn.cs dosyasındaki connection() metodu
        public SqlConnection connection()
        {
            // BU SATIRI KENDİ BİLGİLERİNİZE GÖRE DÜZENLEYİN:
            SqlConnection conn = new SqlConnection(@"Data Source=SUNUCU_ADINIZ;Initial Catalog=DbName;Integrated Security=True");
            conn.Open();
            return conn;
        }
        ```
        -   **`SUNUCU_ADINIZ`**: Kendi SQL Server sunucu adınızla değiştirin (örn: `.` veya `DESKTOP-ABC\SQLEXPRESS`).
        -   **`Initial Catalog`**: Bu değerin, 2. adımda oluşturduğunuz veritabanı adıyla (`ProjectDb`) aynı olduğundan emin olun.
4.  **Projeyi Çalıştırın:**
    1.  Visual Studio'da projeyi (`.sln` dosyası) açın.
    2.  Gerekli NuGet paketlerinin yüklendiğinden emin olun (Genellikle proje açıldığında otomatik yüklenir).
    3.  Projeyi derleyin (`Build > Build Solution`).
    4.  `Start` butonuna basarak uygulamayı başlatın.

## Uygulama Görselleri

<p align="center">
  <b>Giriş Ekranı</b><br>
  <img src="https://github.com/omeraslanw/HospitalAppointmentSystem/blob/master/girissecim.png" alt="Uygulama Giriş Ekranı" width="600"/>
</p>

<p align="center">
  <b>Branş Ekleme</b><br>
  <img src="https://github.com/omeraslanw/HospitalAppointmentSystem/blob/master/bransekle.png" alt="Branş Ekle" width="600"/>
</p>

<p align="center">
  <b>Doktor Detay Ekranı</b><br>
  <img src="https://github.com/omeraslanw/HospitalAppointmentSystem/blob/master/doktordetay.png" alt="Doktor Detay" width="600"/>
</p>

<p align="center">
  <b>Doktor Ekleme Ekranı</b><br>
  <img src="https://github.com/omeraslanw/HospitalAppointmentSystem/blob/master/doktorekle.png" alt="Doktor Ekleme Ekranı" width="600"/>
</p>

<p align="center">
  <b>Doktor Paneli</b><br>
  <img src="https://github.com/omeraslanw/HospitalAppointmentSystem/blob/master/doktorpaneli.png" alt="Doktor Paneli" width="600"/>
</p>

<p align="center">
  <b>Duyuru İşlemleri</b><br>
  <img src="https://github.com/omeraslanw/HospitalAppointmentSystem/blob/master/duyurular.png" alt="Duyuru İşlemleri" width="600"/>
</p>

<p align="center">
  <b>Hasta Detayları</b><br>
  <img src="https://github.com/omeraslanw/HospitalAppointmentSystem/blob/master/hasta%20detay.png" alt="Hasta Ekranı" width="600"/>
</p>

<p align="center">
  <b>Randevu Paneli</b><br>
  <img src="https://github.com/omeraslanw/HospitalAppointmentSystem/blob/master/randevular.png" alt="Randevu Paneli" width="600"/>
</p>

<p align="center">
  <b>Sekreter İşlemleri</b><br>
  <img src="https://github.com/omeraslanw/HospitalAppointmentSystem/blob/master/sekreterpaneli.png" alt="Sekreter İşlemleri" width="600"/>
</p>
