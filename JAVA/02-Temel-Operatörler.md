## Aritmetik Operatörler

**Aritmetik operatörler**, Java’da sayısal veriler üzerinde matematiksel işlemler yapmamızı sağlayan özel sembollerdir.  
Bu operatörler sayesinde toplama, çıkarma, çarpma, bölme ve kalan bulma gibi temel matematik işlemleri yapılır.

Aritmetik operatörler genellikle **int, float, double, long** gibi **sayısal veri tipleri** ile kullanılır ve işlem sonucunda yine bir değer üretirler.

Kısaca:
- Sayılarla işlem yapmak için kullanılırlar.
- Matematiksel hesaplamaların temelini oluştururlar.
- Programlama sırasında en sık kullanılan operatör grubudur.

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
Bu operatör yalnızca **matematiksel amaçla** kullanılır, **Stringdeki gibi birleştirme** görevi yoktur.


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

#### Örnek Kullanım
```java
int a = 10;
int b = 3;

System.out.println(a % b); // 1
```

---

## Atama ve Artırma/Azaltma Operatörleri

Java’da değişkenlere değer atamak veya mevcut değeri güncellemek için **atama operatörleri** ve **artırma/azaltma operatörleri** kullanılır.

---

### Atama Operatörleri (`=`, `+=`, `-=`, `*=`, `/=`, `%=`)

- `=` → Sağdaki değeri sola atar.
- `+=` → Sola atılan değeri sağdaki ile toplar ve sonucu tekrar sola atar.
- `-=` → Sola atılan değeri sağdaki ile çıkarır ve sonucu tekrar sola atar.
- `*=` → Sola atılan değeri sağdaki ile çarpar ve sonucu tekrar sola atar.
- `/=` → Sola atılan değeri sağdaki ile böler ve sonucu tekrar sola atar.
- `%=` → Sola atılan değeri sağdaki ile bölümünden kalanla günceller.

#### Örnek Kullanım
```java
int x = 10;   // = atama
x += 5;       // x = x + 5 → 15
x -= 3;       // x = x - 3 → 12
x *= 2;       // x = x * 2 → 24
x /= 4;       // x = x / 4 → 6
x %= 4;       // x = x % 4 → 2
```

---

### Artırma (`++`) ve Azaltma (`--`) Operatörleri

Java’da **arttırma ve azaltma operatörleri**, bir değişkenin değerini **1 artırmak veya 1 azaltmak** için kullanılır.  

#### Temel Kurallar / Özellikler
- `++` → Değeri 1 artırır.
- `--` → Değeri 1 azaltır.
- Hem **ön ek** hem de **son ek** şeklinde kullanılabilir.
- Sadece sayısal veri tiplerinde geçerlidir. (`int`, `float`, `double`, `long`)

#### Ön Ek ve Son Ek Farkı

1. **Ön Ek (`++a`, `--a`)**  
   - Değeri **önce** artırır/azaltır.  
   - Sonra kullanılacak değeri üretir.

```java
int a = 5;
System.out.println(++a); // 6 (önce artırıldı sonra konsola basıldı)
```

2. **Son Ek (`a++`, `a--`)**

- Değeri **önce kullanır**.  
- **Sonra** artırır/azaltır. 

#### Örnek Kullanım
```java
int a = 5;
System.out.println(a++); // 5 (önce yazdırıldı sonra konsola basıldı)
System.out.println(a);   // 6 (Konsola basıldığında artık 6 oldu)
```

---

## Parantez ile İşlem Önceliği

Java’da matematiksel işlemlerde **öncelik sırasını değiştirmek** için parantez kullanılır.  
Parantez içindeki işlemler, **her zaman önce yapılır**.

### Temel Kurallar / Özellikler
- `()` → Öncelik belirler.
- Matematikteki işlem önceliği kuralları (çarpma, bölme önce, toplama, çıkarma sonra) geçerlidir.
- Parantez kullanarak karmaşık işlemler daha okunabilir ve hatasız olur.

### Örnek Kullanım
```java
int a = 10;
int b = 5;
int c = 2;

int result1 = a + b * c;       // 10 + (5*2) → 20
int result2 = (a + b) * c;     // (10+5)*2 → 30

System.out.println(result1); // 20
System.out.println(result2); // 30
```

---

## Karşılaştırma ve Mantıksal Operatörler

Java’da **karşılaştırma ve mantıksal operatörler**, koşul ifadelerinde ve karar yapılarında kullanılır.  
Bu operatörler **true** veya **false** sonuç üretir.

---

### Karşılaştırma Operatörleri

| Operatör | Anlamı |
|----------|--------|
| `==`     | Eşit mi? |
| `!=`     | Eşit değil mi? |
| `>`      | Büyük mü? |
| `<`      | Küçük mü? |
| `>=`     | Büyük veya eşit mi? |
| `<=`     | Küçük veya eşit mi? |

#### Örnek Kullanım
```java
int a = 10;
int b = 5;

System.out.println(a == b); // false
System.out.println(a != b); // true
System.out.println(a > b);  // true
System.out.println(a <= 10);// true
```

---

## Mantıksal Operatörler

Mantıksal operatörler, **boolean değerler** üzerinde işlem yapmak için kullanılır ve sonucu **true** veya **false** olur.

| Operatör | Anlamı |
|----------|--------|
| `&&`     | VE (and) → Her iki değer de true olmalı |
| `\|\|`     | VEYA (or) → En az biri true ise true |
| `!`      | DEĞİL (not) → Değerin tersini alır |

#### Örnek Kullanım
```java
boolean isAdult = true;
boolean hasTicket = false;

System.out.println(isAdult && hasTicket); // false → ikisi de true olmalı
System.out.println(isAdult || hasTicket); // true  → biri true ise true
System.out.println(!isAdult);             // false → değeri tersine çevirir
```

---

### Karşılaştırma ve Mantıksal Operatörler – Karmaşık Örnekler

Aşağıdaki örneklerde `==`, `!=`, `<`, `>`, `<=`, `>=` gibi karşılaştırma operatörleri ile  
`&&`, `||`, `!` gibi mantıksal operatörler bir arada kullanılmıştır.  
Çıktılar **true veya false** verir.

---

#### Örnek Kullanım
```java
int x = 8;
int y = 12;
int z = 8;

// Basit karşılaştırmalar
System.out.println(x == z); // true
System.out.println(x != y); // true
System.out.println(x > y);  // false
System.out.println(y >= 12);// true

// Mantıksal VE (&&)
System.out.println((x < y) && (y > 10));   // true → her iki koşul da doğru
System.out.println((x > y) && (y > 10));   // false → ilk koşul yanlış

// Mantıksal VEYA (||)
System.out.println((x > y) || (y == 12));  // true → ikinci koşul doğru
System.out.println((x > y) || (y < 10));   // false → her iki koşul da yanlış

// Negasyon (!)
System.out.println(!(x == y));             // true → x ve y eşit değil
System.out.println(!(x != z));             // true → x ve z eşit

// Karışık örnekler
System.out.println((x == z) && (y != z));               // true → her iki koşul da doğru
System.out.println((x < y) || (y < z) && !(x > y));     // true → parantez ve öncelik ile hesaplanır
System.out.println(!(x > y) && (y >= 12) || (z == 8)); // true → mantıksal kombinasyon

// Daha karmaşık
System.out.println((x + y > z) && (y - x < 5) || !(x == 0)); // true
System.out.println((x * 2 == z * 2) && (y / 2 != 6));         // false
```

---

### 📚 Konu Akışı

**⬅️ Önceki:** [**Değişkenler ve Veri Tipleri**](01-Değişkenler-VeriTipleri.md)   
**➡️ Sonraki:** [**Scanner Sınıfı ve Örnekler**](03-ScannerSınıfı-Örnekler.md)
