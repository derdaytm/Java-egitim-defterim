## Aritmetik Operatörler

**Aritmetik operatörler**, Java’da sayısal veriler üzerinde matematiksel işlemler yapmamızı sağlayan özel sembollerdir.  
Bu operatörler sayesinde toplama, çıkarma, çarpma, bölme ve kalan bulma gibi temel matematik işlemleri yapılır.

Aritmetik operatörler genellikle **int, float, double, long** gibi **sayısal veri tipleri** ile kullanılır ve işlem sonucunda yine bir değer üretirler.

Kısaca:
- Sayılarla işlem yapmak için kullanılırlar
- Matematiksel hesaplamaların temelini oluştururlar
- Programlama sırasında en sık kullanılan operatör grubudur

---

### `+` Operatörü (Toplama ve Birleştirme)

`+` operatörü Java’da **iki farklı amaçla** kullanılır:

#### Toplama (Matematiksel İşlem)
Eğer `+` operatörünün iki tarafında da **sayısal veri tipi** varsa, **toplama işlemi** yapar.

#### Örnek Kullanım
```java
int a = 10;
int b = 5;

System.out.println(a + b); // 15
```

>**NOT**:<br>
> Birleştirme amaçlı kullanımını `System.out.print()` ve `String` kısmında gördük.

---

### `-` Operatörü (Çıkarma)

`-` operatörü Java’da **sayısal değerler arasında çıkarma işlemi** yapmak için kullanılır.  
Bu operatör yalnızca **matematiksel amaçla** kullanılır, **String birleştirme** gibi bir görevi yoktur.


#### Temel Çıkarma İşlemi

#### Örnek Kullanım
```java
int a = 20;
int b = 8;

System.out.println(a - b); // 12
```

#### Negatif Değer Oluşturma

#### Örnek Kullanım 
```java
int number = -10;
// veya
int number = 10;
System.out.println(-number); // -10
```

---

### `*` Operatörü (Çarpma)

`*` operatörü Java’da **sayısal değerleri çarpmak** için kullanılır.  
Matematikteki çarpma işlemiyle **aynı mantıkta** çalışır.

---

#### Temel Kullanım

İki sayıyı çarpar ve sonucu üretir.

#### Örnek Kullanım
```java
int a = 4;
int b = 5;

System.out.println(a * b); // 20

int c = 6;

System.out.println(a * b * c); //120
```

---

### `%` Operatörü (Mod – Kalan Bulma)

`%` operatörü Java’da **bir sayının diğerine bölümünden kalanı** bulmak için kullanılır.  
Bu işleme **modulus** veya **mod** denir.

#### Temel Kullanım

Bir sayının diğerine bölümünden kalan değeri verir.

#### Örnek Kullanım
```java
int a = 10;
int b = 3;

System.out.println(a % b); // 1
```

---

