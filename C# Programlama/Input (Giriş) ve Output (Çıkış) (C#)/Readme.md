
Sitemizin C# Programlamada ilk yazısı olan “Hello World !” yazısında ilk output örneğimizi görmüştük. Şimdi bu örneği bu yazımızda daha da pekiştirmiş olacağız.

# Output

Output programa çıktı veren fonksiyondur. Uyarı mesajları, bilgilendirmeler, programda karşımıza çıkan yazıların çoğu output’un eseridir.

İlk olarak basit bir örnek ile başlayalım.

```cpp
Console.Write("hello world");
```

Bu örneğimizde ekrana “hello world” çıktısı vermiş olduk. Yani program başladığı zaman alttaki gibi çıktı vericektir.

```cpp
hello world
```

Örneğimizi biraz daha kompleks hale getirmeye başlayalım.

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int a = 6; // a degiskenini tanimladik
            Console.Write("a sayisi: " + a); // ekrana a harfini "a sayisi: 6" seklinde yazdirdik

        }
    }
}

```

Daha da iyi anlayabilmeniz için aşağıdaki gibi bir gösterim yapılabilir:

```cpp
Console.Write(degiskenAdi);
```

Şimdi ise farklı bir örnek ile ilerleyelim.

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int a = 10, b = 7; // a ve b degiskenini tanimladik

            Console.WriteLine("a sayisi: " + a); // ekrana a degiskenini yazdirdik
            Console.WriteLine("b sayisi: " + b); // ekrana b degiskenini yazdirdik
            Console.WriteLine("a ve b degiskenlerinin toplami: " + (a + b)); ; // a ve b degiskenlerinin toplamini ekrana yazdirdik

            /* WriteLine() fonksiyonu alt satira gecmek icin kullanilir.
             c++'daki "endl" gibi */

        }
    }
}

```

Yukarıdaki örnekte iki tane değişken tanımlayıp toplamlarını ekrana yazdırdık. Bu işlemi yukarıdaki gibi yapabilirsiniz fakat bu pek iyi bir yazım şekli değildir. Bu örnekten farklı olarak aşağıdaki gibi yazılabilir:

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int a = 10, b = 7; // a ve b degiskenini tanimladik
            int c;

            c = a + b;

            Console.WriteLine("a ve b degiskenlerinin toplami: " + c); // a ve b degiskenlerinin toplamini ekrana yazdirdik

        }
    }
}

```

# Input (Girdi)

Input programa girdi alan fonksiyondur. Kullanıcıdan girilen verilerin alınmasının çoğu input’un eseridir. Kullanıcıdan veri almak için “**ReadLine()**” fonksiyonunu kullanırız. Aşağıdaki örnekte konuyu daha net anlayabiliriz:

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int yas; // yas degiskeninin turunu tanimladik

            Console.Write("yasinizi giriniz: "); // kullaniciya yasini girmesi icin cikti gonderdik
            yas = Convert.ToInt32(Console.ReadLine()); // girdiyi almak icin bu fonksiyonu kullandik

            Console.WriteLine("yasiniz: " + yas); // kullanicinin yasini cikti olarak ekrana verdik

            /* !!! ReadLine() fonksiyonu 'string' veri tipinde deger
            dondurur. Bu nedenle bu ornegimizde Convert fonksiyonu
            ile degerimizi int (tam sayi) veri tipine donusturduk. !!!*/

        }
    }
}


```

Daha basit olsun diye aşağıdaki gibi bir formül uygulanabilir:

```cpp
degiskenAdi = Console.ReadLine();
```

# Konuyu bir örnek ile toparlayalım:

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int a, b;

            Console.WriteLine("a sayisini giriniz: ");
            a = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("b sayisini giriniz: ");
            b = Convert.ToInt32(Console.ReadLine());


            Console.WriteLine("a sayisi: " + a + " | b sayisi: " + b);   // bu satirda iki farkli degiskeni ayni ciktida ekrana yazdirdik.

        }
    }
}

```

Ekrana verilen çıktı:

```cpp
a sayisina tam sayi deger giriniz: 5

b sayisina tam sayi deger giriniz: 6

a sayisi: 5 | b sayisi: 6
```
