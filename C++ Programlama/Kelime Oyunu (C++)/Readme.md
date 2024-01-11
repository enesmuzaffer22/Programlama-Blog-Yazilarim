
Yazdığım oyunun mantığı çok basit. Kullanıcıya iki seçenek sunuluyor (harf ile tahmin ve kelime ile tahmin). Kullanıcı istediği seçenek ile kelimeyi tahmin etmeye çalışıyor. Oyundaki kelime sayısı 10 tane ile kısıtlı ve rastgele kelimelerdir.

```cpp
#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
	
	char harf[24];
	srand((unsigned)time(0)); // rastgele sayilar olusması icin yazilan fonksion
	int rastgele_sayi, i, j, kontrol = 0, op = 0, sayac = 0, kontrol_2 = 1, sayac_2 = 0;
	string kelime_tahmini;
	
	for(i = 0; i < 24; i++) {
		
		harf[i] = '0'; // harf dizisinin her elemanina '0' ataniyor
		
	}
	
	string kelime[10] = {"araba", "uzun", "elma", "portakal", 
	"bilgisayar", "basketbol", "ilkbahar", "siyah", "turuncu", "demir"}; /* oyunda tahmin etmeye
	calisacagimiz kelimeler */
	
	cout << "********* KELIME OYUNU *********" << endl;
	cout << endl;
	
	rastgele_sayi = (rand() % (9 - 0 + 1)) + 0; /* 9 - 0 arasinda sayi uretiliyor 
	(9. indeks - 0. indeks)*/
	
	while(kelime_tahmini != kelime[rastgele_sayi] || sayac_2 == kelime[rastgele_sayi].length()) {
	
		for(i = 0; i < kelime[rastgele_sayi].length(); i++) {
			
			for(j = 0; j < sayac; j++) {
				
				if(harf[j] == (kelime[rastgele_sayi])[i]) {
					
					/* kullanicinin girdigi harfler kelimedeki harfler ile
					karsilastiriliyor */
					
					cout << harf[j] << " ";
					kontrol = 1;	
					
					sayac_2++;
					
					break;
					
				}
				
			}
			
			if(kontrol == 0) {
				
				/* uygun harf yoksa yerine '_' yaziliyor */
				
				cout << "_ ";
				
			}
			
			kontrol = 0;
			
		}
		
		cout << endl;
		cout << endl;
		
		while(op != 1 && op != 2) {
			
			/* secim menusu */
			
			cout << "1- harf ile tahmin etme" << endl;
			cout << "2- kelime ile tahmin etme" << endl;
			cout << "secim yapiniz (1, 2): ";
			cin >> op;
			
		}
		
		cout << endl;
		
		if(op == 1) {
			
			cout << "daha once girdiginiz harfler: ";
			
			for(j = 0; j < sayac; j++) {
				
				/* kullanicin daha once girdigi harfler listeleniyor */
				
				cout << harf[j] << " ";
				
			}
			
			cout << endl;
			cout << "harf giriniz: ";
			cin >> harf[sayac]; // harf girisi
			
			sayac++;
			
		}
		
		else {
			
			cout << "kelime giriniz (" << kelime[rastgele_sayi].length() << "):";
			cin >> kelime_tahmini; // kelime girisi
			
			if(kelime_tahmini == kelime[rastgele_sayi]) {
				
				/* kullanicinin girdigi kelime ile tahmin edilmeye calisilan kelime
				karsilastiriliyor */
				
				cout << "OYUNU KAZANDINIZ";
				
				break;
				
			}
			
		}
		
		op = 0;
			
	}
	
	return 0;
}
```

Örnek çıktı:

```cpp
********* KELIME OYUNU *********

_ _ _ _ _ _ _ _

1- harf ile tahmin etme
2- kelime ile tahmin etme
secim yapiniz (1, 2): 1

daha once girdiginiz harfler:
harf giriniz: a
_ _ _ _ a _ a _

1- harf ile tahmin etme
2- kelime ile tahmin etme
secim yapiniz (1, 2): 1

daha once girdiginiz harfler: a
harf giriniz: i
_ _ _ _ a _ a _

1- harf ile tahmin etme
2- kelime ile tahmin etme
secim yapiniz (1, 2): 1

daha once girdiginiz harfler: a i
harf giriniz: t
_ _ _ t a _ a _

1- harf ile tahmin etme
2- kelime ile tahmin etme
secim yapiniz (1, 2): 1

daha once girdiginiz harfler: a i t
harf giriniz: p
p _ _ t a _ a _

1- harf ile tahmin etme
2- kelime ile tahmin etme
secim yapiniz (1, 2): 1

daha once girdiginiz harfler: a i t p
harf giriniz: r
p _ r t a _ a _

1- harf ile tahmin etme
2- kelime ile tahmin etme
secim yapiniz (1, 2): 2

kelime giriniz (8):portakal
OYUNU KAZANDINIZ
```
