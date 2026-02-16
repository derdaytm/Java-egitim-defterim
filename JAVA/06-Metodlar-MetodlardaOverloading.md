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

>**NOT**:
>Aşağıdaki bazı açıklamalar bilgi amaçlı verilmiştir. Kullanılacak kalıba açıklamaların sonunda yer verilmiştir.

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
> public static void fonksiyon_adı(){}
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

---

## Metod Overloading (Aşırı Yükleme)

### Nedir?
Metod overloading, **aynı isimli bir metodun birden fazla farklı parametre ile tanımlanması**dır.  
Java, **parametre sayısı veya türüne göre** hangi metodun çağrılacağını belirler.

- **Metod adı aynı** olmalıdır.  
- **Parametre listesi farklı** olmalıdır. (sayısı veya türü değişmeli)  
- Geri dönüş tipi **farklı olabilir**, ancak dönüş tipi tek başına overload için yeterli değildir. (metod öncesinde `double`, `int` gibi değerler geri dönüş tipidir)

### Neden Kullanılır?
- Kod tekrarını azaltmak.  
- Aynı işlemi farklı veri türleri veya farklı sayıda veri ile yapmak.  
- Daha okunabilir ve esnek kod yazmak.

### Örnek Kullanım

```java
// 1. Metod: 2 tam sayı toplar
public static int topla(int a, int b) {
    return a + b;
}

// 2. Metod: 3 tam sayı toplar
public static int topla(int a, int b, int c) {
    return a + b + c;
}

// 3. Metod: double değerleri toplar
public static double topla(double a, double b) {
    return a + b;
}

public static void main(String[] args) {
    System.out.println(topla(5, 3));       // 8 → 2 int parametreli metod çalışır
    System.out.println(topla(2, 4, 6));    // 12 → 3 int parametreli metod çalışır
    System.out.println(topla(2.5, 3.5));   // 6.0 → double parametreli metod çalışır
}
```

>**NOT**:
>Burada hangi metodu kullanacağını java kendi belirlemektedir.

### Örnek Kullanım
```java
// 1. Metod: İsim alır ve selamlar
public static String selamla(String isim) {
    return "Merhaba " + isim + "!";
}

// 2. Metod: İsim ve soyisim alır ve selamlar
public static String selamla(String isim, String soyisim) {
    return "Merhaba " + isim + " " + soyisim + "!";
}

public static void main(String[] args) {
    String mesaj1 = selamla("Ahmet");
    String mesaj2 = selamla("Ayşe", "Yılmaz");

    System.out.println(mesaj1); // Merhaba Ahmet!
    System.out.println(mesaj2); // Merhaba Ayşe Yılmaz!
}
```

---

## Kod Bloklarındaki Lokal Değişkenler

### Nedir?
- **Lokal değişken**, yalnızca tanımlandığı **kod bloğu içinde geçerli olan değişkendir**.  
- Kod bloğu `{ }` ile sınırlıdır ve blok dışından **erişilemez**.  

### Özellikleri
- Kod bloğu sona erdiğinde **değişken bellekte yok edilir**.  
- Aynı isimde başka bloklarda değişken tanımlanabilir. (bloklar birbirinden bağımsızdır)
- Genellikle metodlar, döngüler veya if-else bloklarında kullanılır.  

---

### Örnek Kullanım: Metod İçinde Lokal Değişken
```java
public static void main(String[] args) {
    int sayi = 10; // main metodunun lokal değişkeni

    if (sayi > 5) {
        int fark = sayi - 5; // if bloğunun lokal değişkeni
        System.out.println("Fark: " + fark);
    }

    // System.out.println(fark); // Hata! 'fark' if bloğu dışından erişilemez
}
```

### Örnek Kullanım: Döngü İçinde Lokal Değişken
```java
for (int i = 0; i < 3; i++) {
    int kare = i * i; // for bloğunun lokal değişkeni
    System.out.println("i: " + i + " karesi: " + kare);
}

// System.out.println(kare); // Hata! 'kare' döngü dışından erişilemez
```

### Örnek: Farklı Metodlarda Aynı İsimli Değişkenler
```java
public static void metod1() {
    int sayi = 5; // metod1'in lokal değişkeni
    System.out.println("Metod1 sayi: " + sayi);
}

public static void metod2() {
    int sayi = 10; // metod2'nin lokal değişkeni, metod1'den bağımsız
    System.out.println("Metod2 sayi: " + sayi);
}

public static void main(String[] args) {
    metod1(); // Metod1 sayi: 5
    metod2(); // Metod2 sayi: 10
}
```

### Örnek: Metoddaki Değişkene Erişmeye Çalışmak
```java
public static void olustur() {
    int sayi = 42; // Bu değişken yalnızca 'olustur' metodunda geçerlidir
    System.out.println("Olustur metodundaki sayi: " + sayi);
}

public static void main(String[] args) {
    olustur(); // Olustur metodunu çağırıyoruz

    // System.out.println(sayi); 
    // Hata! 'sayi' değişkeni sadece olustur() metodunda tanımlı, main metodundan erişilemez
}
```

## Egzersiz

### 1. Kullanıcıdan Alınan Sayının Asal Olup Olmadığını Method Kullanarak Kontrol Etme 

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static int kullanici () {

        Scanner input = new Scanner(System.in);

        System.out.print("Kontrol etmek istediğiniz sayıyı giriniz (Çıkış için -1 yazınız) : ");
            int sayi = input.nextInt();

        return sayi;
    }

    public static String asalmi (int sayi_f) {
        for (int i = 2; i < sayi_f; i++) {
            int kontrol = sayi_f % i ;

            if (kontrol == 0) {
                return "Asal Değil";
            } else {
                return "Asal";
            }
        }
        return "";
    }

    public static void main (String[] args) {

        int sayi = 0;

        System.out.println("-----------------------");
        System.out.println("Asal Sayı Bulma Uygulaması");
        System.out.println("-----------------------");

        while (true) {
            sayi = kullanici();
            

            if(sayi == -1) {
                System.out.println("Çıkış Yapılıyor...");
                break;
            } else {
                System.out.println("Girdiğiniz sayı : " + asalmi(sayi));
            }
            System.out.println("-----------------------");
        }
    }
}
```

</details>

### 2. Kullanıcıdan Alınan 2 Sayının Ekok ve Ebobunu Bulma

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static int kullanici (int sayi_f) {

        Scanner input = new Scanner(System.in);

        System.out.print(sayi_f + ". sayınızı giriniz (Çıkış için -1 giriniz) : ");
            int sayi = input.nextInt();

        return sayi;
    }

    public static int ebobBulma (int sayi1_f, int sayi2_f) {

        int ebob = 1;

        for (int i = 1; i <= sayi1_f && i <=  sayi2_f; i++) {
            if (sayi1_f % i == 0 && sayi2_f % i == 0) {
                ebob = i;
            }
        }

        return ebob;
    }

    public static int ekokBulma (int sayi1_f, int sayi2_f, int ebob_f) {
        int ekok = (sayi1_f * sayi2_f) / ebob_f;
        return ekok;
    }

    public static void main (String[] args) {
        System.out.println("-----------------------------");
        System.out.println("Ebob - Ekok Bulma Uygulaması");
        System.out.println("-----------------------------");

        while (true) {
            int sayi1 = kullanici(1);
            if (sayi1 == -1) {
                System.out.println("Çıkış Yapılıyor...");
                break;
            }

            int sayi2 = kullanici(2);

            System.out.println("-----------------------------");
            System.out.println("Girilen sayıların ebob'u : " + ebobBulma(sayi1, sayi2));
            int ebob = ebobBulma(sayi1, sayi2);
            System.out.println("Girilen sayıların ekok'u : " + ekokBulma(sayi1, sayi2, ebob));
            System.out.println("-----------------------------");

        }
    }
}
```

</details>

### 3. Method Overloading Kullanarak Gelişmiş Hesap Makinesi

> **NOT**
>
> Toplama ve Çarpma metodlarını 2 veya 3 parametre alacak şekilde tasarlayın.

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static int toplama (int sayi1_f, int sayi2_f) {
        return sayi1_f + sayi2_f;
    }

    public static int toplama (int sayi1_f, int sayi2_f, int sayi3_f) {
        return sayi1_f + sayi2_f + sayi3_f;
    }

    public static int carpma (int sayi1_f, int sayi2_f) {
        return sayi1_f * sayi2_f;
    }

    public static int carpma (int sayi1_f, int sayi2_f, int sayi3_f) {
        return sayi1_f * sayi2_f * sayi3_f;
    }

    public static int cıkarma (int sayi1_f, int sayi2_f) {
        return sayi1_f - sayi2_f;
    }

    public static int bölme (int sayi1_f, int sayi2_f) {
        return sayi1_f / sayi2_f;
    }

    public static void main (String[] args) {

        Scanner input = new Scanner(System.in);

        boolean sistemkontrol = true;
        String islemler = "1. Toplama\n"
                         +"2. Çıkarma\n"
                         +"3. Bölme\n"
                         +"4. Çarpma\n"
                         +"5. Çıkış";

        System.out.println("-----------------------------");
        System.out.println("Hesap Makinesi");
        System.out.println("-----------------------------");

        while (sistemkontrol) {
            System.out.println(islemler);
            System.out.print("Lütfen yapmak istediğiniz işlemi seçiniz : ");
            System.out.println("-----------------------------");
            
                int islem = input.nextInt();

            switch (islem) {
                case 1 :
                case 4 :
                    System.out.print("2 sayıyla mı yoksa 3 sayıyla mı işlem yapmak istersiniz : ");
                        int tercih = input.nextInt();

                    if ( tercih == 2) {
                        System.out.print("1. Sayıyı giriniz : ");
                            int sayi1 = input.nextInt();
                        System.out.print("2. Sayıyı giriniz : ");
                            int sayi2 = input.nextInt();

                        if ( islem == 1 ) {
                            System.out.println("Sonuç : " + toplama(sayi1, sayi2));
                            System.out.println("-----------------------------");
                        }

                        if ( islem == 4 ) {
                            System.out.println("Sonuç : " + carpma(sayi1, sayi2));
                            System.out.println("-----------------------------");
                        }

                    } else if ( tercih == 3 ) {
                        System.out.print("1. Sayıyı giriniz : ");
                            int sayi1 = input.nextInt();
                        System.out.print("2. Sayıyı giriniz : ");
                            int sayi2 = input.nextInt();
                        System.out.print("3. Sayıyı giriniz : ");
                            int sayi3 = input.nextInt();

                        if ( islem == 1 ) {
                            System.out.println("Sonuç : " + toplama(sayi1, sayi2, sayi3));
                            System.out.println("-----------------------------");
                        }

                        if ( islem == 4 ) {
                            System.out.println("Sonuç : " + carpma(sayi1, sayi2, sayi3));
                            System.out.println("-----------------------------");
                        }

                    } else {
                        System.out.print("Geçersiz değer girişi...");
                    }

                    break;

                case 2 :
                case 3 :
                    System.out.print("1. Sayıyı giriniz : ");
                    int sayi1 = input.nextInt();
                    System.out.print("2. Sayıyı giriniz : ");
                    int sayi2 = input.nextInt();

                    if ( islem == 2 ) {
                        System.out.println("Sonuç : " + cıkarma(sayi1, sayi2));
                        System.out.println("-----------------------------");
                    }

                    if ( islem == 3 ) {
                        System.out.println("Sonuç : " + bölme(sayi1, sayi2));
                        System.out.println("-----------------------------");
                    }

                    break;

                case 5 :
                    sistemkontrol = false;
                    break;

                default:
                    System.out.println("Geçersiz değer girişi...");
                    System.out.println("Tekrar Deneyiniz...");
                    System.out.println("-----------------------------");
            }
        }

    }

}
```

</details>

---

### 📚 Konu Akışı

**⬅️ Önceki:** [**Döngüler ve Karar Yapıları**](05-Döngüler-KararYapıları.md)<br> 
**➡️ Sonraki:** [**Sınıflar, Metodlar, Constructorlar ve İnheritence**](07-Sınıflar-Metodlar-Constructorlar-Kalıtım.md)
