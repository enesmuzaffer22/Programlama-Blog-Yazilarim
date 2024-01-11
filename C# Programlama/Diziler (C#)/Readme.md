
Diziler birden çok değeri tek bir değişkende tutmak için kullanılır. Yani birden fazla değişkenle yapabileceğimiz işlemleri tek bir değişken ile yapabiliriz.

Dizilerin kullanım şekli aşağıdaki gibidir:

```cpp
int[] degiskenAdi = {1, 2, 3, 4, 5};
```

Yukarıdaki ifadede “degiskenAdi” değişkenine beş tane değer atadık.

## Peki bu değerlerin çıktısını nasıl alabiliriz ?

Bunun için dizinin “**indeks**” numarasından faydalanırız. İndeks numaraları “**0 (sıfır)**” dan başlar (yani 0, 1, 2.. şeklinde devam eder).

Bu durumu aşağıdaki kodlarla ifade edebiliriz:

```cpp
a[0] = 1; //sifirinci indeks 1'e esit
a[1] = 2; //birinci indeks 2'ye esit
a[2] = 3; //ikinci indeks 3'e esit
a[3] = 4; //ucuncu indeks 4'e esit
a[4] = 5; //dorduncu indeks 5'e esit
```

O halde bu kodlara benzer bir yazım ile aşağıdaki kodlar ile herhangi bir indeksteki sayının çıktısı alınabilir:

```cpp
using System;

namespace diziler
{
    class Program
    {
        static void Main()
        {

            int[] a = { 1, 2, 3, 4, 5 };

            Console.WriteLine("ikinci indeksteki sayi: " + a[2]);

        }
    }
}
```

Programın çıktısı aşağıdaki gibi olacaktır.

```cpp
ikinci indeksteki sayi: 3
```

## Döngüden Faydalanarak Çıktı Alma

```cpp
using System;

namespace diziler
{
    class Program
    {
        static void Main()
        {

            int[] a = { 1, 2, 3, 4, 5 };
            int i;

            for (i = 0; i < a.Length; i++)
            {

                /* bu for dongusu 0 dan baslayip dizinin buyuklugune
                kadar devam eder. Dizinin buyuklugunu ifade etmek icin
                "a.Length" ifadesini kullandik */

                Console.WriteLine(i + ". indeksteki sayi: " + a[i]);

            }

        }
    }
}
```

Yukarıda yazdığımız kodlar sayesinde bütün indeksteki sayıları ekrana yazdırdık.

Ekrana verilen çıktı ise aşağıdaki gibidir:

```cpp
0. indeksteki sayi: 1
1. indeksteki sayi: 2
2. indeksteki sayi: 3
3. indeksteki sayi: 4
4. indeksteki sayi: 5
```

## İndekse Değer Atama

İndekse değer atamak herhangi bir değişkene değer atamak ile aynıdır. Sadece yazılışları farklıdır. Örneğin:

```cpp
using System;

namespace diziler
{
    class Program
    {
        static void Main()
        {

            int[] a = new int[3];
            int i;

            /* Onceki orneklerimizde dizinin boyutunu belirtmeden islem
            yapmistik. Bu ornegimizde dizinin boyutunu 3 olarak belirledik
            ve kullanicidan dizi icin degerler aldik. Dizinin boyutunu belirlemek
            icin "new int[boyut]" kod parcasini kullaniriz. */

            Console.WriteLine("0. indeks icin bir sayi giriniz: ");
            a[0] = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("1. indeks icin bir sayi giriniz: ");
            a[1] = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("2. indeks icin bir sayi giriniz: ");
            a[2] = Convert.ToInt32(Console.ReadLine());

            for(i = 0; i < a.Length; i++)
            {

                Console.WriteLine(i + ". indeksteki a sayisi: " + a[i]);

            }

        }
    }
}
```

Ekrana verilen çıktı ise aşağıdaki gibidir:

```cpp
0. indeks icin sayi giriniz: 1

1. indeks icin sayi giriniz: 2

2. indeks icin sayi giriniz: 3

0. indeksteki sayi: 1

1. indeksteki sayi: 2

2. indeksteki sayi: 3
```

## Döngüden Faydalanarak Değer Atama

```cpp
using System;

namespace diziler
{
    class Program
    {
        static void Main()
        {

			int i; 
			int[] a = new int[5];

			for (i = 0; i < 5; i++)
			{

				Console.WriteLine(i + ". indeks icin deger giriniz: ");
				a[i] = Convert.ToInt32(Console.ReadLine());

			}

			for (i = 0; i < 5; i++)
			{

				Console.WriteLine(i + ". indeksteki deger: " + a[i]);

			}

		}
    }
}
```

Yukarıda yazdığımız kodlarda önce kullanıcıdan dizi için değerler alınır sonrasında ise bütün indeksteki sayılar ekrana yazılır.

Program aşağıdaki gibi çıktı verir:

```cpp
0. indeks icin sayi giriniz: 1

1. indeks icin sayi giriniz: 2

2. indeks icin sayi giriniz: 3

3. indeks icin sayi giriniz: 4

4. indeks icin sayi giriniz: 5

0. indeks: 1

1. indeks: 2

2. indeks: 3

3. indeks: 4

4. indeks: 5
```
