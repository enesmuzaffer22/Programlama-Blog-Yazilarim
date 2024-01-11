
switch, “else if” karar yapısının alternatifidir. Yani else if yerine switch de kullanılabilir.

Kullanım şekli aşağıdaki gibidir:

```cpp
switch(degiskenAdi) {

case degiskenSabiti:
.
.
islenecekKodlar;
.
.
break;

case degiskenSabiti:
.
.
islenecekKodlar;
.
.
break;

case degiskenSabiti:
.
.
islenecekKodlar;
.
.
break;

default: 
.
.
islenecekKodlar;
.
.

}
```

Konuyu aşağıdaki örnek ile anlamaya çalışalım:

```cpp
using System;

namespace InputOutput
{
    class Program
    {
        static void Main()
        {

            int s1, s2, islem, mod;
            float sonuc;

            Console.WriteLine("1- toplama");
            Console.WriteLine("2- cikarma");
            Console.WriteLine("3- carpma");
            Console.WriteLine("4- bolme");
            Console.WriteLine("5- mod alma");

            Console.WriteLine("yapmak istediginiz islemin numarasini giriniz: ");
            islem = Convert.ToInt32(Console.ReadLine());

            Console.WriteLine("iki sayi giriniz: ");
            s1 = Convert.ToInt32(Console.ReadLine());
            s2 = Convert.ToInt32(Console.ReadLine());

            switch (islem)
            {

                case 1:
                    sonuc = s1 + s2;
                    Console.WriteLine("sonuc: " + sonuc);
                    break;

                case 2:
                    sonuc = s1 - s2;
                    Console.WriteLine("sonuc: " + sonuc);
                    break;

                case 3:
                    sonuc = s1 * s2;
                    Console.WriteLine("sonuc: " + sonuc);
                    break;

                case 4:
                    sonuc = (float)s1 / s2;
                    Console.WriteLine("sonuc: " + sonuc);
                    break;

                case 5:
                    mod = s1 % s2;
                    Console.WriteLine("sonuc: " + mod);
                    break;

                default: Console.WriteLine("islem icin yanlis sayi girisi yaptiniz"); break;

            }

        }
    }
}

```

Yukarıdaki örnekte switch kullanarak 4 islem ve mod alma programı yazdık.
