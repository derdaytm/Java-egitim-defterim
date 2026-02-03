## Metodlar

### Metod Nedir?
Metod, Java’da **belirli bir işlemi yapan kod bloğudur**.  
Bir kez tanımlanır ve **istendiği kadar tekrar kullanılabilir**.

### Ne İşe Yarar?
- Kodun tekrarını önler.  
- İşlemleri **modüller halinde organize eder**.  
- Daha **temiz, okunabilir ve yönetilebilir** kod yazmayı sağlar.  
- Parametre alabilir ve değer döndürebilir.  

### Temel Yapı
```java
erişimBelirleyici ekstraÖzellikler geriDönüşTipi metodAdı(parametreler) {
    // yapılacak işlemler
}
```

- **Erişim Belirleyici:** Metodun hangi sınıflardan erişilebileceğini belirler.
    - **public:** Metoda her yerden erişilebilir.
    - **private:** Metoda sadece tanımlandığı sınıf içinden erişilebilir.
    - **protected:** Metoda aynı paket içinden ve alt sınıflardan erişilebilir.
    - **default (package-private):** Metoda sadece aynı paket içinden erişilebilir, başka yerden erişilemez.

- **Ekstra Özellikler:** Metod tanımına eklenebilen ve davranışını değiştiren kelimeler.
    - **static:** Metod sınıfa bağlı olur, nesne oluşturmadan çağrılabilir.
    - **final:** Metod override edilemez, sabittir.
    - **abstract:** Metodun gövdesi yoktur, alt sınıflar implement etmek zorundadır.
    - **synchronized:** Metod thread-safe çalışır, aynı anda birden fazla thread erişemez.

- **Geri Dönüş Tipi:** Metodun çalıştıktan sonra dışarıya hangi türde değer döndüreceğini belirler.
    - `void:` Değer döndürmez.
    - `int:` Tam sayı döndürür.
    - `double:` Ondalıklı sayı döndürür.
    - `float:` Daha az hassas ondalıklı sayı döndürür.
    - `char:` Tek karakter döndürür.
    - `boolean:` Mantıksal değer döndürür. (`true` veya `false`)
    - `String:` Metin döndürür.

- **Metod Adı:** Metodun anlamlı ve açıklayıcı ismi.

- **Parametreler:** Metoda dışarıdan veri göndermek için kullanılır. (opsiyonel)
    - `int:` Tam sayı değeri alabilir.
    - `double:` Ondalıklı sayı değeri alabilir.
    - `float:` Daha az hassas ondalıklı sayı alabilir.
    - `char:` Tek karakter alabilir.
    - `boolean:` Mantıksal değer alabilir.
    - `String:` Metin değeri alabilir.
    - **Birden fazla parametre:** Virgül ile ayrılarak birden fazla veri alınabilir.

> **NOT**:
> Şimdilik sabit bir kalıp kullanacağız :
> ```java
> public static void fonksiyon_adı(){}`
> ```

#### Örnek Kullanımı
```java
// Metodun tanımı
public static void selamla() {
    System.out.println("Merhaba");
}

// Metodun çağrıldığı yer
public static void main(String[] args) {
    selamla(); // Merhaba 
    selamla();  // Merhaba 
}

// Parametreli method

// Metodun tanımı
public static void selamla(String isim) {
    System.out.println("Merhaba " + isim + "!");
}

// Metodun çağrıldığı yer
public static void main(String[] args) {
    selamla("Ahmet"); // Merhaba Ahmet!
    selamla("Ayşe");  // Merhaba Ayşe!
}

// Farklı Örnek

public static void toplama (int num1, int num2) {
  int toplam;
  toplam = num1 + num2;
  System.out.println("Sonuç :" + toplam);

public static void main(String[] args) {
  toplam(2, 4); // Sonuç : 6
  toplam(3, 16); // Sonuç : 19
```

### ⚠️ Uyarı: Metodların Tanımı ve Kullanımı

- **Metod Tanımı:**  
  - Metodlar **sınıfın içinde**, `main` metodunun dışında tanımlanmalıdır.  
  - Bu sayede kod **daha düzenli ve tekrar kullanılabilir** olur.  

- **Metod Kullanımı (Çağrısı):**  
  - Metodlar, tanımlandıktan sonra **`main` metodundan veya başka metodlardan** çağrılabilir.  
  - `static` metodlar → **nesne oluşturmadan** direkt çağrılır.
  - `non-static` metodlar → **sınıfın bir nesnesi** üzerinden çağrılır. (Daha görmedik bilgi amaçlı verildi)
  
---

## return Anahtar Kelimesi

`return`, Java’da bir metodun **hesapladığı veya ürettiği değeri dışarıya göndermek** için kullanılır.  
Metod çalıştıktan sonra **return satırına geldiğinde metod sonlanır** ve değer çağıran yere döner.

> **Önemli Not** <br>
> `return` anahtar kelimesi, bir metodun **çalışmasını hemen sonlandırır**.<br>
> `return` satırından sonra metod içinde yazılmış **hiçbir kod çalıştırılmaz**.<br>
> Kısaca, `return` → **metodu bitiren komut** ve (void değilse) **değer döndüren ifade**dir.

### Kullanım Kuralları

- `void` olmayan metodlarda **mutlaka return değeri olmalıdır**.
- `void` metodlarda return kullanmak **opsiyoneldir**, sadece metodu erken bitirmek için kullanılabilir.
- Return değeri **metodun dönüş tipine uygun** olmalıdır.

### Örnek Kullanım: void olan metod
```java
public static void yazdir() {
    System.out.println("Merhaba");
    return; // opsiyonel, sadece metodu bitirir
}
```

### Örnek Kullanım: Değer Döndüren Metod
```java
// Örnek 1 
public static int topla(int a, int b) {
    return a + b; // a+b sonucu geri döndürülür
}

public static void main(String[] args) {
    int sonuc = topla(5, 3);
    System.out.println(sonuc); // 8

    // ya da

    System.out.println(topla(3, 5));
}

// Örnek 2
// Metod tanımı
public static String selamla(String isim) {
    return "Merhaba " + isim + "!";
}

// Metodun çağrıldığı yer
public static void main(String[] args) {
    String mesaj1 = selamla("Ahmet");
    String mesaj2 = selamla("Ayşe");

    System.out.println(mesaj1); // Merhaba Ahmet!
    System.out.println(mesaj2); // Merhaba Ayşe!
}
```
