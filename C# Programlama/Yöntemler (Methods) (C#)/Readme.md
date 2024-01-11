
Belirli bir görevi gerçekleştirmek için yazılan kod bloklarına **fonksiyon** denir. Fonksiyonları belirli bir görev için yazdığımız kodları tekrar tekrar yazmamak için kullanırız (**Normalde kurs müfredatlarında bu konu “Metotlar (Methods)” olarak geçer. Bu yazımızda metot yerine “fonksiyon” kelimesini kullanacağız.**) .

Örneğin uygulama içinde bir işlem menüsü yapmak istediniz ve bu menüyü farklı koşullara göre aktif hale getirmek istediniz. Bu durumda gereken koşulların her birine işlem menüsünü sürekli yazmanız gerekecekti. Bu durumdan sıyrılmak için fonksiyonları kullanıyoruz.

İşlevli bir kod parçacığını sürekli yazmak yerine bir kere yazıp gereken yerde kod ile çağırıyoruz.

## Kullanıcı Tarafından Tanımlanmış Fonksiyonlar

Bu tür fonksiyonlar kullanıcı tarafından ihtiyacı olduğu zaman tanımlanır. Fonksiyonların çalışma mantığı aşağıdaki gibidir:

![](https://cdn.programiz.com/sites/tutorial2program/files/function-c-programming.jpg)

Önce fonksiyon tanımlanır. Sonrasında ise fonksiyon kümesinin içine işlenecek kodlar yazılır. Bu konuda dikkat edilmesi gereken şey: fonksiyonlar C# Programlamada sürekli sınıf içerisinde bulunur. (**Yukarıdaki resimler önceki yazılarımdan alıntıdır ve C programlamaya aittir fakat C, C++ ve C# arasında bu konuda bir fark yoktur**.)

**Fonksiyonun Yazımı**

Fonksiyonlar aşağıdaki gibi yazılır:

```cpp
class Program
{
  static veriTipi degiskenAdi() 
  {
    .
    .
    .
  }
}
```

Örneğin:

```cpp
class Program
{
  static float daireninAlani(float yaricap) 
  {
    .
    .
    .
  }
}
```

**Fonksiyonun Çağırılması**

Fonksiyonlar aşağıdaki gibi çağırılır:

```cpp
fonksiyonAdi(degisken1, degisken2, ...);
```

Örneğin:

```cpp
alan(yaricap);
```

## Fonksiyon Kullanımı İçin Örnek

Dikkat etmişseniz konu anlatımı boyunca dairenin alanı üzerine bir örnek verdim. Konunun bu kısmında dairenin alanını fonksiyon yardımı ile bulacağız.

```cpp
using System;

namespace donguler
{
    class Program
    {
        static float daireAlan(float r)
        {

            float pi = 3.14F, alan;

            alan = pi * r * r;  // fonsiyonun yazimi

            return alan; // donecek olan deger

        }
        static void Main()
        {

            float s, sonuc;

            Console.WriteLine("yaricap degeri giriniz: ");
            s = Convert.ToInt32(Console.ReadLine());

            sonuc = daireAlan(s);  // fonksiyonun cagirilmasi

            Console.WriteLine("sonuc: " + sonuc);

        }
    }
}
```
