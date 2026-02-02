## JAVA Hakkında

- Java **platform bağımsızdır**. (windowsta yazılan linuxda da çalışabilir)
- Java **nesneye yönelik** bir programlama dilidir.
- Java’da **pointer yoktur**, **referans** kullanılır.
- Java **geriye dönük uyumludur** (eski sürüm kodları yeni sürümlerde çalışır).
- **Java hem derlenen hem yorumlanan bir dildir**:  
  Java kodu önce **bytecode**’a derlenir, sonra **JVM** tarafından çalıştırılır.

  - **Diğer dillerle farkı**:  
    C / C++ → Doğrudan makine koduna derlenir (platforma bağımlı)  

  - **Sonuç**:  
    JVM sayesinde hem yorumlanan hem derlenen kod platforma bağımsız şekilde çalışabilir.

- **Java çalışma mantığı**:  
  Java kaynak kodu **`.java`** dosyalarında bulunur.  
  Bu kodlar önce derlenerek **bytecode**’a dönüştürülür ve **`.class`** dosyalarında saklanır.  
  Oluşan bytecode, **JVM** tarafından yorumlanarak işletim sistemine uygun şekilde çalıştırılır.

- **JDK (Java Development Kit)**:  
  Java uygulaması geliştirmek için gerekli tüm araçları içerir (derleyici, JRE vb.).

- **JRE (Java Runtime Environment)**:  
  Java uygulamalarını çalıştırmak için gerekli ortamı sağlar.

- **JVM (Java Virtual Machine)**:  
  Java bytecode’unu işletim sistemine uygun şekilde çalıştıran sanal makinedir.

---

### Java Temel Yapısı (Hello World)

- Java’da her program **class** içinde yazılır.
- Programın çalışmaya başladığı yer **main metodu**dur.
- JVM, programı çalıştırırken ilk olarak **main** metodunu arar.

#### Örnek Kullanım

```java
public class Deneme {
    public void main(String[] args){
        System.out.println("Hello World!");
    }
}

```

**Konsol Çıktısı:**

<img width="604" height="67" alt="image" src="https://github.com/user-attachments/assets/93d38009-1400-4910-9d35-2386915918de" />

### Temel Yapı Açıklamaları
- **public**: Bu sınıfa ve metoda her yerden erişilebileceğini belirtir.
- **class**: Java’da kodların yazıldığı temel yapıdır.
- **static**: main metodunun nesne oluşturulmadan çalışmasını sağlar.
- **void**: Metodun geri dönüş değeri olmadığını ifade eder.
- **String[] args**: Program çalıştırılırken dışarıdan alınan parametreleri temsil eder.

> **NOT**:  
> Bu başlık altındaki kavramlar şu an temel seviyede açıklanmıştır.  
> Java konularını ilerledikçe (**class, method, static, parametreler** gibi) bu ifadelerin ne anlama geldiği daha net şekilde anlaşılacaktır.

---

### Konsola Çıktı Yazdırmak

- `System.out.print()` ve `System.out.println()` kullanılır.
- Programın çalıştığını ve sonuç ürettiğini görmek için en temel araçtır.

#### Temel Kurallar / Özellikler
- **System**: Java’nın hazır (built-in) sınıflarından biridir.
- **out**: Konsola çıkışı temsil eder.
- **println**: Verilen değeri yazdırır ve alt satıra geçer.
- **print**: Verilen değeri yazdırır.

> **NOT**: <br>
> `print` ve `println` arasındaki tek fark alt satıra geçme özelliğidir.

#### Örnek Kullanım
```java
System.out.println("Merhaba Java");
System.out.println(10);
```

**Konsol Çıktısı**

<img width="654" height="92" alt="image" src="https://github.com/user-attachments/assets/714a8939-f4c7-4790-9684-a61ec5ab2132" />

---

### Yorum Satırları (Comments)

- Kodun ne yaptığını açıklamak için kullanılır.
- Programın çalışmasını etkilemez.
- Okunabilirliği ve anlaşılabilirliği artırır.

#### Temel Kurallar / Özellikler
- Yorum satırları Java tarafından **çalıştırılmaz**.
- Kodun **neden** yazıldığını açıklamak için tercih edilir.
- Gereksiz ve tekrar eden yorumlardan kaçınılmalıdır.

#### Yorum Türleri

- **Tek satırlık yorum**: `//`
- **Çok satırlı yorum**: `/* ... */`

#### Örnek Kullanım
```java
// Bu tek satırlık bir yorumdur
int age = 25;

/*
 Bu çok satırlı
 bir yorum örneğidir
*/
int count = 10;
```

> **NOT**:<br>
> İyi yazılmış kod, az ama açıklayıcı yorum içerir.

---

### Değişken Tanımlama

- `int`, **tam sayıları** saklamak için kullanılır. (Diğer değişken türlerini az sonra göreceğiz)
- Java’da değişkenler **kullanılmadan önce tanımlanmalıdır**.

#### Temel Kurallar / Özellikler
- Değişken türü en başta yazılır. (Örn : int)
- Değişkene sonradan farklı türde değer atanamaz. (tam sayı yerine kelime atamak gibi)
- `int` negatif ve pozitif tam sayıları tutabilir.

#### Örnek Kullanım
```java
int age = 25;
int count = 10;
```

#### Değişken Adlandırma Kuralları (int)

- Değişken adı **harf**, **_ (alt çizgi)** veya **$** ile başlayabilir.
- **Rakamla başlayamaz**.
- Boşluk içeremez.
- Java **büyük-küçük harfe duyarlıdır**.
- Anlamlı ve açıklayıcı isimler tercih edilmelidir.

> **NOT**: <br>
> Değişken adlandırırken camelCase kullanılmalıdır.
> - **camelCase kullanımı**:  
> Değişken adı küçük harfle başlar, sonraki kelimelerin ilk harfi büyük yazılır (`userAge`, `totalCount`).


#### Kapsamlı Örnekler:
```java
int age = 30;          // geçerli, anlamlı isim
int your_birthday = 2025 // Alt tire kullanımı
int userAge = 25;      // camelCase kullanımı
int score = -5;        // int negatif değer alabilir
```

Tanımlandıktan sonra değer atamak:
```java
int number;
number = 10;           // önce tanımlama, sonra değer atama
```

Geçersiz kullanımlar:
```java
int 1number;      // rakamla başlayamaz
int user age;     // boşluk içeremez
int total-count;  // özel karakter kullanılamaz
```

---

### Değişken Türleri

#### Tam Sayı Türleri
- **byte** → Küçük tam sayılar için kullanılır
- **short** → byte’tan büyük, int’ten küçük tam sayılar
- **int** → En sık kullanılan tam sayı türü
- **long** → Çok büyük tam sayılar için kullanılır

#### Ondalıklı Sayı Türleri
- **float** → Ondalıklı sayılar (daha az hassas)
- **double** → Ondalıklı sayılar (daha hassas, varsayılan)

#### Karakter Türü
- **char** → Tek bir karakter tutar (`'a'`, `'1'` gibi)

#### Mantıksal Tür
- **boolean** → `true` veya `false` değerini tutar

---

### byte Veri Tipi

- `byte`, Java’da **küçük tam sayıları** saklamak için kullanılır.
- Bellekten tasarruf edilmesi gereken durumlarda tercih edilir.

#### Temel Kurallar / Özellikler
- **8 bit** yer kaplar.
- **1 byte**’a eşittir.
- Negatif ve pozitif tam sayıları tutabilir.
- `int`’e göre çok daha küçük bir aralığa sahiptir.

#### Değer Aralığı
- **Minimum değer**: `-128`
- **Maksimum değer**: `127`

#### Örnek Kullanım
```java
byte level = 10;
byte maxUser = 50;

//Aşağıdaki şekilde de min ve max değerlerini öğrenebiliriz

System.out.print("byte minimum değeri: ");
System.out.println(Byte.MIN_VALUE);

System.out.print("byte maksimum değeri: ");
System.out.println(Byte.MAX_VALUE);

```

---

### short Veri Tipi

- `short`, Java’da **orta büyüklükte tam sayıları** saklamak için kullanılır.
- `byte` ile `int` arasında bir tam sayı türüdür.

#### Temel Kurallar / Özellikler
- **16 bit** yer kaplar.
- **2 byte**’a eşittir.
- Negatif ve pozitif tam sayıları tutabilir.
- `byte`’tan daha geniş, `int`’ten daha dar bir aralığa sahiptir.

#### Değer Aralığı
- **Minimum değer**: `-32,768`
- **Maksimum değer**: `32,767`

#### Örnek Kullanım
```java
short year = 2025;
short temperature = -10;

//Aşağıdaki şekilde de min ve max değerlerini öğrenebiliriz

System.out.print("short minimum değeri: ");
System.out.println(Short.MIN_VALUE);

System.out.print("short maksimum değeri: ");
System.out.println(Short.MAX_VALUE);

```

---

### int Veri Tipi

- `int`, Java’da **tam sayıları** saklamak için kullanılan temel veri tipidir.
- En sık kullanılan sayısal veri tiplerinden biridir.

#### Temel Kurallar / Özellikler
- **32 bit** yer kaplar.
- **4 byte**’a eşittir.
- Negatif ve pozitif tam sayıları tutabilir.

#### Değer Aralığı
- **Minimum değer**: `-2,147,483,648`
- **Maksimum değer**: `2,147,483,647`

> **NOT**  
> Bu sınırlar Java tarafından sabittir ve `Integer` sınıfı üzerinden erişilebilir.

### Örnek Kullanım
```java
int age = 25;
int count = 100;

//Aşağıdaki şekilde de min ve max değerlerini öğrenebiliriz

System.out.print("int minimum değeri: ");
System.out.println(Integer.MIN_VALUE);

System.out.print("int maksimum değeri: ");
System.out.println(Integer.MAX_VALUE);
```

---

### long Veri Tipi

- `long`, Java’da **çok büyük tam sayıları** saklamak için kullanılır.
- `int` türünün yetersiz kaldığı durumlarda tercih edilir.

#### Temel Kurallar / Özellikler
- **64 bit** yer kaplar.
- **8 byte**’a eşittir.
- Negatif ve pozitif tam sayıları tutabilir.
- Sayı sonuna `L` veya `l` eklenerek tanımlanır (önerilen `L`).

#### Değer Aralığı
- **Minimum değer**: `-9,223,372,036,854,775,808`
- **Maksimum değer**: `9,223,372,036,854,775,807`

> **NOT**:<br> 
> Büyük tam sayılar atanırken sonuna `L` eklenmezse derleme hatası alınabilir.

#### Örnek Kullanım
```java
long population = 8500000000L;
long distance = 1234567890123L;

//Aşağıdaki şekilde de min ve max değerlerini öğrenebiliriz

System.out.print("long minimum değeri: ");
System.out.println(Long.MIN_VALUE);

System.out.print("long maksimum değeri: ");
System.out.println(Long.MAX_VALUE);

```

---

### Tam Sayı Türleri Arası Dönüşüm (Type Casting)

Java’da tam sayı türleri arasında **küçükten büyüğe** doğru yapılan dönüşümler sorunsuzdur.  
Ancak **büyükten küçüğe** dönüşümlerde veri kaybı yaşanabilir.

#### Sorunsuz Dönüşüm (Otomatik – Widening)
```text
byte → short → int → long
```

- Bu dönüşümler **otomatik** yapılır.
- Veri kaybı olmaz.
- Ek bir işlem gerekmez.

#### Örnek Kullanım
```java
byte b = 10;
short s = b;
int i = s;
long l = i;
```

#### Sorunlu Dönüşüm (Daraltma – Narrowing)
```text
long → int → short → byte
```

- Bu dönüşümlerde **veri kaybı riski** vardır.
- Java otomatik dönüşüme izin vermez ve **hata** verir.

#### Örnek Kullanım
```java
int number = 130;
byte b = (byte) number; // burada byte yazılmaması halinde hata verir
System.out.println(b);
```
>**NOT**:<br>
>Gerekli olan dönüşüm tespit edilip parantez içinde ona uygun ifadeye yer verilmelidir.

### float Veri Tipi

- `float`, Java’da **ondalıklı (virgüllü) sayıları** saklamak için kullanılır.
- Bellekten tasarruf edilmesi gereken durumlarda tercih edilir.

#### Temel Kurallar / Özellikler
- **32 bit** yer kaplar.
- **4 byte**’a eşittir.
- Ondalıklı sayılar için kullanılır.
- `double`’a göre **daha az hassastır**.
- Sayı sonuna `f` veya `F` eklenerek tanımlanır ya da sayıdan önce parantez içinde float yazılabilir.

#### Değer Aralığı
- Yaklaşık olarak  
  **Minimum değer**: `1.4E-45`  
  **Maksimum değer**: `3.4E38`

#### Örnek Kullanım
```java
float price = 19.99f;
float average = 3.5F;
float weight = (float) 3.51;

//Aşağıdaki şekilde de min ve max değerlerini öğrenebiliriz

System.out.print("float minimum değeri: ");
System.out.println(Float.MIN_VALUE);

System.out.print("float maksimum değeri: ");
System.out.println(Float.MAX_VALUE);
```

### double Veri Tipi

- `double`, Java’da **ondalıklı (virgüllü) sayıları** saklamak için kullanılan  ve varsayılan veri tipidir.
- `float`’a göre **daha hassas** hesaplamalar yapar. Genelde double tercih edilir.

#### Temel Kurallar / Özellikler
- **64 bit** yer kaplar.
- **8 byte**’a eşittir.
- Ondalıklı sayılar için kullanılır.
- `float`’a göre daha geniş bir değer aralığına ve hassasiyete sahiptir.
- Ondalıklı sayılar varsayılan olarak `double` kabul edilir. Ama istenmesi halinde floattaki tanımlamalar gibi yapılabilir.

#### Değer Aralığı
- Yaklaşık olarak  
  **Minimum değer**: `4.9E-324`  
  **Maksimum değer**: `1.7E308`


#### Örnek Kullanım
```java
double price = 19.99;
double average = 3.14159;

//Aşağıdaki şekilde de min ve max değerlerini öğrenebiliriz

System.out.print("double minimum değeri: ");
System.out.println(Double.MIN_VALUE);

System.out.print("double maksimum değeri: ");
System.out.println(Double.MAX_VALUE);
```

#### Ortak Örnek

```java
int a = 22 / 7;
float b = 22f / 7f;
double c = 22 / 7;

System.out.println("a:" + a);
System.out.println("b:" + b);
System.out.println("c:" + c);
```

Konsol Çıktısı :

<img width="599" height="115" alt="image" src="https://github.com/user-attachments/assets/13b80618-335b-43b8-9230-0bdf97a35100" />

Burada hassasiyet farkı net bir şekilde görülmektedir.

## int, float ve double Arası Dönüşüm

Java’da sayısal veri tipleri arasında dönüşüm yapılabilir.  
Ancak **tam sayılar** ile **ondalıklı sayılar** arasında dönüşümde dikkat edilmesi gereken noktalar vardır.

---

### Sorunsuz Dönüşüm (Otomatik – Widening)

```text
int → float → double
```

- Bu dönüşümler otomatik yapılır.
- Kodda ekstra işlem gerekmez.

#### Örnek Kullanım 
```java
int i = 10;
float f = i;
double d = f;
```

#### Sorunlu Dönüşüm (Daraltma – Narrowing)

```text
double → float → int
```

- Bu dönüşümlerde veri kaybı riski vardır.
- Java otomatik dönüşüme izin vermez.

#### Örnek Kullanım

```java
double number = 10.75;
int i = (int) number; // Burada (int) yazılarak ondalık kısım tamamen atılır
System.out.println(i);
```

```java
double i = 3.52;
float j = (float) i // Burada (float) yazıarak kodu çalışabilir hale getirdik
System.out.println(j);
```

### char Veri Tipi

- `char`, Java’da **tek bir karakter** saklamak için kullanılır.
- Karakterler **tek tırnak (`' '`)** içinde yazılır.

#### Temel Kurallar / Özellikler
- **16 bit** yer kaplar.
- **2 byte**’a eşittir.
- Unicode karakter setini kullanır.
- Harf, rakam ve özel karakter tutabilir.

> **NOT**: <br>
> Java’da `char`, ASCII ile sınırlı değildir, Unicode destekler.

#### Örnek Kullanım
```java
char letter = 'A';
char number = '1';
char symbol = '@';
char a = 1000; // Bu şekilde yaparak 1000 karaktere karşılık gelen değeri alabiliriz
char d = '\u0152';  // unicode karakter numarası girerek değeri atayabiliriz
```

### boolean Veri Tipi

- `boolean`, Java’da **mantıksal değerleri** tutmak için kullanılır.
- Sadece iki değer alabilir: `true` veya `false`.

#### Temel Kurallar / Özellikler
- Koşul kontrollerinde kullanılır.
- Karar yapılarının (`if`, `else`, `while`) temelini oluşturur.
- `boolean` sayısal bir değer değildir.

#### Örnek Kullanım
```java
boolean isActive = true;
boolean isLoggedIn = false;
```

### String Veri Tipi

- `String`, Java’da **metin (yazı) ifadelerini** saklamak için kullanılır.

#### Temel Kurallar / Özellikler
- Değerler **çift tırnak (" ")** içinde yazılır. (Zorunludur)
- Java’da en sık kullanılan veri tiplerinden biridir.

#### Örnek Kullanım
```java
String name = "Ahmet";
String message = "Merhaba Java";
```
`+` ile alt satıra geçilebilir

```java
String a = "Java" +
          "Programlama" +
          "Dili";
```

> **NOT**: <br>
> - `\t` => String içinde kullanılarak 1 tab boşluğu bırakır.
> - `\n` => String içinde kullanılarak alt satıra geçmeyi sağlar.

---

### System.out.println ile Birleştirme (Concatenation)

- `System.out.println`, farklı veri tiplerini **tek bir çıktı halinde** yazdırabilir.
- Bu işlem `+` operatörü ile yapılır.
- `+` operatörü String ile kullanıldığında **birleştirme** görevi görür.

#### Temel Kurallar / Özellikler
- String varsa, diğer veri tipleri otomatik olarak String’e çevrilir.
- Yazdırma işlemi soldan sağa doğru yapılır.
- Sayılar String’den önce gelirse toplama yapılır, sonra birleştirme olur.

#### Örnek Kullanım
```java
String name = "Ahmet";
int age = 25;

System.out.println("İsim: " + name);
System.out.println("Yaş: " + age);
System.out.println("İsim: " + name + "Yaş: " + age); // Bu şekilde de yazılabilir
```

Ancak sıralamasına dikkat etmezsek aşşağıdaki gibi hatalar olabilir.

```java
System.out.println(10 + 5 + " sayı"); // Burada çıktı : 15 sayı
```

```java
System.out.println("Sayı : " + 10 + 5); // Burada çıktı : Sayı : 105
```

```java
System.out.println(12 + 4 + " ahmet " + 6 + 3); // Burada çıktı : 16 ahmet 63
```

> **NOT**:<br>
> Java ifadeleri **soldan sağa doğru** değerlendirir.  
> - Eğer ifade **sayı ile başlar** ve ardından yine **sayı gelirse**, işlem **matematiksel toplama** olarak yapılır.  
> - Ancak **String (yazı)** geldikten sonra tüm ifade **String birleştirme** olarak devam eder.
> Buradaki kural String değişkenine atama yapılırken kullanılan + operatörü içinde geçerlidir.

```java
        int a = 3;
        int b = 5;
        String c = "selam";

        String d = a + b + c + a + b;

        System.out.println(d);
```

Konsol Çıktısı :

<img width="507" height="68" alt="image" src="https://github.com/user-attachments/assets/f0cd311f-bd8d-4887-8f92-d23b05b49458" />
