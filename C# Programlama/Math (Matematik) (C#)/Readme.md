

## Math.Max() ve Math.Min() Fonksiyonları

max() ve min() fonksiyonları, iki sayı arasında karşılaştırma yapmayı sağlayan fonksiyonlardır. Basit bir örnek ile konuyu anlamaya çalışalım:

```cpp
using System;

namespace matematik
{
    class Program
    {
        static void Main()
        {

            int a = 9, b = 7;

            Console.WriteLine("buyuk sayi: " + Math.Max(a, b));
            Console.WriteLine("kucuk sayi: " + Math.Min(a, b));

        }
    }
}
```

a ve b tam sayı değişkenleri tanımladık ve değerler atadık. Ekrana verilen ilk çıktıda a ve b arasında Math.Max() fonksiyonu karşılaştırma yaptı ve değeri büyük olan değişkeni ekrana yazdırdı. Benzer işlemi ikinci çıktıda da yaptık. a ve b arasında Math.Min() fonksiyonu karşılaştırma yaptı ve değeri küçük olan değişkeni ekrana yazdırdı.

## Bazı Önemli Fonksiyonlar

```cpp
using System;

namespace matematik
{
    class Program
    {
        static void Main()
        {

			int a = 3, b = 4, c = 81, f = -21;
			float d = 5.56f, e = 2.718281f;

			Console.WriteLine("*** C# ***");

			Console.WriteLine(Math.Sqrt(c)); /* Sqrt() fonksiyonu parantez icindeki
	sayinin karekokunu alir */

			Console.WriteLine(Math.Pow(a, b)); /* Pow() fonksiyonu parantez icindeki
	ilk sayiyi taban, ikinci sayiyi da us kabul ederek tabanin ussunu hesaplar */

			Console.WriteLine(Math.Log(e)); /* Log() fonksiyonu parantez icindeki sayinin 
	logaritmasini hesaplar (tabani 'e'dir. yani dogal logaritma seklinde hesaplar)*/

			Console.WriteLine(Math.Round(d)); /* Round() fonksiyonu parantez icindeki sayiyi tam
	sayiya yuvarlar */

			Console.WriteLine(Math.Abs(f)); /* Abs() fonksiyonu parantez icindeki sayinin
	mutlak degerini alir */

		}
    }
}
```

Ekrana verilen çıktılar:

```cpp
*** C# ***
9
81
0,999999706504216
6
21
```

## İkinci Dereceden Bir Denklemin Köklerini Bulma

_ax2_ + _bx_ + _c_ = _0_ formatında ikinci dereceden bir denklemin köklerini bulmak için öncelikle Diskriminant Δ (delta) bulunur. Sonrasında ise aşağıdaki formüle göre kökler bulunur.

**Kök (x)=−b±√(b^2−4ac) / 2a**

**Diskriminant Δ (delta) : b^2−4ac**

```cpp
using System;

namespace matematik
{
    class Program
    {
        static void Main()
        {

            int a, b, c;

            Console.WriteLine("#### IKINCI DERECEDEN BILINMEYEN DENKLEMIN KOKLERINI BULMA ####");
            Console.WriteLine(" ");
            Console.WriteLine("ax^2 + bx + c");
            Console.WriteLine("yukaridaki formata gore degerleri giriniz (a, b, c): ");

            a = Convert.ToInt32(Console.ReadLine());
            b = Convert.ToInt32(Console.ReadLine());
            c = Convert.ToInt32(Console.ReadLine());

            double delta = Math.Pow(b, 2) - 4 * a * c;

            if (delta > 0)
            {
                double x1 = ((-b - Math.Sqrt(delta)) / (2 * a));
                double x2 = ((-b + Math.Sqrt(delta)) / (2 * a));

                Console.WriteLine("Denklemin İki Kökü Vardır: ");
                Console.WriteLine("x1 =" + x1);
                Console.WriteLine("x2 =" + x2);
            }

            else if (delta == 0)
            {
                double x = -b / (2 * a);
                Console.WriteLine("Denklemin Bir Kökü Vardır: ");
                Console.WriteLine("x =" + x);
            }

            else
            {
                Console.Write("Sanal Kök Vardır");
            }

        }
    }
}
```
