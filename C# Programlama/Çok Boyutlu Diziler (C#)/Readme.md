
Önceki yazılarımda tek boyutlu diziler ile işlem yapmıştık. Bu yazımda ise çok boyutlu dizilere giriş yapacağız.

## İki Boyutlu Diziler

İki boyutlu dizileri x, y koordinat düzlemi gibi veya tablo gibi düşünebilirsiniz. Bu yazımızda çok boyutlu dizileri tablo görünümünde ele alacağız.

İki boyutlu veya çok boyutlu dizilerin normal dizilerin yazımından neredeyse hiçbir farkı yoktur. Tek fark dizi parantezi içerisine boyut ayrımı yapmayı sağlayacak “**, (virgül)**” işaretinin olmasıdır:

```cpp
int[,] cokBoyutluDizi;
```

Yukarıdaki örneği tablo gibi düşünürsek, bu tablonun 3 satır ve 4 sütundan oluştuğunu ve 12 tane eleman olduğunu görebiliriz.

![](https://www.programiz.com/sites/tutorial2program/files/csharp-array-as-table.png)

Bu durumda çok boyutlu dizileri aşağıdaki gibi ele alabiliriz:

```cpp
int[,] cokBoyutluDizi = new int[satir, sutun];
```

## Üç Boyutlu Diziler

Üç boyutlu dizilerin mantığı iki boyutlu diziler gibidir.

```cpp
int[, ,] cokBoyutluDizi;
```

Yukarıdaki örnekte üç boyutlu dizinin nasıl tanımlanacağını gördük. Bu dizi içerisinde 60 tane eleman bulundurur. Her kümede ise 5 eleman bulunur. Bu durumu aşağıdaki gibi toparlayabiliriz:

```cpp
int[, ,] cokBoyutluDizi = new int[satir, sutun, eleman];
```

## İki Boyutlu Dizilere Örnek

```cpp
int[,] cokBoyutluDizi = { {1,2,3,4},{5,6,7,8},{9,10,11,12} };
```

Yukarıdaki kodlarda elemanların çok boyutlu diziye nasıl atandığını gördük. Yukarıdaki yazılış biçimini aşağıdaki gibi değiştirirsek daha anlaşılır olur:

```cpp
int[,] cokBoyutluDizi = { 

{1,2,3,4},
{5,6,7,8},
{9,10,11,12} 

};
```

Bildiğiniz gibi C++, C’ ve C# Programlamada kodlar arasındaki boşluklar önemsenmez. Bu şekilde yazıldığında anlaşılması daha kolay olur.

## Diziyi Tablo Şeklinde Yazdırma

Diziyi tablo şeklinde yazdırmak için iç içe döngüler kullanırız:

```cpp
using System;

namespace matematik
{
    class Program
    {
        static void Main()
        {

            int[,] cokBoyutluDizi = { { 1, 2, 3, 4 }, { 5, 6, 7, 8 }, { 9, 10, 11, 12 } };
            int i, j;


            for (i = 0; i < 3; i++)
            {

                for (j = 0; j < 4; j++)
                {

                    Console.WriteLine(cokBoyutluDizi[i, j]);

                }

            }

        }
    }
}
```

## Üç Boyutlu Dizilere Örnek

```cpp
int[, ,] cokBoyutluDizi = {
    {{3, 4, 2, 3}, {0, -3, 9, 11}, {23, 12, 23, 2}},
    {{13, 4, 56, 3}, {5, 9, 3, 5}, {3, 1, 4, 9}}};
```

Yukarıda iki boyutlu dizilerin yazım şekillerini görmüştük. Aynı şekilde yukarıdaki kodu aşağıdaki gibi yazarsak anlaşılması daha kolay olur:

```cpp
int[, ,] cokBoyutluDizi = {

    { {3, 4, 2, 3}, {0, -3, 9, 11}, {23, 12, 23, 2} },
    { {13, 4, 56, 3}, {5, 9, 3, 5}, {3, 1, 4, 9} }

}; 
```

Üç boyutlu dizileri anlatırken eleman sayısından bahsetmiştik. Bu dizide her kümede 4 eleman bulunur.
