
Birçok mühendis kodlamaya output (çıkış) komutlarını yazarak başlar. Bugün sizlerle birlikte bu output örneklerinin en basitini, C# programlama dilinde nasıl yazıldığını öğreneceğiz ve C# programlama diline kısa bir giriş yapacağız.

```cpp
using System; // ad alanini tanimlama (c++ ve c'deki kutuphaneye
              // benzer)

namespace ProgramAdi // kapsayici tanimlama
{
    class SinifAdi // sinif tanimlama
    {
        static void Main() // ana fonksiyonu tanimlama
        {

            /* ana fonksiyon, c++ ve c'deki main() fonksiyonu ile
            ayni seydir */

            Console.WriteLine("Hello world!"); /* ekrana "Hello World!"
            yazdirir */

        }
    }
}

```

Yukarda yazılan kodlarda ilk olarak kullanacağımız “**ad alanını** (**namespace**)” programa tanıttık. Sonrasında ise **kapsayıcı (namespace)**ve **sınıf (class)** tanımladık. Son adımda ise kodlarımızın büyük bir bölümünü yazacağımız ana fonksiyonu açtık ve içerisine output (çıkış) yazdık.

Program çalıştığı zaman output verir ve bu output’ta “hello world” yazar.
