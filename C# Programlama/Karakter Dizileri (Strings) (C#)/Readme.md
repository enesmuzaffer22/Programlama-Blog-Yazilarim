

## String Veri Tipi Tanımlama

String veri tipini tanımlamayı önceki yazılarımızda bahsetmiştik.

Tekrardan konuyu hatırlayalım:

```cpp
using System;

namespace karakterDizileri
{
    class Program
    {
        static void Main()
        {

            string stringOrnegi = "deneme";

            Console.WriteLine(stringOrnegi); // Ekrana "stringOrnegi" degiskeni yazilir.

        }
    }
}
```

## Karakter Dizilerini Birleştirme

Karakter dizilerini birleştirmek için string degişkenlerini **birbirleri ile toplarız**:

```cpp
using System;

namespace karakterDizileri
{
    class Program
    {
        static void Main()
        {

			string str1 = "hello";
			string str2 = "world";

			string str3 = str1 + str2;
			string str4 = str1 + " " + str2;

			Console.WriteLine("str3: " + str3);

			Console.WriteLine("str4: " + str4);

		}
    }
}
```

Ekrana verilen çıktı:

```cpp
helloworld

hello world
```

Karakter dizilerini birleştirmenin bir diğer yolu ise “**string.Concat()**” fonksiyonudur:

```cpp
using System;

namespace karakterDizileri
{
    class Program
    {
        static void Main()
        {

			string str1 = "hello ";
			string str2 = "world";

			string str3 = string.Concat(str1, str2); //str1 degiskenine str2 degiskenini ekledik

			Console.WriteLine(str3);

		}
    }
}
```

Ekrana verilen çıktı:

```cpp
hello world
```

## Karakter Dizisinin Uzunluğu

Karakter dizisinin uzunluğunu öğrenmek için “**Length**” fonksiyonunu kullanırız:

```cpp
using System;

namespace karakterDizileri
{
    class Program
    {
        static void Main()
        {

            string str1 = "deneme";

            Console.WriteLine("str1 karakter dizisinin uzunlugu: " + str1.Length);

        }
    }
}
```

Ekrana verilen çıktı:

```cpp
str1 karakter dizisinin uzunlugu: 6
```

Not: **Önceki C Programlama yazılarımızda string veri tipi oluşturabilmek için dizilerden yararlanmıştık ve dizilerle işlem yapmıştık. Aynı işlemleri C# Programlamada da yapabilirsiniz.**

## Kullanıcıdan Karakter Dizisi Alma

Kullanıcıdan karakter dizisi almak için “ReadLine()” fonksiyonu kullanılır.

```cpp
using System;

namespace karakterDizileri
{
    class Program
    {
        static void Main()
        {

            string str1;

            Console.WriteLine("karakter dizisi giriniz: ");
            str1 = Console.ReadLine();

            Console.WriteLine(str1);

        }
    }
}
```

Ekrana verilen çıktı:

```cpp
karakter dizisi giriniz: hello world
hello world
```
