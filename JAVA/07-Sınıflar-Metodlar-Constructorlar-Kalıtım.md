## OOP (Object Oriented Programming) Nedir?

> **NOT**: <br>
> Bu kısımda bazı yerler anlaşılmayabilir böyle bir durumda ilerlemeye devam edin.
> Tekrar anlamadığımız yere aaa! dediğiniz kısımda dönebilirsiniz.
> Döndüğünüzde daha anlaşılır olduğunu fark edeceksiniz.

**OOP (Nesne Yönelimli Programlama)**, programı **gerçek hayattaki nesneleri modelleyerek** yazma yaklaşımıdır.

Amaç:
- Daha **düzenli**,
- Daha **okunabilir**,
- Daha **bakımı kolay**,
- Daha **genişletilebilir** kod yazmaktır.

---

## OOP’ye Neden İhtiyaç Duyarız?

Şöyle düşün, kod büyüdükçe:

- Her şey `main` içinde olur.
- Kod karmaşıklaşır.
- Değişiklik yapmak zorlaşır.
- Aynı kodlar tekrar tekrar yazılır.

OOP, bu problemleri çözmek için ortaya çıkmıştır.

---

## OOP’nin Temel Mantığı

OOP der ki:

> “Programını **nesnelerden** oluştur.”

Yani:
- Her şey tek tek değişkenler değil.
- **Birbirleriyle ilişkili özellikler ve davranışlar** bir arada olmalı. 

---

## Gerçek Hayat Benzetmesi

Bir **Araba** düşünelim:

Arabanın:
- Özellikleri: (veriler)
  - marka
  - renk
  - hız
- Davranışları: (işlevler)
  - çalıştır()
  - hızlan()
  - dur()

İşte OOP tam olarak bunu yapar.

### Java’daki Karşılıkları

- **Araba** → `class` (sınıf)  
- **marka, renk, hız** → değişkenler (**fields / attributes**)  
- **çalıştır(), hızlan(), dur()** → metodlar (**methods**)  

Yani Java’da:
- Bir **class**, gerçek hayattaki bir nesnenin **planıdır**
- Özellikler **değişken** olarak,
- Davranışlar ise **metod** olarak tanımlanır.

Bu sayede:
- Birbirleriyle ilişkili veriler ve işlemler **tek bir yapı altında** toplanır.
- Kod daha **anlaşılır**, **düzenli** ve **yönetilebilir** olur.
---

## Class Nedir?

**Class (Sınıf)**, nesnelerin **taslağı (şablonu)**dır.  
Bir nesnenin:
- Hangi **özelliklere** sahip olacağını,
- Hangi **davranışları** yapabileceğini tanımlar.

---

## Class Ne İşe Yarar?

Class sayesinde:
- Birbirleriyle ilgili **veriler ve metodlar** aynı yerde toplanır.
- Kod **daha düzenli** ve **okunabilir** olur.
- Aynı yapıyı tekrar tekrar kullanabiliriz.
- Büyük projeler daha **kontrol edilebilir** hale gelir.

---

## Java’da Class Nasıl Oluşturulur?

> 📌 **Not: Class ve Dosya Adı**
>
> Java’da bir class oluştururken **ayrı bir dosya** açılır.  
> Dosya adı, **class adıyla aynı** olmak zorundadır.
> 
> <img width="157" height="72" alt="image" src="https://github.com/user-attachments/assets/ff30117f-4687-4c9a-b962-a686f35f6d12" />
>
> Burada `test` bizim `main` metodumuuzun olduğu `class`. (Az sonra arabayı tanımlayacağız)


Java’da bir class, `class` anahtar kelimesi ile tanımlanır.

### Temel Yapı
```java
class ClassAdi {
    // değişkenler (özellikler)
    // metodlar (davranışlar)
}
```

#### Örnek Kullanım
```java
public class Araba {

}
```

### Bu Class Ne Anlatıyor?

- **Araba** → class adı (gerçek hayattaki araba)

 **Bu aşamada:**
- Henüz gerçek bir **araba (nesne)** yok. Sadece `class`'ımızı oluşturduk.

## Önemli Not

- Java’da **public class** varsa:
  - Class adı ile **dosya adı aynı olmalıdır**.

- Class isimleri:
  - **Büyük harfle** başlar.  
    - `Araba`
    - `Ogrenci`
    - `User`

> Eğer `class` tanımlamayı / oluşturmayı öğrendiğinizi düşünüyorsanız özellik eklemeye geçebilirsiniz. Aksi halde tekrar etmenizi veya konu ile ilgili video anlatım dinlemenizi öneririm.

---

## Class’a Özellik (Değişken) Ekleme

Bir class’ın **özellikleri**, o nesnenin **bilgilerini tutan değişkenlerdir**.  
Java’da bu özellikler farklı **erişim belirleyiciler** ile tanımlanabilir.

4 tane erişim belirleyicimiz vardır. Bunlar:
- `public`
- `private`
- `protected`
- `default`

Şimdilik konuyu anlatabilmek amaçlı sadece `public`'i kullanacağız.

---

## Public ile Özellik Ekleme

Bir class’a **özellik eklemek**,  `class` süslü parantezleri `{ }` içine **değişken tanımlamak** demektir.

## Nasıl Eklenir?

1. Class oluşturulur.
2. Class’ın içine `public` ile veri tipi ve değişken adı yazılır.

## Temel Kullanım

```java
public class Araba {
    public String marka;
    public String renk;
    public int kilometre;
    public double motorHacmi;
    public double fiyat;
    public boolean calisiyorMu;
}
```

---

## Nesne (Object) Oluşturma

Bir class **tek başına kullanılmaz**.  
Class sadece bir **şablondur**.

Bir class’ı kullanabilmek için ondan **nesne (object)** oluşturmamız gerekir.

## Nesne Nasıl Oluşturulur?

### Temel Sözdizimi
```java
ClassAdi nesneAdi = new ClassAdi();
```

### Mevcut Yapımız

<img width="157" height="72" alt="image" src="https://github.com/user-attachments/assets/ff30117f-4687-4c9a-b962-a686f35f6d12" />

Burada Test classımızın içinde nesnemizi oluşturuyoruz:

```java
public class Test {
    public static void main(String[] args) {

        Araba araba1 = new Araba();
    }
}
```

## Class – Nesne Mantığı

- **Class** → Plan / Kalıp / Şablon
- **Nesne (Object)** → O plandan üretilmiş gerçek şey

`Araba` class’ı:
> “Araba nasıl olur?” sorusunun cevabıydı.

`araba1` nesnesi:
> O tanıma göre oluşturulmuş **gerçek bir araba**.

Burada :
`Araba` → class adı
`araba1` → nesne adı
`new` → yeni bir nesne oluşturur

> Bu format size de tanıdık geldi mi?
> Scanner sınıfında da bu şekilde sınıf oluşturarak erişim sağlıyorduk...

---

## Özelliklere Erişme ve Atama Yapma (Public için)

### Mevcut Yapımız

Şu anda projemizde **2 tane class** var:

- **Araba** → Özellikleri tanımladığımız class
- **Test** → `main` metodunun olduğu, deneme yaptığımız class
- ve `main` metodunun içinde `araba1` nesnemiz.

### Araba Class’ı

```java
public class Araba {

    public String marka;
    public String model;
    public String renk;

    public int kapıSayisi;
    public int kilometre;
    public int motorHacmi;

    public double fiyat;

    public boolean calisiyorMu;
}
```

Bu class: 
- Sadece **arabanın özelliklerini** tanımlar.
- Çalışmaz
- Tek başına bir şey yapmaz.

### Test Class'ı
```java
public class Test {
    public static void main(String[] args) {

        Araba araba1 = new Araba();

        araba1.marka = "Renault";
        araba1.model = "Clio";
        araba1.renk = "beyaz";
        araba1.kapıSayisi = 4;
        araba1.kilometre = 10241;
        araba1.motorHacmi = 1499;
        araba1.fiyat = 120254.96; // virgül yerine nokta kullanmalıyız
        araba1.calisiyorMu = true;

        System.out.println("Marka: " + araba1.marka);
        System.out.println("Model: " + araba1.model);
        System.out.println("Renk: " + araba1.renk);
        System.out.println("Kapı Sayısı: " + araba1.kapıSayisi);
        System.out.println("Kilometre: " + araba1.kilometre);
        System.out.println("Motor Hacmi: " + araba1.motorHacmi);
        System.out.println("Fiyat: " + araba1.fiyat);
        System.out.println("Çalışıyor mu?: " + araba1.calisiyorMu);
    }
}
```
