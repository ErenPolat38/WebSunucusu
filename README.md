# Java ile Sıfırdan Web Sunucusu

Bu proje, üçüncü parti kütüphaneler kullanılmadan, yalnızca Java'nın standart `java.net` ve `java.io` kütüphaneleri kullanılarak geliştirilmiş basit bir HTTP sunucusudur. Yazılım Mühendisliği dersi kapsamında, ağ programlamanın temel prensiplerini ve HTTP protokolünün işleyişini anlamak amacıyla oluşturulmuştur.

## 🚀 Projenin Amacı

Projenin temel hedefi, belirli bir portu dinleyen ve gelen HTTP GET isteklerine önceden tanımlanmış bir HTML sayfası ile yanıt veren bir sunucu uygulaması yazmaktır. Bu sayede `Socket`, `ServerSocket` gibi temel ağ programlama sınıflarının kullanımı ve HTTP yanıt başlıklarının (headers) yapısı pratik olarak öğrenilmiştir.

## ✨ Özellikler

  - **Bağımlılıksız:** Proje, ek bir kütüphane veya framework gerektirmez. Sadece Java Geliştirme Kiti (JDK) yeterlidir.
  - **Tek İş Parçacıklı (Single-Threaded):** Sunucu, basitliği korumak amacıyla gelen istekleri sıralı olarak işler.
  - **Statik Yanıt:** Sunucu, her isteğe aynı statik HTML sayfasını sunar.
  - **Kişisel Bilgi Sayfası:** Sunulan HTML sayfası, proje sahibinin adını, soyadını, öğrenci numarasını ve kısa bir biyografisini içerir.

## 🛠️ Kullanılan Teknolojiler

  - **Dil:** Java
  - **Temel Kütüphaneler:** `java.net.*`, `java.io.*`
  - **İstemci Tarafı:** HTML5 & CSS3

## 📋 Gereksinimler

  - Java Geliştirme Kiti (JDK) 8 veya üstü.

## ⚙️ Kurulum ve Çalıştırma

Projeyi yerel makinenizde çalıştırmak için aşağıdaki adımları izleyin:

1.  **Depoyu Klonlayın:**

    ```bash
    git clone https://github.com/kullanici-adiniz/proje-adiniz.git
    ```

2.  **Dizine Gidin:**

    ```bash
    cd proje-adiniz
    ```

3.  **Java Dosyasını Derleyin:**
    Komut satırını veya terminali açın ve aşağıdaki komutu çalıştırın. (Dosya adının `ErenPolatWebServer.java` olduğunu varsayıyorum)

    ```bash
    javac ErenPolatWebServer.java
    ```

4.  **Sunucuyu Başlatın:**
    Derleme başarılı olduktan sonra sunucuyu başlatmak için aşağıdaki komutu çalıştırın.

    ```bash
    java ErenPolatWebServer
    ```

5.  **Sonucu Görüntüleyin:**
    Komut satırında "Sunucu 1989 portunda başlatıldı..." mesajını gördükten sonra, favori web tarayıcınızı açın ve adres çubuğuna gidin:

    ```
    http://localhost:1989
    ```

## 📝 Kodun Yapısı ve Açıklaması

  - **`ErenPolatWebServer.java`**: Projenin ana ve tek sınıfıdır.
      - **`main` metodu**: Uygulamanın giriş noktasıdır.
      - **`ServerSocket`**: `1989` portunu dinleyerek gelen bağlantı isteklerini bekler.
      - **`while(true)` döngüsü**: Sunucunun sürekli çalışmasını ve birden fazla isteği art arda kabul etmesini sağlar.
      - **`socket.accept()`**: Bir istemci (tarayıcı) bağlandığında, bu istemciye özel bir `Socket` nesnesi oluşturur.
      - **HTML & HTTP Yanıtı**: Tarayıcıya gönderilecek olan HTML içeriği ve HTTP başlıkları (`HTTP/1.1 200 OK`, `Content-Type` vb.) bir `String` olarak oluşturulur.
      - **`OutputStream`**: Oluşturulan yanıt, `Socket`'in çıkış akışı üzerinden byte'lara dönüştürülerek istemciye gönderilir.
      - **`try-catch-finally`**: Ağ işlemlerinde oluşabilecek hataları yönetir ve her durumda `Socket` bağlantısının güvenli bir şekilde kapatılmasını sağlar.

## 🎓 Projeden Çıkarılan Dersler

Bu proje sayesinde aşağıdaki temel yetkinlikler kazanılmıştır:

  - TCP/IP protokolü üzerinde soket programlamanın temelleri.
  - Java'da I/O (Giriş/Çıkış) akışlarının yönetimi.
  - HTTP protokolünün basit yapısı (istek/yanıt döngüsü, başlıklar).
  - Hata yönetimi (`Exception Handling`) ve kaynakların doğru şekilde kapatılmasının önemi.

-----

 
