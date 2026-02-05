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

---

## Neden Her Zaman `public` Kullanmamalıyız?

`public` ile tanımlanan özelliklere **her yerden serbestçe erişilebilir**.  
Bu ilk başta kolay görünür ama **ciddi sorunlara yol açar**.

## 1️⃣ Kontrolsüz Veri Değişimi

`public` özellikler:
- İstediğimiz değeri,
- İstediğimiz yerden,
- Hiçbir kontrol olmadan,
değiştirmemize izin verir.

```java
araba1.kilometre = -500;   // Mantıksız ama izin verilir
araba1.fiyat = 0;         // Hata ama engel yok
araba1.motorHacmi = -1.6; // Sorunlu
```
> **NOT** : Buradaki kodlar `test` classının içine yazılmıştır.

## 2️⃣ Class Kontrolünü Kaybeder

Bir class:
- Kendi verisini **korumalıdır**.
- Nasıl değiştirileceğine **kendisi karar vermelidir**.

Ama `public` olunca:
- Class sadece bir **veri deposuna** dönüşür.
- İş mantığı class dışına **dağılır**.

## 3️⃣ Hatalı Kullanıma Açık Hale Gelir

Başka biri (veya ileride sen):
- Özellikleri **yanlış** kullanılabilir.
- Değerin **nerede değiştiğini** takip edilemez.
- Hata ayıklama (**debug**) süreci zorlaşır.

## 4️⃣ Gerçek Hayat Mantığına Aykırı

Gerçek hayatta:
- Arabanın kilometresini **herkes kafasına göre** değiştiremez.
- Fiyat **kontrolsüz şekilde** sıfırlanamaz.

Ama `public` olunca:
> “Al, istediğini yap” demiş oluruz.

---

## Çözüm: Encapsulation (Kapsülleme)

`public` kullanımının yol açtığı sorunları çözmek için  
**Encapsulation (kapsülleme)** yaklaşımını uygularız.

Encapsulation’ın temel amacı:
> **Veriyi gizlemek ve erişimi kontrol altına almak**

## Encapsulation Nedir?

Encapsulation, bir class’ın:
- İç detaylarını **dış dünyadan saklaması**.
- Veriye doğrudan erişimi **engellemesi**.
- Erişimin sadece **kontrollü yollarla** sağlanmasıdır.

## Java’da Encapsulation Nasıl Uygulanır?

Encapsulation’ı Java’da **adım adım** uygularız.  
Bu konuyu daha net anlayabilmek için **4 bölümde** ele alacağız:

1️⃣ **Özellikleri `private` yapma**  
→ Veriyi dış dünyadan gizleriz  

2️⃣ **Set metodu (setter)**  
→ Veriye kontrollü şekilde değer atarız  

3️⃣ **Get metodu (getter)**  
→ Veriyi güvenli şekilde okuruz  

4️⃣ **Kapsamlı örnek**  
→ Tüm yapıyı tek bir örnek üzerinde görürüz  

Her bölüm bir öncekini tamamlar.  
Şimdi ilk adımla başlayalım 👇

---

## 1️⃣ Özellikleri `private` Yapma

Encapsulation’ın **ilk ve en önemli adımı**,  
class içindeki özellikleri `private` yapmaktır.

`private` yapılan özelliklere:
- Class **dışından doğrudan erişilemez**.
- Sadece **kendi class’ı içinden** erişilebilir.
  
## Neden `private` Yapıyoruz?

Çünkü:
- Verinin kontrolsüz değişmesini istemeyiz.
- Hatalı değer atamalarını engellemek isteriz.
- Kontrol class’ın kendisinde olmalıdır.

## Private kullanımı 

### Araba Class’ı

```java
public class Araba {

    private String marka;
    private String model;
    private String renk;

    private int kapıSayisi;
    private int kilometre;
    private int motorHacmi;

    private double fiyat;

    private boolean calisiyorMu;
}
```

Şuan `test` classın da bu verilere artık erişemeyiz. Yani artık kontrol class'ın kendisinde.

### Örnek Kullanım 

<img width="732" height="375" alt="image" src="https://github.com/user-attachments/assets/f2e1625d-5ec4-47cc-9a6c-cc303c8c1a64" />

Burada da görüldüğü üzere bahsettiğimiz hatayı aldık.

Şimdi bu hataları çözmek için 2.aşamaya geçelim.

---

## 2️⃣ Set Metodu (Setter)

`set` metodu, `private` yapılmış bir özelliğe **kontrollü şekilde değer atamak** için kullanılır.

## Set Metodu Ne İşe Yarar?

- `private` özelliğe doğrudan erişimi engeller.
- Değer atamayı **class’ın kontrolüne** bırakır.
- **class** set kavramı ile kontrollü bir erişim sağlar.
- Böylelikle hatalı veya mantıksız değerleri **filtreleyebilir**.
  
## Set Metodu Nasıl Yazılır?

### Genel Yapı
```java
public void setDegiskenAdi(veriTipi deger) {
    this.deger = deger;
}
```

Burada kullandığımız set'in aslında bir metod olduğunu unutmayalım.

Burada aslında metod kullandık. 

### Neden `this` Kullanırız?

Class içindeki özellik ile metoda gelen parametrenin **adı aynı olduğunda**, Java hangisini kastettiğimizi **ayırt edemez**.

Bu karışıklığı önlemek için:
- `this.deger` ile **class’a ait olanı**,
- `this` olmadan **parametreyi**(test'ten gönderilen), işaret ederiz.

## Set kullanımı 

### Araba Class’ı

```java
public class Araba {

    private String marka;
    private String model;
    private String renk;

    private int kapıSayisi;
    private int kilometre;
    private int motorHacmi;

    private double fiyat;

    private boolean calisiyorMu;

    // SETTER METODLARI

    public void setMarka(String marka) {
        this.marka = marka;
    }

    public void setModel(String model) {
        this.model = model;
    }

    public void setRenk(String renk) {
        this.renk = renk;
    }

    // Gönderilen veriyi kontrol edebilir ve bir filtreden geçirebiliriz.

    public void setKapiSayisi(int kapiSayisi) {
        if (kapiSayisi > 0) {
            this.kapiSayisi = kapiSayisi;
        } else {
            System.out.println("Hata: Kapı sayısı 0 veya negatif olamaz!");
        }
    }
    
    public void setKilometre(int kilometre) {
        if (kilometre >= 0) {
            this.kilometre = kilometre;
        } else {
            System.out.println("Hata: Kilometre değeri negatif olamaz!");
        }
    }
    
    public void setMotorHacmi(int motorHacmi) {
        if (motorHacmi > 0) {
            this.motorHacmi = motorHacmi;
        } else {
            System.out.println("Hata: Motor hacmi 0 veya negatif olamaz!");
        }
    }
    
    public void setFiyat(double fiyat) {
        if (fiyat > 0) {
            this.fiyat = fiyat;
        } else {
            System.out.println("Hata: Fiyat 0 veya negatif olamaz!");
        }
    }

    public void setCalisiyorMu(boolean calisiyorMu) {
        this.calisiyorMu = calisiyorMu;
    }
}
```

### Test Class’ı

<img width="764" height="500" alt="image" src="https://github.com/user-attachments/assets/09ceca31-c4f9-4aaf-b816-f7c9b07a7a47" />

Şu anda görüldüğü üzere atama yapılırken hiçbir sorunla karşılaşmıyoruz ancak veriyi okumaya yani konsola yazdırmaya çalışırken hata alıyoruz.

Şimdi bu hatayı çözmek için 3.aşamaya geçelim.

---

## 3️⃣ Get Metodu (Getter)

`get` metodu, `private` yapılmış bir özelliğin **değerini okumak** için kullanılır.

Değeri **değiştirmez**, sadece **geri döndürür**.

## Get Metodu Ne İşe Yarar?

- `private` özelliklere **doğrudan erişilemez**.
- Ancak bu değerlere **ihtiyaç duyarız**.
- Getter metodları, bu değerlere **okuma izni** sağlar.

> **Setter** → yazmak için  
> **Getter** → okumak için

## Get Metodu Nasıl Yazılır?

### Genel Yapı
```java
public veriTipi getDegiskenAdi() {
    return degiskenAdi;
}
```

> ***NOT**:
>
> `get` bir anahtar kelime değildir.
>  Yazılan yapı, `set`'tede dediğimiz gibi **normal bir java metodudur.**

## Get Kullanımı

### Araba Class’ı

```java
public class Araba {

    private String marka;
    private String model;
    private String renk;

    private int kapıSayisi;
    private int kilometre;
    private int motorHacmi;

    private double fiyat;

    private boolean calisiyorMu;

/// SETTER metodlarını karışıklık olmaması için yazmadık.

/// GETTER metodları

public String getMarka() {
    return marka;
}

public String getModel() {
    return model;
}

public String getRenk() {
    return renk;
}

public int getKapiSayisi() {
    return kapiSayisi;
}

public int getKilometre() {
    return kilometre;
}

public int getMotorHacmi() {
    return motorHacmi;
}

public double getFiyat() {
    return fiyat;
}

public boolean isCalisiyorMu() {
    return calisiyorMu;
}
````

> **NOT**:
>
> `boolean` tiplerde getter metodları genellikle `get` yerine `is` ile başlar.

### Test Class’ı

```java
public class Test {
    public static void main(String[] args) {

        Araba araba1 = new Araba();

        araba1.setMarka("renault");
        araba1.setModel("Clio");
        araba1.setRenk("Beyaz");
        araba1.setKapiSayisi(5);
        araba1.setKilometre(12504);
        araba1.setMotorHacmi(1500);
        araba1.setFiyat(154000.12);
        araba1.setCalisiyorMu(true);

        System.out.println("Marka : " + araba1.getMarka());
        System.out.println("Model : " + araba1.getModel());
        System.out.println("Renk : " + araba1.getRenk());
        System.out.println("Kapı Sayısı : " + araba1.getKapiSayisi());
        System.out.println("Kilometre : " + araba1.getKilometre());
        System.out.println("Motor Hacmi : " + araba1.getMotorHacmi());
        System.out.println("Fiyat : " + araba1.getFiyat());
        System.out.println("Çalışıyor Mu : " + araba1.isCalisiyorMu());

    }
}
```

**Tarayıcı Çıktısı**

<img width="573" height="224" alt="image" src="https://github.com/user-attachments/assets/8b87dab4-504b-4991-a1f3-a751bf9f1fd7" />

Böylelikle hem atama yapabilir hem okuma yapabilir hemde güvenli bir hale getirdik.

Böylece veriye doğrudan müdahale edilmeden,
hem kontrollü şekilde değer atayabilir,
hem de güvenli biçimde okuyabiliriz.

Şimdi son olarak 4.aşamada kapsamlı bir örnek inceleyelim.

---

