
Sitemizin ilk yazısı olan “Hello World !” yazısında ilk output örneğimizi görmüştük. Şimdi bu örneği bu yazımızda daha da pekiştirmiş olacağız.

# Output

Output programa çıktı veren fonksiyondur. Uyarı mesajları, bilgilendirmeler, programda karşımıza çıkan yazıların çoğu output’un eseridir.

İlk olarak basit bir örnek ile başlayalım.

```cpp
printf("hello world");
```

Bu örneğimizde ekrana “hello world” çıktısı vermiş olduk. Yani program başladığı zaman alttaki gibi çıktı vericektir.

```cpp
hello world
```

Örneğimizi biraz daha kompleks hale getirmeye başlayalım.

```cpp
#include <stdio.h>

int main() {

int a = 6; // a degiskenini tanimladik
printf("a sayisi: %d", a); // ekrana a harfini "a sayisi: 6" seklinde yazdirdik

return 0;
}
```

Yukarıdaki örnekte önce “a” değişkenini tanımladık ve hemen ardından ekrana “a sayisi: 6” yazdırdık. Bu çıktıyı daha iyi anlayabilmeniz için şöyle bir gösterim yapılabilir:

```cpp
printf("%d", a);
```

Yukarıda yazdığımız satırda tırnak içerisinde “%d” yazarak çıktı için değişkenin türünü belirttik. Hemen arkasından çıktıyı virgül ile ayırarak çıktıda gözükmesini istediğimiz değişkenin isminiz yazdık.

Daha da iyi anlayabilmeniz için aşağıdaki gibi bir gösterim yapılabilir:

```cpp
printf("%degiskenTuru", degiskenAdi);
```

Değişken türlerinin “%” işareti ile gösterimleri ise aşağıda verilmiş:

![](./Input (Giriş) ve Output (Çıkış) – GoLittleCoder_files/0_1iUeEaggPQRkhDDI.jpg)

Şimdi ise farklı bir örnek ile ilerleyelim.

```cpp
#include <stdio.h>

int main() {

int a = 10, b = 7; // a ve b degiskenini tanimladik

printf("a sayisi: %d", a); // ekrana a degiskenini yazdirdik
printf("b sayisi: %d", b); // ekrana b degiskenini yazdirdik
printf("a ve b degiskeninin toplami: %d", a + b); // a ve b degiskenlerinin toplamini ekrana yazdirdik

return 0;
}
```

Yukarıdaki örnekte iki tane değişken tanımlayıp toplamlarını ekrana yazdırdık. Bu işlemi yukarıdaki gibi yapabilirsiniz fakat bu pek iyi bir yazım şekli değildir. Bu örnekten farklı olarak aşağıdaki gibi yazılabilir:

```cpp
#include <stdio.h>

int main() {

int a = 10, b = 7; // a ve b degiskenini tanimladik
int c;

c = a + b;
printf("a ve b degiskeninin toplami: %d", c); // a ve b degiskenlerinin toplamini ekrana yazdirdik

return 0;
}
```

# Input (Girdi)

Input programa girdi alan fonksiyondur. Kullanıcan girilen verilerin alınmasının çoğu input’un eseridir.

Kullanıcıdan veri almak için “scanf” fonksiyonunu kullanırız.

Aşağıdaki örnekte konuyu daha net anlayabiliriz:

```cpp
#include <stdio.h>

int main() {

int yas; // yas degiskeninin turunu tanimladik

printf("yasinizi giriniz: "); // kullaniciya yasini girmesi icin cikti gonderdik
scanf("%d", &yas); // girdiyi almak icin bu fonksiyonu kullandik

printf("yasiniz: %d", yas); // kullanicinin yasini cikti olarak ekrana verdik

return 0;
}
```

Yukarıdaki örnekte scanf fonksiyonu için ilk olarak tırnak işareti açtık ve içine “%” işareti koyarak kullanıcıdan değerinin girilmesi istenen değişkenin türünü belirttik. Sonrasında ise tırnaklı kısmı virgül ile ayırarak “&” işareti ile birlikte değişkenin adını belirttik.

Daha basit olsun diye aşağıdaki gibi bir formül uygulanabilir:

```cpp
scanf("%degiskenTuru", &degiskenAdi);
```

# Konuyu bir örnek ile toparlayalım:

```cpp
#include <stdio.h>

int main() {

int a, b;

printf("a sayisina tam sayi deger giriniz: ");
scanf("%d", &a);
printf("b sayisina tam sayi deger giriniz: ");
scanf("%d", &b);

printf("a sayisi: %d  b sayisi: %d", a, b);   // bu satirda iki farkli degiskeni ayni ciktida ekrana yazdirdik. ilk yuzde isareti a degiskenini, bir sonraki yuzde isareti ise b harfini ekrana yazdirdi.

return 0;
}
```

Ekrana verilen çıktı:

```cpp
a sayisina tam sayi deger giriniz: 5

b sayisina tam sayi deger giriniz: 6

a sayisi: 5  b sayisi: 6
```
