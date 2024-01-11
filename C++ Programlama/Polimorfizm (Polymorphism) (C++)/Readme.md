
Polimorfizm nesne tabanlı programlama dilleri için önemli bir kavramdır. Programlamada polimorfizm kavramı, aynı isme sahip birden fazla yapının (**fonksiyon veya operator gibi**) farklı işlemler yapabilmesidir. C++ Programlama dilinde 4 farklı polimorfizm yolu vardır:

**1- Fonksiyon Aşırı Yüklemesi (Function Overloading)**

**2- Operatör Aşırı Yüklemesi (Operator Overloading)**

**3- Fonksiyon Geçersiz Kılma (Function Overriding)**

**4- Sanal Fonksiyonlar (Virtual Functions)**

## Fonksiyon Aşırı Yüklemesi (Function Overloading)

Fonksiyon aşırı yüklemesi, aynı isme sahip fonksiyonların **parametrelerinin sayısı veya farklı veri tipi** ile tanımlanıp kullanılmasıdır. Örneğin:

```cpp
#include <iostream>
using namespace std;

double toplama(double a, double b) {

    double sonuc;
    sonuc = a + b;
    return sonuc;

}

int toplama(int a, int b) {

    int sonuc;
    sonuc = a + b;
    return sonuc;

}

int main() {
    
    cout << "double sonuc: " << toplama(4.1, 2.2) << endl;
    cout << "integer sonuc: " << toplama(5, 6) << endl;

    return 0;
}
```

Bu örneğimizde “**toplama**” isminde iki adet farklı veri tipinde ve aynı parametre sayısına sahip fonksiyonlar tanımlanmıştır. “**main()**” fonksiyonunda yazıldığı gibi parametrelere göre uygun fonksiyonlar değer döndürür.

Ekrana verilen çıktı:

```cpp
double sonuc: 6.3
integer sonuc: 11
```

## Operatör Aşırı Yüklemesi (Operator Overloading)

Operatör aşırı yüklemesi, C++ Programlama dilinde kullanıcı tarafından tanımlanan yapılarda veya nesnelerde kullanılabilir. Bu işlemi kullanabilmek için “**operatör sembolleri**“nden yararlanırız. Örneğin:

```cpp
#include <iostream>
using namespace std;

class toplama {

private:
    int sayi;

public:
    toplama() {

        sayi = 20;

    }

    void operator ++() {

        sayi = sayi + 5;

    }

    int getsayi() { return sayi; }

};

int main() {
    
    toplama ornek;

    cout << "ornek: " << ornek.getsayi() << endl;

    ++ornek;

    cout << "ornek: " << ornek.getsayi() << endl;

    return 0;
}
```

Ekrana verilen çıktı:

```cpp
ornek: 20
ornek: 25
```



## Fonksiyon Geçersiz Kılma (Function Overriding)


C++ Programlama dilinde miras yolu ile miras alan sınıfta ve miras alınan sınıfta aynı fonksiyonları kullanabiliriz. Bu yol ile mirası alan bir sınıfın nesnesi ile fonksiyonu çağırdığımızda miras alınan sınıfın fonksiyonu yerine mirası alan sınıfın fonksiyonu çalışır. Bu nedenle fonksiyonu çağıran nesneye göre farklı fonksiyonlar çağırılır. Örneğin:

```cpp
#include <iostream>
using namespace std;

class anaSinif {

public:
    virtual void print() {

        cout << "Ana siniftaki fonksiyon cagirildi" << endl;

    }

};

class turetilmisSinif : public anaSinif {

public:
    void print() {

        cout << "Turetilmis siniftaki fonksiyon cagirildi" << endl;

    }

};

int main() {
    
    anaSinif nesne1;
    nesne1.print();

    turetilmisSinif nesne2;
    nesne2.print();

    return 0;
}
```

Ekrana verilen çıktı:

```cpp
Ana siniftaki fonksiyon cagirildi
Turetilmis siniftaki fonksiyon cagirildi
```

## Sanal Fonksiyonlar (Virtual Functions)

Sanal fonksiyonlar, fonksiyon geçersiz kılma işlemi ile neredeyse aynı çalışır. Bu konudaki önemli detay, ana sınıfı kullanarak **işaretçi (pointer)** bir nesne tanımlayıp bu nesne ile türetilmiş sınıftaki fonksiyonu kullanabilmemizdir. Örneğin:

```cpp
#include <iostream>
using namespace std;

class anaSinif {

public:
    virtual void print() {

        cout << "Ana siniftaki fonksiyon cagirildi" << endl;

    }

};

class turetilmisSinif : public anaSinif {

public:
    void print() {

        cout << "Turetilmis siniftaki fonksiyon cagirildi" << endl;

    }

};

int main() {
    
    anaSinif *nesne1;
    turetilmisSinif nesne2;

    nesne1 = &nesne2;

    nesne1->print();

    return 0;
}
```

Ekrana verilen çıktı:

```cpp
Turetilmis siniftaki fonksiyon cagirildi
```
