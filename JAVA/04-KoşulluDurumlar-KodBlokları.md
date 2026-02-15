## Kod Blokları 

Java’da **kod blokları**, `{ }` süslü parantezler arasına yazılan ve **birlikte çalışan kod gruplarını** ifade eder.  
Bir kod bloğu, Java’ya **hangi satırların birlikte çalışacağını** söyler.

### Ne İşe Yarar?
- Kodun **başlangıç ve bitiş sınırlarını** belirler.
- Değişkenlerin **geçerlilik alanını (scope)** tanımlar.
- Programın daha **düzenli ve okunabilir** olmasını sağlar.

---

## Kodları Temiz Yazmak (Clean Code)

**Temiz kod**, kolay okunan, kolay anlaşılan ve kolay geliştirilen koddur.  
Amaç sadece çalışan kod yazmak değil, **başka biri baktığında rahatça anlayabileceği kod** yazmaktır.

### Neden Önemlidir?
- Okuması ve anlaması kolay olur.
- Hatalar daha hızlı fark edilir.
- Kod geliştirmek ve düzenlemek kolaylaşır.
- Uzun vadede projeyi sürdürülebilir yapar.

### Temel Temiz Kod Kuralları

#### 1️⃣ Anlamlı İsimler Kullan
```java
int a = 10;      // kötü
int userAge = 10; // iyi
```

#### 2️⃣ Gereksiz Kod Yazma
```java
int x = 10;
x = x; // gereksiz
```

#### 3️⃣ Düzenli Boşluk ve Satır Kullan
```java
int a=10;int b=5;System.out.println(a+b); // kötü

int a = 10;
int b = 5;
System.out.println(a + b); // iyi
```

#### 4️⃣ Her Satıra Bir İş Yükle
```java
int a = 10; int b = 5; int c = a + b; // okunması zor

int a = 10;
int b = 5;
int c = a + b; // temiz
```

#### 5️⃣ Gereksiz Yorum Yazma
```java
int age = 20; // yaş değişkeni
```

#### 6️⃣ Kodları Mantıksal Olarak Grupla
```java
// Kullanıcı bilgileri
String name = "Ahmet";
int age = 25;

// Hesaplama
int total = age + 5;
```

#### 7️⃣ Girintili Yazma (Indentation)
```java
public class Main{
public static void main(String[] args){
int x=10;
if(x>5){
System.out.println("Büyük");
}
}
}

public class Main {
    public static void main(String[] args) {

        int x = 10;

        if (x > 5) {
            System.out.println("Büyük");
        }

    }
}
```

---

## if – else Yapısı (Koşullu İfadeler)

**if – else**, Java’da koşula göre **karar vermek** için kullanılır.  
“Eğer şu doğruysa bunu yap, değilse şunu yap” mantığıyla çalışır.

### Temel Mantık

- Koşul **true** ise → `if` bloğu çalışır.
- Koşul **false** ise → `else` bloğu çalışır.

### Temel Kullanım
```java
if (koşul) {
    // koşul doğruysa çalışır
} else {
    // koşul yanlışsa çalışır
}
```

#### Örnek Kullanım
```java
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Yaşınızı girin: ");
        int age = scanner.nextInt();

        if (age >= 18) {
            System.out.println("Reşit");
        } else {
            System.out.println("Reşit değil");
        }

        scanner.close();
    }
}
```

---

## Birden Fazla Koşul

Birden fazla olası durum varsa **`else if`** yapısı kullanılır.  
Bu yapı, koşulları **üstten alta doğru sırayla** kontrol eder.

### Çalışma Mantığı
- İlk `if` kontrol edilir.
- Eğer **false** ise `else if` bloklarına geçilir.
- **İlk true olan blok çalışır**.
- Java o noktada **durur**, alttaki koşullara bakmaz.
- Hiçbiri true değilse `else` çalışır.

### Örnek Kullanım
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Notunuzu girin: ");
        int not = scanner.nextInt();

        if (not >= 85) {
            System.out.println("Pekiyi");
        } else if (not >= 70) {
            System.out.println("İyi");
        } else if (not >= 50) {
            System.out.println("Geçer");
        } else {
            System.out.println("Kaldı");
        }

        scanner.close();
    }
}
```

---

## Mantıksal Operatörlerle if - else Kullanımı

Bu örnekte, **birden fazla koşulun aynı anda sağlanması** gerektiği durumlarda 
**mantıksal operatörler** ile `if - else` yapısının nasıl kullanıldığı gösterilir.


### Örnek Kullanım
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Yaşınızı girin: ");
        int age = scanner.nextInt();

        System.out.print("Biletiniz var mı? (true / false): ");
        boolean hasTicket = scanner.nextBoolean();

        if (age >= 18 && hasTicket) {
            System.out.println("Giriş yapılabilir");
        } else {
            System.out.println("Giriş yapılamaz");
        }

        scanner.close();
    }
}
```

---

## İç İçe if (Nested if)

Bir koşulun **ancak başka bir koşul sağlandığında** kontrol edilmesi gerekiyorsa
**iç içe if (nested if)** yapısı kullanılır.

### Örnek Kullanım
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Birinci sayıyı girin: ");
        int a = scanner.nextInt();

        System.out.print("İkinci sayıyı girin: ");
        int b = scanner.nextInt();

        if (a > 0) {
            if (b > 0) {
                System.out.println("İki sayı da pozitif");
            }
        }

        // Burada else kullanılmadı peki zorunlu mu ? (Altta Anlatıldı)

        scanner.close();
    }
}
```

---

## else Zorunlu mu?

`else` bloğu **zorunlu değildir**.  
Bazı durumlarda sadece `if` kullanmak yeterlidir.

### Ne Anlama Gelir?
- `if` → Koşul **sağlanırsa** çalışır.
- `else` → Koşul **sağlanmazsa** çalışır.
- Eğer yapılacak **ekstra bir işlem yoksa**, `else` yazmaya gerek yoktur.

### Örnek Kullanım 
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Bir sayı girin: ");
        int x = scanner.nextInt();

        if (x > 0) {
            System.out.println("Pozitif");
        }

        scanner.close();
    }
}
```

---

## Çoklu ve İç İçe if - else Kullanımı

Java’da **istediğimiz kadar `if` ve `else` yapısını** iç içe kullanabiliriz.  
Bu, **karmaşık karar mekanizmaları** kurmamızı sağlar.

> ⚠️ Ancak fazla iç içe kullanım kodu zor okunur hale getirebilir.  
> Bu örnek bilerek **karmaşık** hazırlanmıştır.

### Senaryo
Bir etkinliğe giriş kuralları:

1. Yaş kontrolü
2. Bilet kontrolü
3. Öğrenci durumu
4. VIP durumu
5. Saat kontrolü

### Örnek Kullanım (Karmaşık / İç İçe)
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Yaşınızı girin: ");
        int age = scanner.nextInt();

        System.out.print("Biletiniz var mı? (true / false): ");
        boolean hasTicket = scanner.nextBoolean();

        System.out.print("Öğrenci misiniz? (true / false): ");
        boolean isStudent = scanner.nextBoolean();

        System.out.print("VIP misiniz? (true / false): ");
        boolean isVip = scanner.nextBoolean();

        System.out.print("Saat kaç? (0-23): ");
        int hour = scanner.nextInt();

        if (age >= 18) {
            if (hasTicket) {
                if (hour >= 10 && hour <= 22) {
                    if (isVip) {
                        System.out.println("VIP giriş yapılabilir");
                    } else {
                        if (isStudent) {
                            System.out.println("Öğrenci indirimiyle giriş yapılabilir");
                        } else {
                            System.out.println("Tam ücretli giriş yapılabilir");
                        }
                    }
                } else {
                    System.out.println("Etkinlik saatleri dışında");
                }
            } else {
                System.out.println("Biletiniz yok");
            }
        } else {
            System.out.println("Yaşınız giriş için uygun değil");
        }

        scanner.close();
    }
}
```

---

## switch - case Yapısı

`switch - case`, **bir değişkenin aldığı değere göre** farklı işlemler yapmak için kullanılır.  
Çok sayıda `else if` yerine **daha okunabilir** bir yapı sunar.

### Ne İşe Yarar?
- Tek bir değişkenin **farklı değerlerini** kontrol eder.
- Kodun daha **temiz ve anlaşılır** olmasını sağlar.
- Genellikle **sabit değerler** (int, char, String) ile kullanılır.

### Temel Yapı
```java
switch (deger) {
    case 1:
        // yapılacak işlem
        break;
    case 2:
        // yapılacak işlem
        break;
    default:
        // hiçbir case eşleşmezse
}
```

### Nasıl Çalışır?

- `switch` içine verilen değer kontrol edilir.  
- Bu değer, `case` ifadeleriyle **tek tek karşılaştırılır**.  
- Eşleşme bulunduğunda ilgili `case` bloğu çalışır. 
- `break` kullanılırsa `switch` bloğundan **çıkılır**.
- kullanılmazsa o `case`'den sonraki tüm `case`'ler çalışır. (default dahil)
- Hiçbir `case` eşleşmezse `default` bloğu çalışır.

#### Örnek Kullanım
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Bir sayı girin (1-3): ");
        int choice = scanner.nextInt();

        switch (choice) {
            case 1:
                System.out.println("Seçim: 1");
                break;
            case 2:
                System.out.println("Seçim: 2");
                break;
            case 3:
                System.out.println("Seçim: 3");
                break;
            default:
                System.out.println("Geçersiz seçim");
        }

        scanner.close();
    }
}
```

> **NOT**  
> `break` zorunlu değildir, ancak **çoğu durumda mutlaka kullanılmalıdır**.  
> `break` yazılmazsa, eşleşen `case` çalıştıktan sonra **altındaki tüm case blokları da çalışır**. (fall-through) (default dahil)<br>
> Bu durum genellikle **istenmeyen sonuçlara** yol açar. 

#### Örnek Kullanım (break'siz)
```java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Bir sayı girin (1-3): ");
        int choice = scanner.nextInt();

        switch (choice) {
            case 1:
                System.out.println("Seçim: 1");
            case 2:
                System.out.println("Seçim: 2");
            case 3:
                System.out.println("Seçim: 3");
            default:
                System.out.println("Geçersiz seçim");
        }

        scanner.close();
    }
}
```

**Konsol Çıktısı**

<img width="509" height="152" alt="image" src="https://github.com/user-attachments/assets/16712e8a-8ee0-4068-a8af-d4b6be955c25" />

---

## Egzersiz

### Girilen 3 Sayıdan Maksimum Sayıyı Bulma

Kullanıcıdan alınan 3 sayıdan en büyük olanı bulan ve konsola yazdıran programı yazınız.

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {
        
        Scanner input = new Scanner(System.in);
        
        System.out.println("----------------------------");
        System.out.println("3 Sayı Arasından En Büyüğü Bulma Programı");
        System.out.println("----------------------------");
        
        System.out.print("Lütfen 1.sayınızı giriniz : ");
            int sayi1 = input.nextInt();
        System.out.print("Lütfen 2.sayınızı giriniz : ");
            int sayi2 = input.nextInt();
        System.out.print("Lütfen 3.sayınızı giriniz : ");
            int sayi3 = input.nextInt();
            
        if (sayi1 > sayi2) {
            if (sayi3 > sayi1) {
                System.out.println("En Büyük Sayı :" + sayi3);
            } else {
                System.out.println("En Büyük Sayı : " + sayi1);
            }
        } else {
            if (sayi2 > sayi3) {
                System.out.println("En Büyük Sayı : " + sayi2);
            } else {
                System.out.println("En Büyük Sayı : " + sayi3);
            }
        }
    }
}
```

**Konsol Çıktısı**

<img width="528" height="154" alt="image" src="https://github.com/user-attachments/assets/e1adcc5a-3c16-426c-a962-ae0fa5b0fb96" />

</details>

### Koşullarla Beden Kitle İndeksi Hesaplama

Kullanıcıdan alınan boy ve kilo değerlerine göre BKİ (beden kitle indeksini) hesaplayın ve aşağıda belirtilen koşullara göre konsola çıktı yazdırın.
(BKİ = Kilo / Boy * Boy)
BKİ < 18.5 = Zayıf
18.5 < BKİ < 25 = Normal
25 < BKİ < 30 = Fazla kilolu
30 < BKİ = Obez

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.println("--------------------------------");
        System.out.println("Beden Kitle İndeksi Hesaplayan Program");
        System.out.println("--------------------------------");

        System.out.print("Lütfen kilonuzu yazınız : ");
            double kilo = input.nextDouble();
        System.out.print("Lütfen boyunuzu metre cinsinden yazınız : ");
            double boy = input.nextDouble();

        double bki = kilo / (boy * boy);

        if (bki < 0) {
            System.out.println("Yanlış veri girdiniz. Program kapatılıyor...");
        } else if (bki < 18.5) {
            System.out.println("Zayıf");
        } else if (bki < 25) {
            System.out.println("Normal");
        } else if (bki < 30) {
            System.out.println("Fazla Kilolu");
        } else {
            System.out.println("Obez");
        }
    }
}
```

**Konsol Çıktısı**

<img width="442" height="133" alt="image" src="https://github.com/user-attachments/assets/425fe648-96c9-4aaf-b190-edeff389e077" />

</details>

### Basit Hesap Makinesi

`switch - case` yapısını kullanarak 4 işlem yapan bir hesap makinesi tasarlayın.

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        String islemler = "1.Toplama İşlemi\n"
                         +"2.Çıkarma İşlemi\n"
                         +"3.Çarpma İşlemi\n"
                         +"4.Bölme İşlemi";

        Scanner input = new Scanner(System.in);

        System.out.println("--------------------------");
        System.out.println("Hesap Makinesi");
        System.out.println("--------------------------");

        System.out.println(islemler);
        System.out.print("Lütfen İşlem Seçiniz : ");
            int islem = input.nextInt();
        System.out.println("--------------------------");

        double sonuc;
        int sayi1;
        int sayi2;

        switch (islem) {
            case 1 :
                System.out.print("Lütfen 1.sayınızı giriniz : ");
                    sayi1 = input.nextInt();
                System.out.print("Lütfen 2.sayınızı giriniz : ");
                    sayi2 = input.nextInt();
                System.out.println("--------------------------");
                sonuc = sayi1 + sayi2;
                System.out.printf("Sonuç : %.0f", sonuc);
                break;

            case 2 :
                System.out.print("Lütfen 1.sayınızı giriniz : ");
                    sayi1 = input.nextInt();
                System.out.print("Lütfen 2.sayınızı giriniz : ");
                    sayi2 = input.nextInt();
                System.out.println("--------------------------");
                sonuc = sayi1 - sayi2;
                System.out.printf("Sonuç : %.0f", sonuc);
                break;

            case 3 :
                System.out.print("Lütfen 1.sayınızı giriniz : ");
                    sayi1 = input.nextInt();
                System.out.print("Lütfen 2.sayınızı giriniz : ");
                    sayi2 = input.nextInt();
                System.out.println("--------------------------");
                sonuc = sayi1 * sayi2;
                System.out.printf("Sonuç : %.0f", sonuc);
                break;

            case 4 :
                System.out.print("Lütfen 1.sayınızı giriniz : ");
                    sayi1 = input.nextInt();
                System.out.print("Lütfen 2.sayınızı giriniz : ");
                    sayi2 = input.nextInt();
                System.out.println("--------------------------");
                sonuc = sayi1 / sayi2;
                System.out.printf("Sonuç : %.0f", sonuc);
                break;

            default:
                System.out.println("--------------------------");
                System.out.println("Geçersiz değer girdiniz. Program kapatılıyor...");
        }
    }
}
```

**Konsol Çıktısı**

<img width="494" height="282" alt="image" src="https://github.com/user-attachments/assets/39db3cbc-0c5f-49d0-8daa-c8a1da0557bb" />

</details>

### Gelişmiş Not Hesaplama

Kullanıcıdan vize 1, vize 2 ve final notunu alarak bir harf hesaplama sistemi yapın.
1. Vizeler %30 etki edecektir.
2. Final %40 etki edecektir.

Not ortalaması 
    90 ve üzeriyse = AA,
    85 - 90 arasıysa = BA,
    80 - 85 arasıysa = BB,
    75 - 80 arasıysa = CB,
    70 - 75 arasıysa = CC,
    65 - 70 arasıysa = DC,
    60 - 65 arasıysa = DD,
    50 - 60 arasıysa = FD,
    50 altıysa = FF
    
<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        String islemler = "1.Toplama İşlemi\n"
                         +"2.Çıkarma İşlemi\n"
                         +"3.Çarpma İşlemi\n"
                         +"4.Bölme İşlemi";

        Scanner input = new Scanner(System.in);

        System.out.println("--------------------------");
        System.out.println("Hesap Makinesi");
        System.out.println("--------------------------");

        System.out.println(islemler);
        System.out.print("Lütfen İşlem Seçiniz : ");
            int islem = input.nextInt();
        System.out.println("--------------------------");

        double sonuc;
        int sayi1;
        int sayi2;

        switch (islem) {
            case 1 :
                System.out.print("Lütfen 1.sayınızı giriniz : ");
                    sayi1 = input.nextInt();
                System.out.print("Lütfen 2.sayınızı giriniz : ");
                    sayi2 = input.nextInt();
                System.out.println("--------------------------");
                sonuc = sayi1 + sayi2;
                System.out.printf("Sonuç : %.0f", sonuc);
                break;

            case 2 :
                System.out.print("Lütfen 1.sayınızı giriniz : ");
                    sayi1 = input.nextInt();
                System.out.print("Lütfen 2.sayınızı giriniz : ");
                    sayi2 = input.nextInt();
                System.out.println("--------------------------");
                sonuc = sayi1 - sayi2;
                System.out.printf("Sonuç : %.0f", sonuc);
                break;

            case 3 :
                System.out.print("Lütfen 1.sayınızı giriniz : ");
                    sayi1 = input.nextInt();
                System.out.print("Lütfen 2.sayınızı giriniz : ");
                    sayi2 = input.nextInt();
                System.out.println("--------------------------");
                sonuc = sayi1 * sayi2;
                System.out.printf("Sonuç : %.0f", sonuc);
                break;

            case 4 :
                System.out.print("Lütfen 1.sayınızı giriniz : ");
                    sayi1 = input.nextInt();
                System.out.print("Lütfen 2.sayınızı giriniz : ");
                    sayi2 = input.nextInt();
                System.out.println("--------------------------");
                sonuc = sayi1 / sayi2;
                System.out.printf("Sonuç : %.0f", sonuc);
                break;

            default:
                System.out.println("--------------------------");
                System.out.println("Geçersiz değer girdiniz. Program kapatılıyor...");
        }
    }
}
```

**Konsol Çıktısı**

<img width="494" height="282" alt="image" src="https://github.com/user-attachments/assets/39db3cbc-0c5f-49d0-8daa-c8a1da0557bb" />

</details>
 
---

### 📚 Konu Akışı

**⬅️ Önceki:** [**Scanner Sınıfı ve Örnekler**](03-ScannerSınıfı-Örnekler.md)   
**➡️ Sonraki:** [**Döngüler ve Karar Yapıları**](05-Döngüler-KararYapıları.md)
