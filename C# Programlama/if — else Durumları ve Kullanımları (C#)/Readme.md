
# if

if kelimesinin Türkçe karşılığı “eğer” dir. if, bir koşula bağlı olarak işlenecek kodlar için kullanılır. Örneğin:

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int a = 5, b = 4;

            if (a > b)
            {

                Console.WriteLine("a b'den buyuktur");

            }

        }
    }
}

```

Yukarıdaki örneğimizde a, b olarak iki değişken tanımladık. Sonrasında ise bir koşul belirledik. Eğer a b’den büyükse “a b den buyuktur” yazdırır. Örnekte de görüldüğü üzere a b’den büyüktür ( 5 > 4 ). Bu durumda ekrana aşağıdaki çıktıyı vericektir.

```cpp
a b den buyuktur
```

Sonuç olarak if ifadesini aşağıdaki gibi özetleyebiliriz:

```cpp
if(kosulIfadesi) {..islenecekKodlar;..}
```

# if — else

if — else ifadesinin if ifadesinden tek farkı, koşul sağlanmaz ise koşulun sağlanmadığı durum için yazılan kodlar işlenir. else kelimesinin Türkçe karşılığı “aksi halde, başka”dır. Örneğin:

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int a = 5, b = 4;

            if (a < b)
            {

                Console.WriteLine("b a'dan buyuktur");

            }

            else
            {

                Console.WriteLine("a b'den buyuktur");

            }

        }
    }
}

```

Yukarıdaki örnekte if ifadesinin içindeki koşul sağlanmaz ve koşulun sağlanmadığı duruma yani “else” ifadesine geçilir. Programa ise aşağıdaki çıktı verilir:

```cpp
a b den buyuktur
```

Sonuç olarak else ifadesini aşağıdaki gibi özetleyebiliriz:

```cpp
if(kosulIfadesi) {
.
.
islenecekKodlar;
.
.
}

else {
.
.
islenecekKodlar;
.
.
}
```

# if — else if

if — else if birden fazla koşullu ifadeyi belirtmek için kullanılır. Örneğin:

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int a = 5, b = 4;

            if (a < b)
            {

                Console.WriteLine("b a'dan buyuktur");

            }

            else if (a == b)
            {

                Console.WriteLine("b a'ya esittir");

            }

            else if (a > b)
            {

                Console.WriteLine("a b'den buyuktur");

            }

        }
    }
}

```

Yukarıdaki örnekte birden fazla koşullu ifade kullandık. Doğru koşul sağlandığında ise aşağıdaki gibi bir çıktı verdi:

```cpp
a b den buyuktur
```

# Çok Önemli Not:

Birden fazla koşullu ifadeyi “else if” yerine “if” kullanarak yazarsanız, program koşulları doğru olan bütün kodları işler. Örneğin:

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int a = 5, b = 4;

            if (b < a)
            {

                Console.WriteLine("a b'den buyuktur (1. ifade)");

            }

            if (a == b)
            {

                Console.WriteLine("b a'ya esittir");

            }

            if (a > b)
            {

                Console.WriteLine("a b'den buyuktur (3. ifade)");

            }

        }
    }
}

```

Yukarıdaki örnek aşağıdaki gibi çıktı vericektir:

```cpp
a b den buyuktur 1. ifade

a b den buyuktur 3. ifade
```

Eğer yukarıdaki örneği aşağıdaki gibi yazarsanız, koşulu doğru olan kodları işlediğinde diğer koşulları önemsemiyecektir.

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int a = 5, b = 4;

            if (b == a)
            {

                Console.WriteLine("a b'ye esittir (1. ifade)");

            }

            else if (b < a)
            {

                Console.WriteLine("a b'den buyuktur (2. ifade)");

            }

            else if (a > b)
            {

                Console.WriteLine("a b'den buyuktur (3. ifade)");

            }

        }
    }
}

```

Programın çıktısı aşağıdaki gibi olucaktır:

```cpp
a b den buyuktur 2. ifade
```

# if İçinde if, else if, if — else

Koşul sağlandığı zaman ek olarak bir koşul daha koymak için if içinde if, else if, if — else ifadeleri yazılır. Örneğin:

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int a = 5, b = 4;

            if (a > b)
            {

                Console.WriteLine("a b'den buyuktur");

                if ((a % 2) == 1)
                {

                    Console.WriteLine("a tek sayidir");

                }

                else
                {

                    Console.WriteLine("a cift sayidir");

                }

            }

            else
            {

                Console.WriteLine("b a'dan buyuktur");

                if ((a % 2) == 1)
                {

                    Console.WriteLine("b tek sayidir");

                }

                else
                {

                    Console.WriteLine("b cift sayidir");

                }

            }

        }
    }
}

```

Yukarıdaki örnekte büyük sayının tek mi çift mi olduğunu inceledik. İlk olarak a ve b’nin büyüklük kıyaslamasını yaptık. Sonrasında ise büyük olan sayının tek mi çift mi olduğunu inceledik.

Program aşağıdaki gibi çıktı verir:

```cpp
a b den buyuktura tek sayidir
```
