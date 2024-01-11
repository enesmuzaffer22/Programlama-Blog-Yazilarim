
Biz değerli yazılımcı arkadaşlar kodlarını yazarlarken sık sık hatalar yaparız ve bu hataları genelde kod yürütülürken fark ederiz. Bu hatalar bizim hatalı yazdığımız kodlardan, kullanıcının yaptığı yanlış girişlerden (**input**) ve buna benzer birçok sebepten kaynaklanan hatalardır. Genelde bu hatalar derleyici tarafından fark edildiğinde program durur ve derleyici tarafından bir hata mesajı oluşturulur. Bu hata mesajlarının teknik anlamdaki ismi “**istisna (exception)**“dır .

## try , catch ve throw Komutları

Konunun girişinde bahsettiğimiz gibi genelde aldığımız hataları derleyici tarafından öğreniriz. Bu noktada biz de kendi hata mesajlarımızı yani istisnaları **try, catch ve throw** komutları ile oluşturabiliriz ve bu istisnaları program yürütülmeye devam ederken ekrana çıktı olarak verebiliriz. Örneğin:

```cpp
#include <iostream>
using namespace std;

int main() {
	
	int sayi;
	
	cout << "Pozitif bir sayi giriniz: ";
	cin >> sayi;
	
	try{
		
		if(sayi < 0) {
			
			throw(sayi);
			
		}
		
		else {
			
			cout << "Girdiginiz sayi pozitif sayidir: " << sayi << endl;
			
		}
		
	}
	
	catch(int sayi) {
		
		cout << "Girdiginiz sayi pozitif bir sayi degil !" << endl;
		cout << "Girdiginiz sayi: " << sayi << endl;
		
	}
	
	return 0;
}
```

Bu örneğimizde basit bir istisna yapısı kurduk. İlk olarak kullanıcıdan pozitif bir sayı girmesini istedik. Eğer kullanıcı pozitif yerine negatif sayı girişi yaparsa “**throw**” komutu ile sayı “**catch**” bloğuna gönderilir. “**catch**” bloğunda hatanın yani istisnanın çıktısı ekrana verilir. Kullanıcı pozitif sayı girişi yaparsa sayı ekrana çıktı olarak verilir.

Ekrana verilen çıktı (**sayı pozitif ise**):

```cpp
Pozitif bir sayi giriniz: 14
Girdiginiz sayi pozitif sayidir: 14
```

Ekrana verilen çıktı (**sayı negatif ise**):

```cpp
Pozitif bir sayi giriniz: -23
Girdiginiz sayi pozitif bir sayi degil !
Girdiginiz sayi: -23
```

## Kendi Hata Kodunuzu Oluşturun

Yukarıdaki örneği biraz değiştirip konuya devam edelim:

```cpp
#include <iostream>
using namespace std;

int main() {
	
	int sayi;
	
	cout << "Pozitif bir sayi giriniz: ";
	cin >> sayi;
	
	try{
		
		if(sayi < 0) {
			
			throw 513; // istediginiz sayiyi hata kodu olarak kullanabilirsiniz.
			
		}
		
		else {
			
			cout << "Girdiginiz sayi pozitif sayidir: " << sayi << endl;
			
		}
		
	}
	
	catch(int hataKodu) {
		
		cout << "Girdiginiz sayi pozitif bir sayi degil !" << endl;
		cout << "Hata kodu: " << hataKodu << endl;
		
	}
	
	return 0;
}
```

Ekrana verilen çıktı (**sayı negatif ise**):

```cpp
Pozitif bir sayi giriniz: -1
Girdiginiz sayi pozitif bir sayi degil !
Hata kodu: 513
```

## Her Veri Türünden İstisnayı İşleme

Yazdığınız kodlar arasında “**catch**” bloğuna göndereceğiniz veri türü belli değil ise “**catch (…)**” kodu ile gelen istisnaları işleyebilirsiniz. Örneğin:

```cpp
#include <iostream>
using namespace std;

int main() {
	
	int sayi;
	
	cout << "Pozitif bir sayi giriniz: ";
	cin >> sayi;
	
	try{
		
		if(sayi < 0) {
			
			throw 513; // istediginiz sayiyi hata kodu olarak kullanabilirsiniz.
			
		}
		
		else {
			
			cout << "Girdiginiz sayi pozitif sayidir: " << sayi << endl;
			
		}
		
	}
	
	catch(...) {
		
		cout << "Girdiginiz sayi pozitif bir sayi degil !" << endl;
		
	}
	
	return 0;
}
```

Bu örneğimizde “**catch**” bloğuna gönderilen verinin türüne bakılmaksızın ekrana bloktaki istisna çıktı olarak verilir.

Ekrana verilen çıktı:

```cpp
Pozitif bir sayi giriniz: -56
Girdiginiz sayi pozitif bir sayi degil !
```

try, catch ve throw Komutlarını Fonksiyonlar ile Birlikte Kullanma

```cpp
#include <iostream>
using namespace std;

void paydaKontrol(int sayi1, int sayi2) {
	
	if(sayi2 == 0)
	throw sayi2;
	
	else
	cout << "Sonuc: " << (float)sayi1 / sayi2 << endl;
	
}

int main() {
	
	int sayi1, sayi2;
	
	cout << "@@@@ BOLME ISLEMI @@@@" << endl << endl;
	
	cout << "Pay giriniz: ";
	cin >> sayi1;
	cout << "Payda giriniz: ";
	cin >> sayi2;
	
	try {
		
		paydaKontrol(sayi1, sayi2);
		
	}
	
	catch(...) {
		
		cout << "Tanimsiz - Bolme isleminde payda sifir (0) olamaz !" << endl;
		
	}
	
	return 0;
}
```

Bu örneğimizde **try, catch ve throw** komutlarını “**paydaKontrol()**” fonksiyonu ile birlikte kullandık. Kullanıcıdan “**sayi1**” ve “**sayi2**” olarak iki tane sayı girişi istedik (**“sayi2” payda olacaktır.**). Sonrasında “**try**” bloğunda “**paydaKontrol()**” fonksiyonunu çağırdık. Bu fonksiyonun içerisinde payda “**sıfır (0)**” ise “**throw**” komutu ile “**sayi2**“yi “**catch**” bloğuna gönderdik ve istisnayı yani hata çıktısını ekrana verdik.

Ekrana verilen çıktı (**Payda (sayi2) sıfır (0) ise**):

```cpp
@@@@ BOLME ISLEMI @@@@

Pay giriniz: 5
Payda giriniz: 0
Tanimsiz - Bolme isleminde payda sifir (0) olamaz !
```

Ekrana verilen çıktı (**Payda (sayi2) sıfır (0) değil ise**):

```cpp
@@@@ BOLME ISLEMI @@@@

Pay giriniz: 5
Payda giriniz: 2
Sonuc: 2.5
```
