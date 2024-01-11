
C++ Programlama dili nesne yönelimli bir programlama dilidir. C++ Programlama dilindeki her şey sınıflar ve sınıfların nesneleri ile ilişkilidir. Buna göre sınıflar, nesneleri oluşturmak için kullanıcı tarafından oluşturulan bir yapıdır (Nesneleri bir varlık gibi düşünebilirsiniz. Her varlığın kendine ait özellikleri vardır ve biz bu özellikleri sınıf yapısının içinde tanımlarız. Örneğin bir arabanın rengi, markası, modeli o arabanın özellikleridir. Arabanın kendisi ise bir nesnedir.).

## Sınıfların Tanımlanması ve Nesne Oluşturma

**Sınıf Tanımlama**

Kodlarımız arasında sınıf oluşturmak için kullanacağımız anahtar kelimemiz “**class**” kelimesidir. Örneğin:

```cpp
class araba {
	
	public:
		int yil;
		string marka;
		string model;
	
};
```

Bu örneğimizde sınıfımızın adı “araba” olsun. Sınıfları anlatırken bahsettiğimiz gibi arabamızın özelliklerini “**public**” belirticinin altında tanımladık (public ve private belirticilerinden konunun ilerisinde bahsedeceğiz.). Son olarak da sınıf yapımızı noktalı virgül ile sonlandırdık.

**Nesne Oluşturma**

Nesne oluşturmak için **önce sınıfımızın adını sonrasında ise nesnemizin adını** tanımlarız. Örneğin:

```cpp
#include <iostream>
#include <string>
#include <cstring>
using namespace std;

class araba {
	
	public:
		int yil;
		string marka;
		string model;
	
};

int main() {
	
	araba yeniAraba_1;
	
	yeniAraba_1.yil = 2014;
	yeniAraba_1.marka = "Mercedes Benz";
	yeniAraba_1.model = "C180";
	
	araba yeniAraba_2;
	
	yeniAraba_2.yil = 2015;
	yeniAraba_2.marka = "BMW";
	yeniAraba_2.model = "I8";
	
	cout << yeniAraba_1.yil << " " << yeniAraba_1.marka << " " << yeniAraba_1.model << endl;
	cout << yeniAraba_2.yil << " " << yeniAraba_2.marka << " " << yeniAraba_2.model << endl;
	
	return 0;
}
```

Bu örneğimizde iki adet araba nesnesi tanımladık ve nesnelerin özelliklerini ekrana yazdırdık.

Ekrana verilen çıktı:

```cpp
2014 Mercedes Benz C180
2015 BMW I8
```

## Sınıf Fonksiyonları

Sınıf fonksiyonları, sınıf yapıları içerisinde oluşturulan fonksiyonlardır. Bu fonksiyonları kullanırken nesneler ile birlikte kullanırız. Örneğin:

```cpp
#include <iostream>
using namespace std;

class sinifOrnegi {
	
	public:
		void ekranaYazdir() {
			
			cout << "Hello world" << endl;
			
		}
	
};

int main() {
	
	sinifOrnegi yeniNesne;
	
	yeniNesne.ekranaYazdir(); 
	
	return 0;
}
```

Bu örneğimizde yeni bir sınıf oluşturduk ve yeni bir nesne tanımladık. Bu nesne ile birlikte “**ekranaYazdir()**” fonksiyonunu çağırdık ve ekrana “**Hello world**” yazdırdık (Nesne ile fonksiyon arasındaki bağlantıyı “**. (nokta)**” işareti ile sağlarız.).

Az önceki örneğimizde fonksiyonu sınıf içerisinde tanımlayıp sınıf içerisinde yazmıştık. Bu yazıma alternatif olarak fonksiyon sınıf içerisinde tanımlanıp sınıf dışarısında yazılabilir. Örneğin:

```cpp
#include <iostream>

using namespace std;

class sinifOrnegi {
	
	public:
		void ekranaYazdir();

	
};

void sinifOrnegi::ekranaYazdir() {
	
	cout << "Hello world" << endl;
	
} 

int main() {
	
	sinifOrnegi yeniNesne;
	
	yeniNesne.ekranaYazdir(); 
	
	return 0;
}
```

Fonksiyon ile sınıf arasında bağlantı kurmak için “**:: (iki defa üst üste iki nokta) işareti**” kullanırız. Örnekte yukarıda olduğu gibi ekrana “**Hello world**” çıktısı verilir.

## Yapıcılar (Constructors)

Yapıcılar, bir sınıfın nesnesi oluşturulduğunda otomatik olarak çağrılan özel bir yöntemdir. Yapıcıları oluşturmak için **adı sınıf ile aynı olan fonksiyon benzeri bir yapı** kullanılır. Örneğin:

```cpp
#include <iostream>

using namespace std;

class sinifOrnegi {
	
	public:
		sinifOrnegi() {
			
			cout << "Hello world" << endl;
			
		}

	
};

int main() {
	
	sinifOrnegi yeniNesne;
	
	return 0;
}
```

Bu örneğimizde yeni bir sınıf ve bu sınıfın içerisinde **yapıcı (Constructors)** yapısını oluşturduk. Sonrasında bir nesne tanımladık. Bu nesne program içerisinde tanımlandığı anda yapıcı çalışır ve ekrana “**Hello world**” yazdırır.

Farklı bir örnek ile konuyu anlamaya çalışalım:

```cpp
#include <iostream>
#include <string>
#include <cstring>
using namespace std;

class araba {
	
	public:
		int yil;
		string marka;
		string model;
		
		araba(int x, string y, string z) {
			
			yil = x;
			marka = y;
			model = z;
			
		} 
	
};

int main() {
	
	araba yeniAraba_1(2014, "Mercedes Benz", "C180");
	
	araba yeniAraba_2(2015, "BMW", "I8");
	
	cout << yeniAraba_1.yil << " " << yeniAraba_1.marka << " " << yeniAraba_1.model << endl;
	cout << yeniAraba_2.yil << " " << yeniAraba_2.marka << " " << yeniAraba_2.model << endl;
	
	return 0;
}
```

Bu örneğimizde “**araba**” isminde yeni bir sınıf oluşturduk. Sonrasında ise yapıcı oluşturduk ve içerisine sınıf için tanımlayacağımız nesnelerin özellikleri için geçici parametreler yerleştirdik ve bu parametreleri nesnenin özelliklerine atadık. Yeni bir nesne oluştururken yapıcı ile birlikte oluşturduk ve parametreler ile özelliklerin değerlerini atadık. Örneğimizin sonunda ise arabaların özelliklerini ekrana yazdırdık.

Ekrana verilen çıktı:

```cpp
2014 Mercedes Benz C180
2015 BMW I8
```

## Erişim Belirticileri (public ve private)

Erişim belirticileri bir sınıfın üyelerine nasıl erişim sağlanacağını tanımlar. Biz sınıf konusunda buraya kadar sınıf içerisinde sürekli “**public**” belirticisini kullandık. Bu nedenle nesnenin özelliklerine kolaylıkla erişim sağlayabiliyorduk.

Kodlar arasında bazı noktalarda nesnenin özelliklerinin erişilebilirliğinin kolay olmaması gerekir. Bu durumda “**private**” erişim belirticisini kullanırız. Bir örnek ile konuyu anlamaya çalışalım:

```cpp
#include <iostream>
#include <string>
#include <cstring>
using namespace std;

class okul {
	
	private:
		string tcKimlikNo;
		
	public:
		string ad;
		string soyAd;
	
};

int main() {
	
	okul ogrenci;
	
	ogrenci.ad = "C";
	ogrenci.soyAd = " Ogrencisi";
	ogrenci.tcKimlikNo = "12345678901"; 
	
	cout << ogrenci.ad << " " << ogrenci.soyAd << " " << ogrenci.tcKimlikNo << endl;
	
	return 0;
}
```

Bu örnekte “**okul**” adında bir sınıf oluşturduk ve içerisinde “**private**” belirticisinin altında “**tcKimlikNo**” isimli bir değişken tanımladık. “**public**” belirticisinin altında ise “**ad**” ve “**soyAd**” isimli iki tane değişken tanımladık. Sonrasında ise yeni bir nesne oluşturduk ve özelliklerini “**main()**” fonksiyonu içerisinde tanımladık. En sonunda ise bu özellikleri ekrana yazdırdık.

Şimdi buraya kadar her şey güzel fakat bir sorun var. Kodu çalıştırdığımızda bir hata alıyoruz. Aldığımız hata bize “**tcKimlikNo**” değişkenin “**private**” belirticisinin altında olduğunu ve bu değişkene dışarıdan erişim sağlanamadığından bahsediyor. Bu noktada “**private**” belirticisinin işlevini yukarıda bahsettiğimiz gibi anlamış oluyoruz.

## Kapsülleme (Encapsulation)

Bir önceki konu başlığında yani erişim belirticilerinde “**public**” ve “**private**” belirticilerinden bahsetmiştik. “**private**” belirticisinin nesnelerin özelliklerine erişim sağlama konusunda işleri kasıtlı olarak zorlaştırdığını öğrenmiştik. Bu konu başlığında özel bir yöntem ile “**private**” belirticisi altındaki değişkenlere nasıl erişebileceğimizi öğrenmiş olacağız.

Bu yöntemde adını bizim koyduğumuz fakat genel olarak “**get**” ve “**set**” olarak bilinen fonksiyonlar kullanacağız. Hemen bir örnek ile konuyu anlamaya çalışalım:

```cpp
#include <iostream>
#include <string>
#include <cstring>
using namespace std;

class okul {
	
	private:
		string tcKimlikNo;
		
	public:
		string ad;
		string soyAd;
		
	void set_tcKimlikNo(string tc_temp) { tcKimlikNo = tc_temp; }
	string get_tcKimlikNo() { return tcKimlikNo; }
		
};

int main() {
	
	okul ogrenci;
	
	ogrenci.ad = "C";
	ogrenci.soyAd = " Ogrencisi";
	ogrenci.set_tcKimlikNo("12345678901"); 
	
	cout << ogrenci.ad << ogrenci.soyAd << " " << ogrenci.get_tcKimlikNo() << endl;
	
	return 0;
}
```

Hatırlarsanız bir önceki konu başlığındaki örnekte “**tcKimlikNo**” değişkenine erişim sağlayamıyorduk. Bu örneğimizde “**public**” belirticisinin altında “**get**” ve “**set**” fonksiyonları ile değişkene değer atadık ve değişkeni ekrana yazdırdık.

## Miras Kavramı (Inheritance)

Miras kavramının (Inheritance) anlamı C++ Programlama dilinde bir sınıftan yeni bir sınıf türetmektir. Bu türetme işlemi “**: (üst üste iki nokta)**” işareti ile yapılır. Örneğin:

```cpp
#include <iostream>
#include <string>
#include <cstring>
using namespace std;

class insan {
	
	public:
		string ad;
	
};

class ogrenci: public insan {
	
	public:
		int ogrenciNo;
	
};

int main() {
	
	ogrenci yeniOgrenci;
	
	yeniOgrenci.ad = "METE";
	yeniOgrenci.ogrenciNo = 123456;
	
	cout << yeniOgrenci.ad << " " << yeniOgrenci.ogrenciNo;
	 
	return 0;
}
```

Bu örnekte “**ogrenci**” sınıfı “**insan**” sınfından aldığı miras ile türetildi. “**main()**” fonksiyonunda ise nesne tanımlanırken mirası alan sınıf ile tanımla yapılır. Nesnenin özelliklerini de tanımladıktan sonra nesnenin özellikleri ekrana yazdırdık.

Ekrana verilen çıktı:

```cpp
METE 123456
```

## Çok Seviyeli Miras (Multilevel Inheritance)

Çok seviyeli miras kavramı bir sınıfın mirasını alan sınıfın mirasını almasıdır. Bir örnek ile konuyu anlamaya çalışalım:

```cpp
#include <iostream>
#include <string>
#include <cstring>
using namespace std;

class anaSinif {
	
	public:
		void printFonk() {
			
			cout << "Hello world" << endl;
			
		}
	
};

class mirasSinif_1: public anaSinif {};
class mirasSinif_2: public mirasSinif_1 {};

int main() {
	
	mirasSinif_2 yeniNesne;
	
	yeniNesne.printFonk(); 
	 
	return 0;
}
```

Bu örnekte mirası alan sınıfın mirasını alan sınıf “**mirasSinif_2**” sınıfıdır. Bir nesne tanımlanırken bu sınıfın adı ile tanımlanır. Bu örnekte “**yeniNesne**” adında bir nesne oluşturduk ve bu nesnenin aracılığı ile “**printFonk()**” fonksiyonunu çağırdık.

Ekrana verilen çıktı:

```cpp
Hello world
```

## Çoklu Miras (Multiple Inheritance)

Çoklu miras kavramı bir sınıfın birden çok ana sınıftan miras almasıdır. Örneğin:

```cpp
#include <iostream>
#include <string>
#include <cstring>
using namespace std;

class anaSinif_1 {
	
	public:
		void printFonk_1() {
			
			cout << "Hello world" << endl;
			
		}
	
};

class anaSinif_2 {
	
	public:
		void printFonk_2() {
			
			cout << "Merhaba dunya" << endl;
			
		}
	
};

class mirasSinif: public anaSinif_1, public anaSinif_2 {};


int main() {
	
	mirasSinif yeniNesne;
	
	yeniNesne.printFonk_1();
	yeniNesne.printFonk_2(); 
	 
	return 0;
}
```

Bu örnekte “**mirasSınıf**” sınıfı “**anaSinif_1**” ve “**anaSinif_2**” sınıflarının mirasını aldı. Sonrasında ise mirası alan sınıfın adı ile yeni bir nesne tanımladık ve bu nesne aracılığı ile “**printFonk_1()**” ve “**printFonk_2()**” fonksiyonlarını çağırdık.

Ekrana verilen çıktı:

```cpp
Hello world
Merhaba dunya
```

## Erişim Belirticisi (protected)

Bu konu başlığında yeni bir erişim belirticisi olan “**protected**” belirticisinden bahsedeceğiz. Bu belirtici “**private**” belirticisi ile neredeyse aynı işleve sahiptir. “**private**” belirticisinden tek farkı “**protected**” belirticisi miras sınıflarında kullanılır. Örneğin:

```cpp
#include <iostream>
#include <string>
#include <cstring>
using namespace std;

class insan {
	
	protected:
		string tcKimlikNo;
		string ad;
		string soyAd;
		int ogrenciNo;
	
};

class ogrenci: public insan {
	
	public:
		void setOgrenci(string x, string y, string z, int a) {
			
			tcKimlikNo = x;
			ad = y;
			soyAd = z;
			ogrenciNo = a;
			
		}
		
		void printOgrenci() {
			
			cout << "TC KIMLIK NO: " << tcKimlikNo << endl;
			cout << "AD: " << ad << endl;
			cout << "SOYAD: " << soyAd << endl;
			cout << "OGRENCI NO: " << ogrenciNo << endl;
			
		}
	
};

int main() {
	
	ogrenci yeniKayit;
	
	yeniKayit.setOgrenci("12345678901", "C", "Ogrencisi", 123456);
	yeniKayit.printOgrenci();
	 
	return 0;
}
```

Bu örnekte “**protected**” belirticisi ile “**insan**” sınıfı altında bazı değişkenler tanımladık. Sonrasında ise “**ogrenci**” sınıfı ile “insan” sınıfının mirasını aldık ve içerisine “**set**” ve “**print**” fonksiyonları yerleştirdik. Son olarak “**main()**” fonksiyonu içerisinde yeni bir nesne oluşturduk ve bu nesne aracılığı ile “**set**” ve “**print**” fonksiyonlarını kullandık.

Ekrana verilen çıktı:

```cpp
TC KIMLIK NO: 12345678901
AD: C
SOYAD: Ogrencisi
OGRENCI NO: 123456
```

## Alternatif Parametre Yöntemi

Bu konu başlığı sınıflar için **ekstra** bir başlıktır. Bu konu başlığında sınıflar içerisinde yazdığımız fonksiyonlardaki parametrelerin alternatiflerinden bahsedeceğiz.

Normal şartlarda “**set**” fonksiyonları ve benzer fonksiyonlarda geçici bir değişken kullanarak nesne özelliklerine atamalar yapıyorduk. Bu konu başlığında öğreneceğimiz yöntem ile geçici bir değişken kullanmadan bu işlemi nasıl yapacağımızı öğreneceğiz.

Parametrelerde geçici değişken kullanmak yerine nesnenin özelliklerini belirten değişkenleri kullanacağız ve bu işlemleri “**this ->**” kod parçacığı ile yapacağız. Bir örnek ile konuyu anlamaya çalışalım:

```cpp
#include <iostream>
#include <string>
#include <cstring>
using namespace std;

class okul {
	
	private:
		int okulNo;
		string ad;
		string soyAd;
		
	public:
		setOgrenci(int okulNo, string ad, string soyAd) {
			
			this -> okulNo = okulNo;
			this -> ad = ad;
			this -> soyAd = soyAd;
			
		}
		
		printOgrenci() {
			
			cout << "AD: " << ad << endl;
			cout << "SOYAD: " << soyAd << endl;
			cout << "OKUL NO: " << okulNo << endl;
			
		}
	
};


int main() {
	
	okul yeniKayit;
	
	yeniKayit.setOgrenci(123456, "C", "Ogrencisi");
	yeniKayit.printOgrenci();
		 
	return 0;
}
```

Bu örnekte fonksiyon parametrelerinde geçici değişken kullanmak yerine nesnenin özelliklerini belirten değişkenleri kullandık.

Ekrana verilen çıktı:

```cpp
AD: C
SOYAD: Ogrencisi
OKUL NO: 123456
```
