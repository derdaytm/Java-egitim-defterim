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

### 📚 Konu Akışı

**⬅️ Önceki:** [**Temel Operatörler**](02-Temel-Operatörler.md)   
**➡️ Sonraki:** [**Koşullu Durumlar ve Kod Blokları**](04-KoşulluDurumlar-KodBlokları.md)
