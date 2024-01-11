
Structures (Bu kısımdan sonra **Yapılar** diye bahsedeceğim. ) tek bir veri tipi adı altında birden fazla benzer veya farklı veri tipindeki değişkeni kendi mimarisinde tutar.

Yapılar genelde veri saklamak için kullanılır. Örneğin veri tipinizin adı Sınıf olsun. Sınıfta öğrenci bilgilerini saklayacağımızı varsayalım. Bu öğrencilerin veri olarak adı, soyadı, numarası, not bilgileri gibi verileri bulunur. Bu bilgileri saklamak için Yapılar’ı kullanırız.

## Yapılar’ın Tanımlanması

Yapılar, işlem kolaylığı olması için genelde **main() (ana fonksiyon) ve diğer fonksiyonlardan yukarıda** tanımlanır.

Yapılar aşağıdaki gibi tanımlanır:

```cpp
struct sinif {
	
	string ad;
	string soyad;
	int okulNo;
	
};
```

Yapılar’ın tanımlanmasını aşağıdaki örnek ile kavramaya çalışalım:

```cpp
#include <iostream>
#include <cstring>
#include <string>
using namespace std;

struct sinif {
	
	string ad;
	string soyad;
	int okulNo;
	
};

int main() {
	
	sinif ogrenci;
	
	ogrenci.ad = "C ve C++";
	ogrenci.soyad = "Ogrencisi";
	ogrenci.okulNo = 546352;
	
	cout << "ad: " << ogrenci.ad << endl;
	cout << "soyad: " << ogrenci.soyad << endl;
	cout << "okul numarasi: " << ogrenci.okulNo << endl;
	
	return 0;
}
```

Bu örneğimizde main() fonksiyonunun üzerinde **sinif** Yapısı’nı oluşturduk ve içerisine saklayacağımız veri tiplerini yerleştirdik. main() fonksiyonu içerisinde ise verilerini saklayacağımız bir değişken tanımladık (**Yapılar kendi başına bir veri tipi olduğu için veri tipinin adı ile değişken tanımlıyoruz**). Oluşturduğumuz değişkenin, sinif içerisine koyduğumuz veri tiplerine ulaşabilmesi için **. (nokta)** kullanıyoruz (**ogrenci.ad** gibi). Ulaşabildiği bu veri tiplerine uygun şekilde istenilen atamalar yapılabilir. Örneğin sonunda ise bu verileri ekrana çıktı olarak veriyoruz.

Ekrana verilen çıktı:

```cpp
ad: C ve C++
soyad: Ogrencisi
okul numarasi: 546352

```

Yapılar ve Fonksiyonlar

Yapılar ve fonksiyonlar arasındaki ilişkinin, normal bir veri tipi ile fonksiyonlar arasındaki ilişkiden çok da bir farkı yoktur.

Bir örnek ile konuyu kavramaya çalışalım:

```cpp
#include <iostream>
#include <cstring>
#include <string>
using namespace std;

struct sinif { 
	
	string ad;
	string soyad;
	int okulNo;
	
};

void yazdir(sinif ogrenci);

void yazdir(sinif ogrenci) {
	
	cout << "ad: " << ogrenci.ad << endl; 
	cout << "soyad: " << ogrenci.soyad << endl;
	cout << "okul numarasi: " << ogrenci.okulNo << endl;
	
}

int main() {
	
	sinif ogrenci;
	
	ogrenci.ad = "C ve C++";
	ogrenci.soyad = "Ogrencisi";
	ogrenci.okulNo = 546352;
	
	yazdir(ogrenci);
	
	return 0;
}
```

Fonksiyonları kullanırken main() fonksiyonunda tanımladığımız fonksiyona bir değer veya değişken göndeririz. Fonksiyon içerisinde ise bu değerin veya değişkenin tekrardan tanımlanıp isteğe bağlı olarak adı değiştirilir. Bu tanımlama işleminde **sinif** değişkeni bir **veri tipi** olarak kabul edilir ve fonksiyonun içerisinde “**sinif ogrenci**” olarak tanımlanır. Örneğin sonunda ise **yazdir()** fonksiyonu ekrana çıktılar verir.

Ekrana verilen çıktı:

```cpp
ad: C ve C++
soyad: Ogrencisi
okul numarasi: 546352
```

## Yapılar ve Pointers (İşaretçiler)

Fonksiyonlar ile Yapılar arasındaki ilişkiden bahsettiğimiz gibi bu konuda da ilişkiler arasında pek bir fark yoktur. Sadece tanımlama yaparken sinif veri tipini kullanacağız.

Konuyu örnek ile anlamaya çalışalım:

```cpp
#include <iostream>
#include <cstring>
#include <string>
using namespace std;

struct sinif { 
	
	string ad;
	string soyad;
	int okulNo;
	
};

void yazdir(sinif ogrenci);

void yazdir(sinif ogrenci) {
	
	sinif *ptr;
	
	ptr = &ogrenci;
	
	cout << "ad: " << (*ptr).ad << endl; 
	cout << "soyad: " << (*ptr).soyad << endl;
	cout << "okul numarasi: " << (*ptr).okulNo << endl;
	
}

int main() {
	
	sinif ogrenci;
	
	ogrenci.ad = "C ve C++";
	ogrenci.soyad = "Ogrencisi";
	ogrenci.okulNo = 546352;
	
	yazdir(ogrenci);
	
	return 0;
}
```

Pointer’ı (İşaretçiyi) **yazdir()** fonksiyonunda kullanacağımız için “**sinif *ptr**” şeklinde tanımladık. “**ogrenci**” değişkenin adresini ise “**ptr**” ye atadık. Çıktılarda ise işaretçiyi kullanmış olduk.

**Not: İşaretçiyi kullanırken parantez içerisinde kullanmak daha sağlıklıdır. Bunun nedeni ise .(nokta) ile “->” operatörü ile aynı işleve sahip olmasıdır. .(nokta) operatörünü kullanırken hata yapmanız daha olasıdır. Bu nedenle işaretçiyi parantez içerisine alırız.** (**ptr -> ad** ile **(*ptr).ad** aynı şeydir.)

## Yapılar ve Diziler

Diziler Yapılar’da tanımlanan değişkeni diziye dönüştürmeyi sağlar. Örneğin:

```cpp
#include <iostream>
#include <cstring>
#include <string>
using namespace std;

struct sinif { 
	
	string ad;
	string soyad;
	int okulNo;
	
};

void yazdir(sinif ogrenci[], int indeks);

void yazdir(sinif ogrenci[], int indeks) {
	
	sinif *ptr;
	
	ptr = &ogrenci[indeks];
	
	cout << "ad: " << (*ptr).ad << endl; 
	cout << "soyad: " << (*ptr).soyad << endl;
	cout << "okul numarasi: " << (*ptr).okulNo << endl;
	
}

int main() {
	
	sinif ogrenci[2];
	
	ogrenci[0].ad = "C ve C++";
	ogrenci[0].soyad = "Ogrencisi";
	ogrenci[0].okulNo = 546352;
	
	ogrenci[1].ad = "Muzaffer";
	ogrenci[1].soyad = "Enes";
	ogrenci[1].okulNo = 748952;
	
	yazdir(ogrenci, 0);
	cout << endl;
	yazdir(ogrenci, 1);
	
	return 0;
}
```

Bu örnekte dizi sayesinde “ogrenci” değişkenini diziye dönüştürdük ve belirli bir kapasite oluşturduk. Yani bu sınıfın öğrenci mevcudu 2 oldu. Örneğin sonunda da öğrencileri ekrana bastırdık.

Ekrana verilen çıktı:

```cpp
ad: C ve C++
soyad: Ogrencisi
okul numarasi: 546352

ad: Muzaffer
soyad: Enes
okul numarasi: 748952
```

## Öğrendiklerimiz ile Öğrenci Kayıt Sistemi Yapalım

Bu örnekte öğrenci mevcudu 30 olan bir sınıfın kayıt sistemini yaptık.

```cpp
#include <iostream>
#include <cstdlib>
#include <ctime>
#include <cstring>
#include <string>
using namespace std;

struct sinif { 

	/* sinif yapisini tanimladik ve icerisine 
	farkli veri tipleri tanimladik */
	
	int ID;
	char ad[30];
	char soyad[30];
	char telNo[15];
	
};

void kayitEkle(); // kayit ekleme fonksiyonunun tanimlanmasi
int anaMenu(); // ana menu fonksiyonunun tanimlanmasi
void kayitBul(); // kayit bulma fonksiyonunun tanimlanmasi

void kayitEkle(sinif ogrenci[], int id) {
	
	int sira = id % 100; /* gelen id ile sira olusturulur ve siraya gore kayit 
	islemleri yapilir */
	
	ogrenci[sira].ID = id;
	
	cout << "Kayit icin gerekli bilgileri giriniz" << endl;
	
	cout << endl;
	
	cout << "ad: ";
	cin.ignore();
	
	 /* Bazen istenmeyen arabelleği temizlememiz gerekir, 
	bu nedenle cin.ignore() fonksiyonunu kullaniriz. Bu fonksiyon
	C programlamada fflush() fonksiyonuna benzer */
	
	cin.getline(ogrenci[sira].ad, 30);
	cout << "soyad: ";
	cin.getline(ogrenci[sira].soyad, 30);
	cout << "telefon numarasi: ";
	cin.getline(ogrenci[sira].telNo, 15);
	
}

int anaMenu() {
	
	int secim = -1;
	
	cout << "#### ANA MENU ####" << endl;
	cout << "1- kayit ekle" << endl;
	cout << "2- kayit bul" << endl;
	cout << "3- cikis" << endl;
	
	while(!(secim < 4 && secim > 0)) {
		
		/* kullanicidan secim icin 1-3 arasinda tam sayi degeri alinir */
		
		cout << "yapmak istediginiz islemi giriniz (1, 2, 3): ";
		cin >> secim;
		
	}
	
	return secim;
	
}

void kayitBul(sinif ogrenci[], int sira) {
	
	/* gelen sira degiskenine gore ekrana ogrenci ile
	ilgili veriler yazdirilir */
	
	cout << "id: " << ogrenci[sira].ID << endl;
	cout << "ad: " << ogrenci[sira].ad << endl;
	cout << "soyad: " << ogrenci[sira].soyad << endl;
	cout << "telefon numarasi: " << ogrenci[sira].telNo << endl;
	
}

int main() {
	
	srand(time(0));
	sinif ogrenci[30];
	int op, id[30], sayac = 0, i, sira;
	
	for(i = 0; i < 30; i++) {
		
		/* 6 basamakli ogrenci id leri hazirlaniliyor */
		
		id[i] = rand() % (9999 - 1000 + 1) + 1000;
		id[i] = id[i] * 100 + i; 
		
	}
	
	op = anaMenu();
	
	while(op != 3) {
		
		if(op == 1) {
			
			/* op == 1 ise kayit ekle fonksiyonu calisir */
			
			cout << endl;
			
			kayitEkle(ogrenci, id[sayac]);
			sayac++;
			
			cout << endl;
			
			op = anaMenu();
			
		}
		
		else if(op == 2) {
			
			/* op == 2 ise kayit bul fonksiyonu calisir */
			
			cout << "ogrenci kayit sirasini giriniz (1 - 30): ";
			cin >> sira;
			
			sira--;
			
			cout << endl;
			
			kayitBul(ogrenci, sira);
			
			cout << endl;
			
			op = anaMenu();
			
		}
		
	}
	
	/* op == 3 ise programdan cikis saglanir calisir */
	
	cout << endl;
	cout << "cikis yapiliyor";
	
	return 0;
}
```

Ekrana verilen örnek çıktı:

```cpp
#### ANA MENU ####
1- kayit ekle
2- kayit bul
3- cikis
yapmak istediginiz islemi giriniz (1, 2, 3): 1

Kayit icin gerekli bilgileri giriniz

ad: C ve C++
soyad: Ogrencisi
telefon numarasi: 555555555

#### ANA MENU ####
1- kayit ekle
2- kayit bul
3- cikis
yapmak istediginiz islemi giriniz (1, 2, 3): 2
ogrenci kayit sirasini giriniz (1 - 30): 1

id: 179100
ad: C ve C++
soyad: Ogrencisi
telefon numarasi: 555555555

#### ANA MENU ####
1- kayit ekle
2- kayit bul
3- cikis
yapmak istediginiz islemi giriniz (1, 2, 3): 3

cikis yapiliyor
```
