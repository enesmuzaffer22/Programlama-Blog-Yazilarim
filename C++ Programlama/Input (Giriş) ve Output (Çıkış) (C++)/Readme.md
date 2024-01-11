
Sitemizin ilk yazısı olan “Hello World !” yazısında ilk output örneğimizi görmüştük. Şimdi bu örneği bu yazımızda daha da pekiştirmiş olacağız.

# Output

Output programa çıktı veren fonksiyondur. Uyarı mesajları, bilgilendirmeler, programda karşımıza çıkan yazıların çoğu output’un eseridir.

İlk olarak basit bir örnek ile başlayalım.

```cpp
cout << "hello world";
```

Bu örneğimizde ekrana “hello world” çıktısı vermiş olduk. Yani program başladığı zaman alttaki gibi çıktı vericektir.

```cpp
hello world
```

Örneğimizi biraz daha kompleks hale getirmeye başlayalım.

```cpp
#include <iostream>
using namespace std;

int main() {

int a = 6; // a degiskenini tanimladik
cout << "a sayisi: " << a; // ekrana a harfini "a sayisi: 6" seklinde yazdirdik

return 0;
}
```

Daha da iyi anlayabilmeniz için aşağıdaki gibi bir gösterim yapılabilir:

```cpp
cout << degiskenAdi;
```

Şimdi ise farklı bir örnek ile ilerleyelim.

```cpp
#include <iostream>
using namespace std;

int main() {

int a = 10, b = 7; // a ve b degiskenini tanimladik

cout << "a sayisi: " << a; // ekrana a degiskenini yazdirdik
cout << "b sayisi: " << a; // ekrana b degiskenini yazdirdik
cout << "a ve b degiskeninin toplami: " << a + b; // a ve b degiskenlerinin toplamini ekrana yazdirdik

return 0;
}
```

Yukarıdaki örnekte iki tane değişken tanımlayıp toplamlarını ekrana yazdırdık. Bu işlemi yukarıdaki gibi yapabilirsiniz fakat bu pek iyi bir yazım şekli değildir. Bu örnekten farklı olarak aşağıdaki gibi yazılabilir:

```cpp
#include <iostream>
using namespace std;

int main() {

int a = 10, b = 7; // a ve b degiskenini tanimladik
int c;

c = a + b;
cout << "a ve b degiskeninin toplami: " << c; // a ve b degiskenlerinin toplamini ekrana yazdirdik

return 0;
}
```

# Input (Girdi)

Input programa girdi alan fonksiyondur. Kullanıcan girilen verilerin alınmasının çoğu input’un eseridir.

Kullanıcıdan veri almak için “cin >>” fonksiyonunu kullanırız.

Aşağıdaki örnekte konuyu daha net anlayabiliriz:

```cpp
#include <iostream>

int main() {

int yas; // yas degiskeninin turunu tanimladik

cout << "yasinizi giriniz: "; // kullaniciya yasini girmesi icin cikti gonderdik
cin >> yas; // girdiyi almak icin bu fonksiyonu kullandik

cout << "yasiniz: " << yas; // kullanicinin yasini cikti olarak ekrana verdik

return 0;
}
```

Daha basit olsun diye aşağıdaki gibi bir formül uygulanabilir:

```cpp
cin >> degiskenAdi;
```

# Konuyu bir örnek ile toparlayalım:

```cpp
#include <stdio.h>

int main() {

int a, b;

cout << "a sayisina tam sayi deger giriniz: ";
cin >> a;
cout << "b sayisina tam sayi deger giriniz: ";
cin >> b;

cout << "a sayisi: " << a << "b sayisi: " << b;   // bu satirda iki farkli degiskeni ayni ciktida ekrana yazdirdik. ilk yuzde isareti a degiskenini, bir sonraki yuzde isareti ise b harfini ekrana yazdirdi.

return 0;
}
```

Ekrana verilen çıktı:

```cpp
a sayisina tam sayi deger giriniz: 5

b sayisina tam sayi deger giriniz: 6

a sayisi: 5  b sayisi: 6
```
