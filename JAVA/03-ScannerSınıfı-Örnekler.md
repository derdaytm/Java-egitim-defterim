## Scanner Sınıfı

Java’da **kullanıcıdan veri almak** için `Scanner` sınıfı kullanılır.  
Konsoldan **sayı, metin veya diğer veri tiplerini** okuyabiliriz.

---

### Temel Kurallar / Özellikler
- `Scanner` sınıfı `java.util` paketinde bulunur.
- Konsoldan veri almak için **nesne oluşturmak** gerekir. (örnek kısmında anlaşılacak)
- Kullanıcı girişi **beklenir** ve program o noktada durur.
- Farklı veri tipleri için farklı metodlar vardır:
  - `nextLine()` → String okur. (satır tamamı)
  - `next()` → String okur. (Sadece boşluğa kadar tamamını değil)
  - `nextInt()` → int okur.
  - `nextDouble()` → double okur.
  - `nextBoolean()` → boolean okur.
- Sonrasında `scanner.close()` scanner ile işimiz bittiğinde bu komut ile kapatarak veri sızıntısını önleyebiliriz. Kullanılmaması sorun yaratmaz.


### Örnek Kullanım
```java
import java.util.Scanner; // 1. `Scanner` sınıfını import et

public class Deneme {
    public void main(String[] args){
        Scanner scanner = new Scanner(System.in); // 2. Scanner nesnesi oluştur

        String a = scanner.nextLine(); // 3. Artık kullanıcıdan veri alabilirsin

        System.out.println(a);

        input.close(); // 4. Program sonunda kapattık

    }
}
```

> **NOT**:  
> - `import java.util.Scanner;` → Scanner sınıfı **java.util paketinde** olduğu için kullanabilmek adına **programa dahil ediyoruz**.  
> - `Scanner input = new Scanner(System.in);` → Scanner bir **sınıftır**, metodlarını kullanabilmek için **nesne oluşturmak gerekir**.

---

## Scanner Sınıfı – Tüm Veri Tiplerini Kullanan Örnek

Aşağıdaki örnekte **String, int, double ve boolean** veri tipleri Scanner ile okunuyor.  

### Toplu Örnek Kullanım
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in); // Burada scanner yerine input yazdık. (başka şeylerde yazılabilir)
                                                // Buradaki 'input' ismi, oluşturduğumuz Scanner nesnesinin adıdır.
                                                // Değişken adı gibi bunu da biz adlandırıyoruz. 
                                               // İstersek bunu başka bir isimle de yazabiliriz, örn: 'scanner' veya 'kb' gibi.  
                                               // Önemli olan Scanner sınıfını kullanarak nesne üzerinden metodları çağırmaktır.

        // String okuma
        System.out.print("İsminizi girin: ");
        String name = input.nextLine();

        // Kelime okuma
        System.out.print("Soyadınızı girin: ");
        String surname = input.next(); // sadece boşluğa kadar okur
        input.nextLine(); // next() sonrası nextLine() kullanırken boş satırı temizleme (az sonra anlatılacak)

        // int okuma
        System.out.print("Yaşınızı girin: ");
        int age = input.nextInt();

        // double okuma
        System.out.print("Boyunuzu girin (örn: 1.75): ");
        double height = input.nextDouble();

        // boolean okuma
        System.out.print("Öğrenci misiniz? (true/false): ");
        boolean isStudent = input.nextBoolean();

        // Sonuçları yazdırma
        System.out.println("\n--- Bilgileriniz ---");
        System.out.println("İsim: " + name + " " + surname);
        System.out.println("Yaş: " + age);
        System.out.println("Boy: " + height);
        System.out.println("Öğrenci: " + isStudent);

        input.close();
    }
}
```
---

## Scanner ile Boşluk Kullanarak Veri Girişi

`Scanner` sınıfı ile kullanıcı **boşluk bırakarak birden fazla veri girebilir**.  

### Örnek kullanım
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("İki tam sayı girin (boşlukla ayırın): ");
        int num1 = scanner.nextInt();  // ilk sayıyı alır
        int num2 = scanner.nextInt();  // ikinci sayıyı alır
        int num3 = scanner.nextInt();  // Üçüncü sayıyı alır

        System.out.println("Birinci sayı: " + num1);
        System.out.println("İkinci sayı: " + num2);

        input.close();
    }
}
```

### Örnek Kullanım
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("İsminizi ve soyadınızı girin (boşlukla ayırın): ");
        String firstName = input.next();   // ilk kelimeyi alır
        String lastName = input.next();    // ikinci kelimeyi alır

        System.out.println("İsim: " + firstName);
        System.out.println("Soyad: " + lastName);

        input.close();
    }
}
```

---

## Dummy Scanner Kullanımı (Sayıdan Sonra String Okuma)

Java’da `Scanner` ile kullanıcıdan sayı aldıktan sonra **String okumak istediğimizde** bazen boş satır okuma hatası oluşur.  
Bunun nedeni, `nextInt()` veya `nextDouble()` metodlarının **enter tuşunu (newline)** bırakmasıdır.

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Yaşınızı girin: ");
        int age = scanner.nextInt();

        System.out.print("İsminizi girin: ");
        String name = scanner.nextLine();

        System.out.println("Yaş: " + age);
        System.out.println("İsim: " + name);

        scanner.close();
    }
}
```

**Konsol Çıktısı**

<img width="643" height="125" alt="image" src="https://github.com/user-attachments/assets/e40660a1-3819-4d11-8a88-c8878665ed53" />

Görüldüğü üzere burada adımızı sormadı bu şekil hatalar almamak için : 

### Çözüm
- Sayı girdisinden sonra **dummy `scanner.nextLine();`** kullanarak kalan newline karakterini temizleriz.  
- Böylece sonraki `nextLine()` doğru şekilde çalışır.

### Örnek Kullanım
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Yaşınızı girin: ");
        int age = scanner.nextInt();
        scanner.nextLine(); // dummy satır → enter tuşunu temizliyor

        System.out.print("İsminizi girin: ");
        String name = scanner.nextLine();

        System.out.println("Yaş: " + age);
        System.out.println("İsim: " + name);

        scanner.close();
    }
}
```
---

## Ekstralar

> Bu başlık altında, egzersizlerde kullandığımız ancak konu anlatımı sırasında anlatmadığımız veya detaylı açıklamadığımız kavramları ele alacağız.  
> Böylece örneklerde geçen yeni ifadeler veya yapılar eksiksiz şekilde anlaşılmış olacak.

---

### System.out.printf()

`printf`, formatlı (biçimlendirilmiş) çıktı vermek için kullanılır.

#### Ne İşe Yarar?

- Ondalıklı sayıları belirli basamakta göstermek.
- Metni hizalamak.
- Sayıları düzenli biçimde yazdırmak.
- Profesyonel çıktı üretmek.


#### Genel Yapı

```java
System.out.printf("format ifadesi", degisken);
```

#### Format İfadeleri

| İfade | Anlamı |
|-------|--------|
| `%d`  | Tam sayı (`int`) |
| `%f`  | Ondalıklı sayı (`double` / `float`) |
| `%.2f`| Virgülden sonra 2 basamak gösterir |
| `%s`  | String (metin) |
| `%b`  | boolean |

#### Kapsamlı Örnek – printf Tüm Format İfadeleri

Bu örnekte `%d`, `%f`, `%.2f`, `%s`, `%b` ifadelerinin hepsini birlikte kullanıyoruz. Burada böylelikle ondalıklı sayıların kaç basamağının gözükeceğini belirleriz.

##### Örnek Kod

```java
public class Test {
    public static void main(String[] args) {

        String ad = "Ahmet";
        int yas = 25;
        double boy = 1.7564;
        boolean ogrenciMi = true;

        System.out.printf(
            "Ad: %s | Yaş: %d | Boy: %.2f | Öğrenci mi: %b",
            ad, yas, boy, ogrenciMi
        );
    }
}
```

**Konsol Çıktısı**

<img width="607" height="49" alt="image" src="https://github.com/user-attachments/assets/7ce7dd5c-2ad6-40a7-9237-6d034af5dd7b" />

---

### Math.pow()

`Math.pow()` iki sayının **üssünü almak** için kullanılan hazır (built-in) bir Java metodudur.

#### Ne İşe Yarar?

Bir sayının başka bir sayı kuvvetini hesaplar.

#### Genel Yapı

```java
double sonuc = Math.pow(taban, us); // double kullanılması zorunludur.
```

#### Örnek Kullanım
```java
double sonuc = Math.pow(2, 3);
System.out.println(sonuc); // 8
```

---

### Math.sqrt()

`Math.sqrt()` bir sayının **karekökünü almak** için kullanılan hazır (built-in) bir Java metodudur.

#### Ne İşe Yarar?

Bir sayının **pozitif karekökünü** hesaplar.

#### Genel Yapı

```java
double sonuc = Math.sqrt(sayi); // double kullanılması zorunludur.
```

#### Örnek Kullanım 
```java
double sonuc = Math.sqrt(25);
System.out.println(sonuc); // 5.0
```

---

### Math.PI

`Math.PI`, π (pi) sayısını temsil eden hazır (built-in) bir Java sabitidir.

#### Ne İşe Yarar?

Daire ve çember hesaplamalarında kullanılan  
π sayısını (3.141592653589793...) hazır olarak verir.

#### Genel Yapı

```java
double piDegeri = Math.PI; // double tipindedir.
```

---

## Egzersiz

### 1. Beden Kitle İndeksi Hesaplama

Kullanıcıdan aldığınız boy ve kilo değerlerine göre kullanıcının beden kitle indeksini bulun.
(Beden Kitle Endeksi : Kilo / Boy(m) * Boy(m))

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        Scanner scanner = new Scanner(System.in);

        // Kullanıcıdan Veri Alma
        System.out.println("------------------------");
        System.out.println("Beden Kitle Endeksi Hesaplama Uygulamasını Hoşgeldiniz");
        System.out.println("------------------------");
        System.out.print("Lütfen kilonuzu giriniz : ");
            Double kilo = scanner.nextDouble();

        System.out.print("Lütfen boyunuzu metre cinsinden giriniz : ");
            Double boy = scanner.nextDouble();

        Double endeks = kilo / (boy * boy);

        // Ekrana Çıktı Basma
        System.out.println("------------------------");
        System.out.println("Girilen Veriler :");
        System.out.println("Kilo : " + kilo);
        System.out.println("Boy : " + boy);
        System.out.println("------------------------");
        System.out.printf("Beden Kitle Endeksiniz :  %.2f", endeks); 
    }
}
```

**Konsol Çıktısı**

<img width="596" height="266" alt="image" src="https://github.com/user-attachments/assets/67b734fd-7da2-4432-9f29-8a32cd4135c4" />

</details>

### 2. Kilometreye Göre Toplam Ödenecek Tutar Hesaplama

Bir aracın kilometrede ne kadar yaktığı ve kaç kilometre yol yaptığı bilgilerini alın ve sürücünün toplam ne kadar ödemesi gerektiğini hesaplayınız.

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.println("------------------------");
        System.out.print("Aracınız kilometrede kaç kuruş yakıyor ? (Örnek : 0,32) : "); // print kullanma sebebimiz, kullanıcıdan alınacak değerin
                                                                                        // bir alt satıra değil, mesajın hemen yanına yazılmasını sağlamaktır.
                                                                                        // println kullansaydık imleç bir alt satıra geçerdi.
        double kurus = input.nextDouble();

        System.out.print("Aracınızla kaç kilometre yol gittiniz : ");
            double km = input.nextDouble();

        double tutar = kurus * km;

        System.out.println("------------------------");
        System.out.printf("Toplam ödemeniz gereken tutar : %.2f", tutar);

    }
}
```

**Konsol Çıktısı**

<img width="567" height="141" alt="image" src="https://github.com/user-attachments/assets/84274297-46bb-462b-9dd2-b317b28fa0af" />

</details>

### 3. Dik Üçgenin Hipotenüsü Bulma

Dik üçgenin hipotenüsünü (en büyük kenarını) bulan programı yazınız. (hipotenüs = (a kenarı)² + (b kenarı)²)

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.println("----------------------------------");
        System.out.println("Hipotenüs Hesaplama Uygulamasına Hoşgeldiniz...");
        System.out.println("----------------------------------");
        System.out.print("Lütfen 1.kenarı giriniz : " );
            int kenar1 = input.nextInt();

        System.out.print("Lütfen 2.kenarı giriniz : ");
            int kenar2 = input.nextInt();

        double hipotenüs = Math.pow(kenar1, 2) + Math.pow(kenar2, 2);
        hipotenüs = Math.sqrt(hipotenüs);

        System.out.println("----------------------------------");
        System.out.printf("Hipotenüs uzunluğu : %.0f", hipotenüs);
    }
}
```

**Konsol Çıktısı**

<img width="536" height="185" alt="image" src="https://github.com/user-attachments/assets/4c5d3a54-9477-48cb-a277-908b8acc29bf" />

</details>

### 4. Dairenin Alan ve Çevresini Hesaplama  
Kullanıcıdan yarıçap değerini alın ve dairenin alanını ile çevresini hesaplayınız.  
(Alan = πr², Çevre = 2πr)

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        Scanner input = new Scanner (System.in);

        System.out.println("----------------------------");
        System.out.println("Daire Alan ve Çevresini Hesaplama");
        System.out.println("----------------------------");

        System.out.print("Lütfen dairenizin yarıçapını giriniz : ");
            double yaricap = input.nextDouble();

        double alan = Math.PI * yaricap * yaricap;
        double cevre = 2 * Math.PI * yaricap;

        System.out.println("----------------------------");
        System.out.printf("Dairenizin alanı : %.2f \n", alan);
        System.out.printf("Dairenizin alanı : %.2f", cevre);
    }
}
```

**Konsol Çıktısı**

<img width="427" height="180" alt="image" src="https://github.com/user-attachments/assets/334d8036-22ac-462d-a442-0a63bb343a41" />

</details>

### 5. Girilen 3 Sayının Ortalamasını Hesaplama 
Kullanıcıdan üç sayı alın ve bu sayıların aritmetik ortalamasını hesaplayınız.

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.println("-------------------------");
        System.out.println("Aritmetik Ortalama Hesaplama");
        System.out.println("-------------------------");

        System.out.print("Lütfen 1.sayınızı giriniz : ");
            double sayi1 = input.nextDouble();
        System.out.print("Lütfen 2.sayınızı giriniz : ");
            double sayi2 = input.nextDouble();
        System.out.print("Lütfen 3.sayınızı giriniz : ");
            double sayi3 = input.nextDouble();

        double ortalama = (sayi1 + sayi2 + sayi3) / 3;

        System.out.println("------------------------");
        System.out.printf("Girdiğiniz sayıların ortalaması : %.2f", ortalama);
    }
}
```

**Konsol Çıktısı**

<img width="401" height="197" alt="image" src="https://github.com/user-attachments/assets/00a5d871-ce88-4c5f-9e6c-acf3ce23ca25" />

</details>

---

### 📚 Konu Akışı

**⬅️ Önceki:** [**Temel Operatörler**](02-Temel-Operatörler.md)   
**➡️ Sonraki:** [**Koşullu Durumlar ve Kod Blokları**](04-KoşulluDurumlar-KodBlokları.md)
