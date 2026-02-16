## Döngü (Loop)

### Ne İşe Yarar?
- Tekrarlanan işlemleri otomatik hale getirir.
- Kod tekrarını azaltır.
- Daha temiz ve okunabilir kod yazmayı sağlar.

### Temel Mantık
- Bir **başlangıç değeri** vardır.
- Bir **koşul** kontrol edilir.
- Her adımda **ilerleme** (artış / azalış) olur.
- Koşul `false` olduğunda döngü durur.

### Döngü Türleri

Java’da **3 temel döngü yapısı** vardır:

- **for döngüsü** → Kaç kez çalışacağı belliyse.
- **while döngüsü** → Koşul baştan kontrol edilecekse.
- **do-while döngüsü** → Kod en az bir kez çalışacaksa.

> Eğer döngüler konusunu biliyor ancak hangi döngüyü kullanmakta karar veremiyorsanız [BURAYA TIKLAYABİLİRSİNİZ.](#for-while-ve-do-while-Arasındaki-Temel-Farklar)

---

## for Döngüsü

### Ne Zaman Kullanılır?
- Belirli sayıda tekrar gerekiyorsa.
- Sayma, listeleme, aralık kontrolü yapılacaksa.
- Başlangıç ve bitiş değeri netse.

### Temel Yapı
```java
for (başlangıç; koşul; artış) {
    // çalışacak kodlar
}
```

### Yapının Anlamı

- **başlangıç** → Döngü sayacının ilk değeridir. 
- **koşul** → Döngünün devam edip etmeyeceğini belirler.
- **artış** → Her turda sayacın nasıl değişeceğini ifade eder.

> **NOT**:
> Koşul sağlandığında döngüye son verilir.

### Örnek Kullanım
```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}

// Değişken dışarıda da tanımlanabilir

int i;

for (i = 1; i <= 5; i++) {
    System.out.println(i);
}

// Değişken hem dışarı da tanımanıp hem ilk değerini dışarıda alabilir

int i = 1;

for (; i <= 5; i++) { // Başa noktalı virgül koyulduğuna dikkat edelim
    System.out.println(i);
}
````

---

## for Döngüsünde Artış

`for` döngüsünde **artış kısmı tamamen serbesttir**.  
Sadece `i++` kullanılmak zorunda değildir.


### 1’er 1’er Artırma
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

### 2’şer 2’şer Artırma
```java
for (int i = 0; i <= 10; i += 2) {
    System.out.println(i);
}
```

### Azaltma (Geriye Doğru Sayma)
```java
for (int i = 5; i > 0; i--) {
    System.out.println(i);
}
```

### Farklı Azaltma Miktarı
```java
for (int i = 10; i >= 0; i -= 3) {
    System.out.println(i);
}
```

### Koşula Bağlı Artış (İleri Seviye Mantık)
```java
// Örnek 1
for (int i = 1; i < 20; i = i * 2) {
    System.out.println(i);
}

// Örnek 2
for (int i = 100; i > 0; i = i / 2) {
    System.out.println(i);
}

// Örnek 3
for (int i = 2; i <= 100; i = i * i) {
    System.out.println(i);
}
```

---

### for Döngüsünde Birden Fazla Değişken Kullanımı

`for` döngüsünde **aynı anda 2 veya daha fazla değişken** tanımlanabilir ve yönetilebilir.  
Bu yapı, **birden fazla değerin birlikte ilerlemesi** gereken durumlarda kullanılır.

### Örnek Kullanım
```java
// Örnek 1
for (int i = 1, j = 10; i <= 5; i++, j--) {
    System.out.println("i: " + i + " j: " + j);
}

// Örnek 2
for (int a = 0, b = 0; a <= 10; a += 2, b += 3) {
    System.out.println("a: " + a + " b: " + b);
}

// Örnek 3
for (int x = 1, y = 20; x < y; x++, y--) {
    System.out.println("x: " + x + " y: " + y);
}

// Örnek 4
for (int x = 1, y = 20; x < y; x++, y--) {
    System.out.println("x: " + x + " y: " + y);
}

// Örnek 5
for (int x = 1, y = 1; x <= 3 || y <= 3; x++, y++) {
    System.out.println("x: " + x + " y: " + y);
}

// Örnek 6
for (int a = 0, b = 20; a < b && b > 10; a += 2, b -= 3) {
    System.out.println("a: " + a + " b: " + b);
}

// Atama ve / veya Tanımlama Dışarda da yapılabilir.

int a = 0, b = 20

for (; a < b && b > 10; a += 2, b -= 3) {
    System.out.println("a: " + a + " b: " + b);

```

***

## while Döngüsü

### Ne Zaman Kullanılır?
- Kaç kez çalışacağı **önceden belli değilse**.
- Döngü **tamamen bir koşula bağlıysa**.
- Kullanıcıdan gelen veriye göre tekrar gerekiyorsa.
- Bir işlem **koşul sağlandığı sürece** devam edecekse.

---

### Temel Yapı
```java
while (koşul) {
    // çalışacak kodlar
    // sayaç değişkenini koşula bağlı artırma / azaltma
}
```

### Yapının Anlamı

- **koşul** → Döngünün çalışıp çalışmayacağını belirler.  
- Koşul **en başta** kontrol edilir.
- Koşul `true` ise döngü çalışır.  
- Koşul `false` ise döngü **hiç çalışmaz**.

>**ÖNEMLİ**<br>
>`while` döngüsünde **önce koşul kontrol edilir**, **sonra** kod bloğu çalışır.<br>
>Bu yüzden koşul **baştan yanlışsa**, döngüye **asla girilmez**.

#### Örnek Kullanım
```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i++; 
}
```

Sayaç artışı / azalışı matematiksel ifadelerle duruma göre ayarlanır :

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i += 2; 
}
```

Eğer sayaç artış / azalışı unutulursa veya yanlış girilirse sonsuz döngü oluşturulabilir :

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i-- ; // Azaldığı için sonsuz döngü 
}

// ya da

int i = 1;

while (i <= 5) {
    System.out.println(i);
     // `i++` gibi bir kısım yok o yüzden sonsuz döngü 
}
```


---

## while Döngüsünde Birden Fazla Değişken

`while` döngüsünde **birden fazla değişken** aynı anda kullanılabilir ve bu değişkenler **koşul kısmında birlikte kontrol edilebilir**.

Bu yapı genellikle:
- İki değerin birbirine yaklaşması.
- Biri artarken diğerinin azalması.
- Birden fazla şartın aynı anda sağlanması gereken durumlarda kullanılır.

### Örnek Kullanım
```java
int a = 1;
int b = 10;

while (a <= 5 && b >= 5) {
    System.out.println("a: " + a + " b: " + b);
    a++; // a değişkeni her turda 1 artırılır
    b--; // b değişkeni her turda 1 azaltılır
}
```

---

## for ile while Arasındaki Temel Fark

| Özellik | for Döngüsü | while Döngüsü |
|------|------------|---------------|
| Tekrar Sayısı | Tekrar sayısı **bellidir** | Tekrar sayısı **belirsizdir** |
| Sayaç Tanımı | Sayaç **döngü içinde** tanımlanır | Sayaç **döngü dışında** tanımlanır |
| Kullanım Amacı | Kaç kez döneceği net olan durumlar | Koşula bağlı belirsiz tekrarlar |
| Okunabilirlik | Daha **düzenli ve kısa** görünür | Daha **esnek** bir yapı sunar |
| Kontrol Noktası | Başlangıç, koşul ve artış tek satırdadır | Kontroller kodun farklı yerlerindedir |
| Tercih Edilme | Sayma, listeleme, aralık işlemleri | Kullanıcı girişi, belirsiz süreçler |

### Kısa Özet
- **for** → Kaç kez döneceğini biliyorsan. 
- **while** → Ne zaman biteceğini bilmiyorsan.

---

## do-while Döngüsü

### Ne Zaman Kullanılır?
- Kodun **en az bir kez çalışması gerekiyorsa**.
- Kullanıcıdan veri alınıp **sonradan kontrol yapılacaksa**.
- Menü, onay, tekrar deneme gibi senaryolarda.

---

### Temel Yapı
```java
do {
    // çalışacak kodlar
    // sayaç değişkenini koşula bağlı artırma / azaltma
} while (koşul);
```

> ⚠️ **Noktalı Virgüle (;) Dikkat!**
> `do-while` döngüsünde `while` satırı **noktalı virgül (;) ile biter**.

### Yapının Anlamı
- **do bloğu** → Önce çalışır.  
- **koşul** → En son kontrol edilir.  
- Koşul `true` ise döngü tekrar eder.  
- Koşul `false` olsa bile **kod en az 1 kez çalışır**.

### ÖNEMLİ FARK (for / while ile)
- `do-while`, koşulu **sonda** kontrol eder. 
- Bu yüzden koşul baştan yanlış olsa bile **1 kez çalışır*.

#### Örnek Kullanım
```java
int i = 5;

do {
    System.out.println(i);
    i++;
} while (i < 3);

// Burada koşul sağlanmamasına rağmen 1 kez çalıştı.
```

**Tarayıcı Çıktısı**

<img width="498" height="70" alt="image" src="https://github.com/user-attachments/assets/62b0c3c1-7e4e-4418-8708-dc75e5b4e8e0" />

#### Örnek Kullanım

```java
int i = 0;

do {
    System.out.println(i);
    i++;
} while (i < 3);
```

Sayaç artışı / azalışı matematiksel ifadelerle duruma göre ayarlanır :

```java
int i = 0;

do {
    System.out.println(i);
    i += 2;
} while (i < 3);
```

Eğer sayaç artış / azalışı unutulursa veya yanlış girilirse sonsuz döngü oluşturulabilir :

```java
int i = 0;

do {
    System.out.println(i);
    i--; // Azaldığı için sonsuz döngü 
} while (i < 3);

// ya da

int i = 0;

do {
    System.out.println(i);
     // `i++` gibi bir kısım yok o yüzden sonsuz döngü 
} while (i < 3);
```

---

## do-while Döngüsünde Birden Fazla Değişken

`do-while` döngüsünde de **birden fazla değişken** aynı anda kullanılabilir ve bu değişkenler **koşul kısmında birlikte kontrol edilebilir**.

Bu yapı genellikle:
- İşlemin **en az bir kez yapılmasının zorunlu olduğu**.
- Sonrasında şartların kontrol edilmesi gereken durumlarda tercih edilir.

### Örnek Kullanım
```java
int a = 1;
int b = 10;

do {
    System.out.println("a: " + a + " b: " + b);
    a++; // a değişkeni her turda 1 artırılır
    b--; // b değişkeni her turda 1 azaltılır
} while (a <= 5 && b >= 5);
```

---

## for, while ve do-while Arasındaki Temel Farklar

| Özellik | for Döngüsü | while Döngüsü | do-while Döngüsü |
|------|------------|---------------|------------------|
| Tekrar Sayısı | Tekrar sayısı **bellidir** | Tekrar sayısı **belirsizdir** | Tekrar sayısı **belirsizdir** |
| Sayaç Tanımı | Sayaç **döngü içinde** tanımlanır | Sayaç **döngü dışında** tanımlanır | Sayaç **döngü dışında** tanımlanır |
| Koşul Kontrolü | Döngü **başında** kontrol edilir | Döngü **başında** kontrol edilir | Döngü **sonunda** kontrol edilir |
| En Az Çalışma | Koşul false ise **hiç çalışmaz** | Koşul false ise **hiç çalışmaz** | Koşul false olsa bile **en az 1 kez çalışır** |
| Okunabilirlik | Daha **düzenli ve kısa** | Daha **esnek** | Mantığı net ama daha az kullanılır |
| Kullanım Amacı | Sayma, listeleme, aralık işlemleri | Belirsiz tekrarlar, kullanıcı girişi | En az 1 kez çalışması gereken işlemler |
| Tipik Kullanım | Sabit tekrar sayısı | Koşula bağlı süreçler | Menü, doğrulama, ilk çalıştırma |

### Kısa Özet
- **for** → Kaç kez döneceğini biliyorsan.  
- **while** → Ne zaman biteceğini bilmiyorsan.  
- **do-while** → Kod **en az 1 kez mutlaka çalışmalıysa**.

---

## break Anahtar Kelimesi

`break`, Java’da **akışı anında durdurmak** için kullanılır.  
Bulunduğu yapıyı **hemen sonlandırır** ve kod akışı dışarıdan devam eder.

## Döngülerde break Kullanımı

Bir döngü çalışırken belirli bir şart oluştuğunda **döngüyü erken bitirmek** için `break` kullanılır.

### Örnek Kullanım
```java
// `for` döngüsünde kullanımı
for (int i = 1; i <= 10; i++) {
    if (i == 5) {
        break; // i 5 olduğunda döngü durur
    }
    System.out.println(i);
}

// `while` döngüsünde kullanımı
int i = 1;

while (i <= 10) {
    if (i == 7) {
        break; // i 7 olduğunda döngü biter
    }
    System.out.println(i);
    i++;
}

// `do-while` döngüsünde kullanımı
int i = 1;

do {
    if (i == 3) {
        break; // koşuldan bağımsız olarak döngü sonlanır
    }
    System.out.println(i);
    i++;
} while (i <= 5);
```

Bazen sayaç artırma / azaltma yapılmadan direk break ile bitirilebilir :
```java
// `while` döngüsünde kullanımı
int i = 1;

while (i <= 10) {
    if (i == 7) {
        break; // i 7 olduğunda döngü biter
    }
    System.out.println(i);
}

// `do-while` döngüsünde kullanımı
int i = 1;

do {
    if (i == 3) {
        break; // koşuldan bağımsız olarak döngü sonlanır
    }
    System.out.println(i);
} while (i <= 5);
```

---

## continue Anahtar Kelimesi

`continue`, Java’da **döngü içinde o turu atlamak** için kullanılır.  
Bulunduğu turda **kalan kodları çalıştırmaz** ve bir sonraki turdan devam eder.

### Örnek Kullanım
```java
// `for` döngüsünde kullanımı
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue; // i 3 olduğunda yazdırma işlemi atlanır
    }
    System.out.println(i);
}

// `while` döngüsünde kullanımı
int i = 0;

while (i < 5) {
    i++;
    if (i == 2) {
        continue; // i = 2 turu atlanır
    }
    System.out.println(i);
}

// `do-while` döngüsünde kullanımı
int i = 0;

do {
    i++;
    if (i == 4) {
        continue; // i = 4 turunu atlar
    }
    System.out.println(i);
} while (i < 5);
```
---

## Ekstralar

> Bu başlık altında, egzersizlerde kullandığımız ancak konu anlatımı sırasında anlatmadığımız veya detaylı açıklamadığımız kavramları ele alacağız.  
> Böylece örneklerde geçen yeni ifadeler veya yapılar eksiksiz şekilde anlaşılmış olacak.

---

### String.equals()

`equals()` metodu, iki metnin (String) **içeriklerini karşılaştırmak** için kullanılır.

#### Ne İşe Yarar?

- İki String değerin içerik olarak aynı olup olmadığını kontrol eder.
- `==` operatörünün yaptığı gibi adres karşılaştırması yapmaz.
- Kullanıcı adı, şifre, metin kontrolü gibi işlemlerde kullanılır.

#### Neden `==` Kullanılmaz?

`==` operatörü String ifadelerde:
- Bellek adresini karşılaştırır.

`equals()` metodu ise:
- Metnin içeriğini karşılaştırır.

Bu yüzden String karşılaştırmalarında **daima `equals()` kullanılmalıdır.**

#### Genel Yapı

```java
metin1.equals(metin2);
```

---

## Egzersiz

#### 1. ATM Programı
Döngü yardımıyla bir tane ATM programı yapalım.

İşlemler : <br>
1. işlem : Bakiye öğrenme <br>
2. işlem : Para çekme <br>
3. işlem : Para yatırma <br>
Çıkış : q veya Q

> **NOT**
>
> `scanner` metodunu kullanarak char ataması yapmak için aşağıdaki formül kullanılmaktadır. Diziler konusunda neden kullanıldığı detaylı anlaşılacaktır.
> 
> char islem = input.nextLine().charAt(0);

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        Scanner input = new Scanner (System.in);

        System.out.println("---------------------------");
        System.out.println("Hesabınız Hoşgeldiniz");
        System.out.println("---------------------------");

        String islemler = "1. Bakiye öğrenme\n"
                         +"2. Para çekme\n"
                         +"3. Para yatırma\n"
                         +"Çıkış için q'ya basınız\n";

        double bakiye = 1000;
        int tutar;
        boolean sistemCalisiyorMu = true;

        while (sistemCalisiyorMu) {
            System.out.println(islemler);
            System.out.print("Lütfen yapmak istediğiniz işlemi seçiniz : ");
                String islem = input.next();
            System.out.println("---------------------------");

            switch (islem) {
                case "1" :
                    System.out.println("Güncel Bakiyeniz : " + bakiye);
                    System.out.println("---------------------------");
                    break;

                case "2" :
                    while (true) {
                        System.out.print("Çekmek istediğiniz tutar : ");
                            tutar = input.nextInt();

                        if (tutar < bakiye) {
                            bakiye -= tutar;

                            System.out.println("---------------------------");
                            System.out.println("Hesabınızdan " + tutar + " tl çekilmiştir");
                            System.out.println("Güncel Bakiyeniz : " + bakiye);
                            System.out.println("---------------------------");
                            break;
                        } else {
                            System.out.println("Bakiyeniz yetersiz...");
                            System.out.println("Lütfen geçerli bir tutar giriniz...");
                        }
                    }
                    break;

                case "3" :
                    while (true) {
                        System.out.print("Yatırmak istediğiniz tutar : ");
                        tutar = input.nextInt();

                        if (tutar > 0) {
                            bakiye += tutar;

                            System.out.println("---------------------------");
                            System.out.println("Hesabınıza " + tutar + " tl yatırılmıştır");
                            System.out.println("Güncel Bakiyeniz : " + bakiye);
                            System.out.println("---------------------------");
                            break;
                        } else {
                            System.out.println("Tutar 0 dan küçük olamaz...");
                            System.out.println("Lütfen geçerli bir tutar giriniz...");
                        }
                    }
                    break;


                case "q" :
                case "Q" :
                    System.out.println("Çıkış yapılıyor...");
                    System.out.println("İyi Günler...");
                    sistemCalisiyorMu = false;
                    break;

                default:
                    System.out.println ("Geçersiz değer girişi...");
                    System.out.println("Tekrar Deneyiniz...");
                    System.out.println("---------------------------");
            }
        }

    }
}
```

</details>

#### 2. Armstrong Sayı Bulma
Kullanıcıdan alınan sayının armstrong olup olmadığını bulan bir program yazın.

Armstrong sayı : N haneli bir sayının basamaklarının n'inci üstlerinin toplamı, sayının kendisine eşitse böyle sayılara Armstrong sayı denir.
Örneğin :
    407 = 4³ + 0³ + 7³ = 407

> **NOT**
>
> Burada matematiksel olarak bir çok ifade ile yazım yapılabilir. Bu yüzden 2 tane örnek gösterilmiştir.
>
> `Math.pow()` her zaman double çıktı verir. Bu da 2. örnekte sorun yaşama ihtimali doğurur.

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.println("---------------------------------------");
        System.out.println("Armstrong Sayı Bulma Programı");
        System.out.println("---------------------------------------");

        System.out.print("Lütfen sayınızı giriniz : ");
        int sayi = input.nextInt();

        int kontrol = sayi;
        int basamakSayisi = 0;
        int toplam = 0;

        while (kontrol > 0) {
            kontrol /= 10;
            basamakSayisi++;
        }

        kontrol = sayi;

        while (kontrol > 0) {

            int basamak = kontrol % 10;
            int usSonuc = 1;

            for (int i = 0; i < basamakSayisi; i++) {        |
                usSonuc *= basamak;                          |        Bu ifadeyle de aynı sonuça ulaşılabilir.
            }                                                |        //toplam += (int) (Math.pow(basamak, basamakSayisi));
                                                             |
            toplam += usSonuc;                               |

            kontrol /= 10;
        }

        if (toplam == sayi) {
            System.out.println("Armstrong sayıdır.");
        } else {
            System.out.println("Armstrong sayı değildir.");
        }
    }
}
```

</details>

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        Scanner input = new Scanner (System.in);

        int sayac = 0;
        int toplam = 0;
        int yardimci1 = 0;
        int yardimci2 = 0;

        System.out.println("---------------------------------------");
        System.out.println("Armstrong Sayı Bulma Programı");
        System.out.println("---------------------------------------");

        System.out.print("Lütfen sayınızı giriniz : " );
            int sayi = input.nextInt();

        int kontrol = sayi;

        while (true) {

            kontrol = kontrol / 10;

            if (kontrol == 0) {
                sayac++;
                break;
            }

            sayac++;
        }

        kontrol = sayi;
        yardimci1 = sayac;

        while (sayac > 0) {
            yardimci2 = (int) (kontrol / Math.pow(10, sayac - 1));
            toplam += (int) ( (Math.pow(yardimci2,yardimci1)));
            kontrol = (int) (kontrol % Math.pow(10, sayac - 1));
            sayac--;
        }

        if (toplam == sayi) {
            System.out.println("Armstrong sayıdır.");
        } else {
            System.out.println("Armstrong sayı değildir.");
        }

    }

}
```

</details>

#### 3. İç İçe For Döngüsüyle Çarpım Tablosu Oluşturma

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
public class Test {
    public static void main (String[] args) {
        for (int i = 1; i <= 10; i++) {
            for (int j = 1; j <= 10; j++) {
                System.out.println(i + "x" + j + "=" + i * j);
            }
        System.out.println("----------------------------");
        }
    }
}
```

</details>

#### 4. While Döngüsü ile Kullanıcı Girişi Programı
Kullanıcıdan kullanıcı adı ve şifre bilgilerini alarak doğruluğunu kontrol eden ve en fazla 3 deneme hakkı bulunan bir giriş sistemi yazınız.

<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        Scanner input = new Scanner(System.in);

        String kullaniciAdi = "developer";
        String sifre = "java";
        int hak = 3;



        while (hak > 0) {
            System.out.println("--------------------------");
            System.out.print("Kullanıcı Adı : ");
            String kullaniciAdi_test = input.nextLine();
            System.out.print("Şifre : ");
            String sifre_test = input.nextLine();
            System.out.println("--------------------------");

            if (kullaniciAdi_test.equals(kullaniciAdi) && sifre_test.equals(sifre)) {
                System.out.println("Giriş Başarılı...");
                break;
            }
            System.out.println("Kullanıcı adı veya şifre hatalı!");
            System.out.println("Tekrar Deneyiniz...");
            hak--;
        }
        if (hak == 0) {
            System.out.println("3 kez yanlış deneme yapıldı.");
            System.out.println("Sistemden Çıkılıyor...");
        }
    }
}
```

#### 5. Faiz Uygulaması

Kullanıcıdan yatırmak istediği **anapara** tutarını alın.  
Parayı **aylık mı yoksa yıllık mı** vadeli yatırmak istediğini sorun.  
Seçime göre kaç **ay** veya kaç **yıl** vadeli yatıracağını öğrenin.  
(%40 yıllık ≈ %3 aylık)

Program:
- Her ay sonunda oluşan **faiz getirisini**
- Vade sonunda **toplam anapara + faiz** tutarını
- Vade sonunda toplam faizi 

ekrana yazdırmalıdır.


<details>
<summary>📌 Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Test {
    public static void main (String[] args) {

        Scanner input = new Scanner(System.in);
        int sure = 0;
        double toplamFaiz = 0;
        double faizTutari = 0;
        double yeniMiktar = 0;

        System.out.println("----------------------------");
        System.out.println("Faiz hesaplama uygulamasına hoşgeldiniz");
        System.out.println("----------------------------");

        System.out.print("Faize koyacağınız ana para tutarı : ");
            int anapara = input.nextInt();
        System.out.print("Ay için 1'i \n" + "Yıl için 2'i tuşlayın.");
            int seçim = input.nextInt();

        switch (seçim) {
            case 1 :
                System.out.print("Kaç aylığına yatırılacak : ");
                    sure = input.nextInt();

                faizTutari = anapara * 0.03;
                toplamFaiz = faizTutari * sure;
                yeniMiktar = anapara + toplamFaiz;

                System.out.println("----------------------------");
                System.out.printf("Yatırılan para : %d\n", anapara);
                System.out.printf("Aylık faiz tutarı : %.2f\n", faizTutari);
                System.out.printf("Toplam faiz : %.2f\n", toplamFaiz);
                System.out.printf("Vadeli hesap bitişi sonrası yeni bakiye : %.2f", yeniMiktar);

                break;

            case 2 :
                System.out.print("Kaç yıllığına yatırılacak : ");
                    sure = input.nextInt();

                faizTutari = anapara * 0.40;
                toplamFaiz = faizTutari * sure;
                yeniMiktar = anapara + toplamFaiz;

                System.out.println("----------------------------");
                System.out.printf("Yatırılan para : %d\n", anapara);
                System.out.printf("Yıllık faiz tutarı : %.2f\n", faizTutari);
                System.out.printf("Toplam faiz : %.2f\n", toplamFaiz);
                System.out.printf("Vadeli hesap bitişi sonrası yeni bakiye : %.2f", yeniMiktar);

                break;

            default:
                System.out.println("Geçersiz değer girdiniz.");
                System.out.println("Çıkış yapılıyor....");

        }
    }
}
```

</details>


</details>
---

### 📚 Konu Akışı

**⬅️ Önceki:** [**Koşullu Durumlar ve Kod Blokları**](04-KoşulluDurumlar-KodBlokları.md)   
**➡️ Sonraki:** [**Metodlar ve Metodlarda Overloading**](06-Metodlar-MetodlardaOverloading.md)
