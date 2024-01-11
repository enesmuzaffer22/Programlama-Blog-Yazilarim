
Birçok mühendis kodlamaya output (çıkış) komutlarını yazarak başlar. Bugün sizlerle birlikte bu output örneklerinin en basitini, C++ programlama dilinde nasıl yazıldığını öğreneceğiz ve C++ programalama diline kısa bir giriş yapacağız.

```cpp
#include <iostream> //kutuphane tanimi 
using namespace std; //kodlarin basindaki "std::" kodunu atlamak icin yazilir 

int main() {   // ana fonksiyon
 
  cout << "Hello World!";   // output (cikis)
    
    return 0;   // program bittikten sonra programin bize dondurmesini istedigimiz deger 
 }
```

Yukarda yazılan kodlarda ilk olarak kullanıcağımız kütüphaneyi programa tanıttık. Sonrasında ise kodlarımızın büyük bir bölümünü yazıcağımız ana fonskiyonu açtık ve içerisine output (çıkış) yazdık.

Program çalıştığı zaman aşağıdaki gibi output verir ve bu output’ta “hello world” yazar. Hemen altında ise “return value 0” yazar. Bu bizim program sonunda programın düzgün çalışıp çalışmadığını anlamamız için döndürmesini istediğimiz değerdir.
