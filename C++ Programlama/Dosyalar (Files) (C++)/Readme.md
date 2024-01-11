
C++ Programlamada dosya okuma ve yazma işlemleri için “**fstream**” kütüphanesini tanımlamamız gerekir.

```cpp
#include <fstream>
```

“fstream” kütüphanesinde dosya oluşturmak, yazmak ve okumak için üç tane sınıf vardır:

–**ofstream**: Dosyaları oluşturmak ve yazmak için kullanılır.

–**ifstream**: Dosyaları okumak için kullanılır.

–**fstream**: ofstream ve ifstream sınıflarının kombinasyonudur. Okumak, yazmak vb. birçok işlem için kullanılır.

ofstream (Dosya Oluşturma ve Yazma)

ofstream sınıfı dosyaları oluşturmak ve yazmak için kullanılır. Örneğin:

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
	
	ofstream dosya("ornek.txt"); /* dosyayi olusturduk ve dosyanin adini "ornek" 
	koyduk. olusturdugumuz dosya ile islem yapmak icin akis nesnemizin adini "dosya" 
	koyduk. */
	
	dosya << "hello world"; /* bu satirda dosyanin icerisine "hello world" 
	yazdirdik. */
	
	dosya.close(); /* dosya ile isimiz bittigi icin dosyayi kapattik */
	
	return 0;
}
```

Kodlar arasında ” **dosya << “hello world”;** ” yazmamızın sebebi akış nesnemizin adının “**dosya**” olmasıdır. Normal şartlarda “**cout**” yazmamızın sebebi standart çıktının (**cout**) “**iostream**” kütüphanesinde **akış nesnesi** olmasıdır. Fakat bu örnekte konsolda işlem yapmıyoruz. İşlemleri dosya üzerinde yapıyoruz. Bu nedenle dosyadaki standart çıkış (cout), yeni tanımladığımız akış nesnesi olan “**dosya**“ya dönüşür.

Bu kodlar çalıştırıldığında konsolda herhangi bir çıktı göremeyeceksiniz. Çünkü “**hello world**” çıktısını dosyada verdik. Dosyayı açıp baktığınız zaman “**hello world**” yazdığını göreceksiniz (Dosya, proje dosyası ile aynı klasörde olacaktır.).

ifstream (Dosya Okuma)

ifstream sınıfı dosyaları okumak için kullanılır. Örneğin:

```cpp
#include <iostream>
#include <fstream>
#include <string>
#include <cstring>
using namespace std;

int main() {
	
	string satir; /* satirlari konsola cikti olarak vermek icin "satir" degiskenini
	tanimladik */
	
	// dosyayi acip okumak icin akis nesnesi olusturduk ve adini "dosya" koyduk.
	ifstream dosya;
	
	dosya.open("ornek.txt");
	
	while (getline(dosya, satir)) {
	
		/* dosyayi okuyup satirlari konsola cikti olarak vermek icin dongu kullandik */
	
		cout << satir << endl; // satiri konsola cikti olarak verdik
	
	}
	
	// isimiz bittigi icin dosyayi kapattik
	dosya.close();
	
	return 0;
}
```

Bu örnekte içerisinde

```cpp
hello world
Merhaba dunya
C Ogrencisi
```

yazan dosyayı okuyup içindekileri satır satır ekrana çıktı olarak verdik.

Ekrana verilen çıktı:

```cpp
hello world
Merhaba dunya
C Ogrencisi
```

fstream (Dosya Okuma ve Yazma)

fstream sınıfı birçok farklı işlemi birlikte yapmayı sağlar. Okumak, yazmak vb. birçok işlem için kullanılır. Örneğin:

```cpp
#include <iostream>
#include <fstream>
#include <cstring>
#include <string>
using namespace std;

int main() {
	
	string satir; /* ekrana cikti vermek icin kullanacagimiz degisken */
	
	fstream dosya; /* akis nesnesi tanimladik ve adini "dosya" koyduk.*/
	
	dosya.open("ornek.txt", ios::out | ios::in); /* dosya acildigi zaman hem okuma
	hem de yazma islemlerinin yapilmasini saglar. ayrica amaciniza gore eklemek
	istediginiz farkli bir islemi "|" ayiraci ayirip ekleyebilirsiniz. 
	
	ornegin:
	
	dosya.open("ornek.txt", ios::out | ios::in | ios::trunc);
	
	*/
	
	if(dosya) {
		
		/* ornegimiz icin "ornek.txt" dosyamizin icine "Hello world !" ve 
		"C Ogrencisi" yazdirdik. */
		
		dosya << "Hello world !" << endl;
		dosya << "C Ogrencisi" << endl;
		
	}
	
	/* bu kisim yazma islemlerini icerir. */
	
	/***************************************************/
	
	/* bu kisim okuma islemlerini icerir. */
	
	dosya.seekg(0, ios::beg); /* okuma isaretcisinin dosyanin basini isaret etmesini
	sagladik. boylece dosyayi okumaya satir sonundan degil satir basindan basladik. */
	
	while(dosya) {
		
		/* dosya acik oldugu surece bu dongu devam eder. */
		
		while(getline(dosya, satir)) {
			
			/* getline fonksiyonu ile satir almayana kadar satir alma islemlerine
			devam eder. */
			
			cout << satir << endl; /* satirlari konsola cikti olarak verir. */
			
		}
		
		dosya.close(); /* dongunun bitmesi icin dosyayi kapatir. */
		
	}
		
	return 0;
}
```

Bu örnekte aynı akış nesnesi ile hem okuma hem de yazma işlemleri yaptık. Bu örnekte dikkat edilmesi gereken bir şey vardır. **Dosyayı, projenin kendisi oluşturamaz. Proje dosyası ile aynı klasörde el ile kendiniz açmalısınız.**

Ekrana verilen çıktı:

```cpp
Hello world !
C Ogrencisi
```
