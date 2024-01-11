
C# Programlamada rastgele sayı üretmek için “**Random()**” fonksiyonunu kullanırız. Üretilecek sayının aralığını belirlemek için de “**Next(altSinir, ustSinir)**” fonksiyonu kullanılır. Örneğin:

```cpp
using System;

namespace donguler
{
    class Program
    {
        static void Main()
        {

            Random rd = new Random();

            int rastgeleSayi = rd.Next(100, 200);

            Console.WriteLine(rastgeleSayi);

        }
    }
}
```

Bu örneğimizde 100-200 arasında rastgele sayılar üretilir.

Ekrana verilen çıktı:

```cpp
167
```
