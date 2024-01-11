

## Tek Boyutlu Dizilerde Karşılaştırma ve Sıralama

Dizideki En Büyük Elemanı Bulma:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int a[5] = {3, 32, 2, 45, 14};
	int ref_deger, i;
	
	ref_deger = a[0]; /* dizide elemanlarin karsilastirilmasi icin herhangi bir
	referans deger 'ref_deger' degiskenine atanir */
	
	for(i = 0; i < 5; i++) {
		
		if(ref_deger < a[i]) {
			
			/* dizideki elemanlar referans degeri ile karsilastirilir */
			
			ref_deger = a[i]; /* dizide ref_deger den daha buyuk bir deger var ise 
			ref_deger atanir */ 
			
		}
		
	}
	
	cout << "en buyuk deger: " << ref_deger; /* ekrana ref_deger yani dizinin
	en buyuk degeri cikti olarak verilir (45) */
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a[5] = {3, 32, 2, 45, 14};
	int ref_deger, i;
	
	ref_deger = a[0]; /* dizide elemanlarin karsilastirilmasi icin herhangi bir
	referans deger 'ref_deger' degiskenine atanir */
	
	for(i = 0; i < 5; i++) {
		
		if(ref_deger < a[i]) {
			
			/* dizideki elemanlar referans degeri ile karsilastirilir */
			
			ref_deger = a[i]; /* dizide ref_deger den daha buyuk bir deger var ise 
			ref_deger atanir */ 
			
		}
		
	}
	
	printf("en buyuk deger: %d", ref_deger); /* ekrana ref_deger yani dizinin
	en buyuk degeri cikti olarak verilir (45) */
	
	return 0;
}
```

Dizideki En Küçük Elemanı Bulma:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int	a[5] = {3, 32, 2, 45, 14};
	int ref_deger, i;
	
	ref_deger = a[0]; /* dizide elemanlarin karsilastirilmasi icin herhangi bir
	referans deger 'ref_deger' degiskenine atanir */
	
	for(i = 0; i < 5; i++) {
		
		if(ref_deger > a[i]) {
			
			/* dizideki elemanlar referans degeri ile karsilastirilir */
			
			ref_deger = a[i]; /* dizide ref_deger den daha kucuk bir deger var ise 
			ref_deger e atanir */ 
			
		}
		
	}
	
	cout << "en buyuk deger: " << ref_deger; /* ekrana ref_deger yani dizinin
	en kucuk degeri cikti olarak verilir (2) */
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>

int main() {
	
	int	a[5] = {3, 32, 2, 45, 14};
	int ref_deger, i;
	
	ref_deger = a[0]; /* dizide elemanlarin karsilastirilmasi icin herhangi bir
	referans deger 'ref_deger' degiskenine atanir */
	
	for(i = 0; i < 5; i++) {
		
		if(ref_deger > a[i]) {
			
			/* dizideki elemanlar referans degeri ile karsilastirilir */
			
			ref_deger = a[i]; /* dizide ref_deger den daha kucuk bir deger var ise 
			ref_deger e atanir */ 
			
		}
		
	}
	
	printf("en buyuk deger: %d", ref_deger); /* ekrana ref_deger yani dizinin
	en kucuk degeri cikti olarak verilir (2) */
	
	return 0;
}
```

Dizideki Elemanları Küçükten Büyüğe Sıralama:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int a[6] = {3, 32, 2, 45, 14, 13};
	
	int boyut = 6; /* islemler daha iyi anlasilsin diye eleman sayisini 'boyut'
	degiskenine atadim */
	
	int j, i, temp; // temp: takas icin kullanacagimiz degisken
	
	for(i = 0; i < boyut - 1; i++) {
		
		for(j = 0; j < (boyut - 1) - i; j++) {
			
			if(a[j] > a[j + 1]) {
				
				/* dizideki j. eleman ile (j + 1). eleman karsilastiriliyor */
								
				temp = a[j];
				a[j] = a[j + 1]; 
				a[j + 1] = temp;
				
				/* eger j. eleman (j + 1). elemandan buyuk ise j. eleman ile
				(j + 1). elemanin degerleri birbirleri ile degistiriliyor */
				
			}
			
		}
		
	}
	
	cout << "kucukten buyuge siralama: ";
	for(i = 0; i < boyut; i++) {
		
		cout << a[i] << " "; // ekrana siralama cikti olarak veriliyor
		
	}
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a[6] = {3, 32, 2, 45, 14, 13};
	
	int boyut = 6; /* islemler daha iyi anlasilsin diye eleman sayisini 'boyut'
	degiskenine atadim */
	
	int j, i, temp; // temp: takas icin kullanacagimiz degisken
	
	for(i = 0; i < boyut - 1; i++) {
		
		for(j = 0; j < (boyut - 1) - i; j++) {
			
			if(a[j] > a[j + 1]) {
				
				/* dizideki j. eleman ile (j + 1). eleman karsilastiriliyor */
								
				temp = a[j];
				a[j] = a[j + 1]; 
				a[j + 1] = temp;
				
				/* eger j. eleman (j + 1). elemandan buyuk ise j. eleman ile
				(j + 1). elemanin degerleri birbirleri ile degistiriliyor */
				
			}
			
		}
		
	}
	
	printf("kucukten buyuge siralama: ");
	for(i = 0; i < boyut; i++) {
		
		printf("%d ", a[i]); // ekrana siralama cikti olarak veriliyor
		
	}
	
	return 0;
}
```

Dizideki Elemanları Büyükten Küçüğe Sıralama:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int	a[6] = {3, 32, 2, 45, 14, 13};
	
	int boyut = 6; /* islemler daha iyi anlasilsin diye eleman sayisini 'boyut'
	degiskenine atadim */
	
	int j, i, temp; // temp: takas icin kullanacagimiz degisken
	
	for(i = 0; i < boyut - 1; i++) {
		
		for(j = 0; j < (boyut - 1) - i; j++) {
			
			if(a[j] < a[j + 1]) {
				
				/* dizideki j. eleman ile (j + 1). eleman karsilastiriliyor */
								
				temp = a[j];
				a[j] = a[j + 1]; 
				a[j + 1] = temp;
				
				/* eger j. eleman (j + 1). elemandan kucuk ise j. eleman ile
				(j + 1). elemanin degerleri birbirleri ile degistiriliyor */
				
			}
			
		}
		
	}
	
	cout << "buyukten kucuge siralama: ";
	for(i = 0; i < boyut; i++) {
		
		cout << a[i] << " "; // ekrana siralama cikti olarak veriliyor
		
	}
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a[6] = {3, 32, 2, 45, 14, 13};
	
	int boyut = 6; /* islemler daha iyi anlasilsin diye eleman sayisini 'boyut'
	degiskenine atadim */
	
	int j, i, temp; // temp: takas icin kullanacagimiz degisken
	
	for(i = 0; i < boyut - 1; i++) {
		
		for(j = 0; j < (boyut - 1) - i; j++) {
			
			if(a[j] < a[j + 1]) {
				
				/* dizideki j. eleman ile (j + 1). eleman karsilastiriliyor */
								
				temp = a[j];
				a[j] = a[j + 1]; 
				a[j + 1] = temp;
				
				/* eger j. eleman (j + 1). elemandan kucuk ise j. eleman ile
				(j + 1). elemanin degerleri birbirleri ile degistiriliyor */
				
			}
			
		}
		
	}
	
	printf("buyukten kucuge siralama: ");
	for(i = 0; i < boyut; i++) {
		
		printf("%d ", a[i]); // ekrana siralama cikti olarak veriliyor
		
	}
	
	return 0;
}
```

## Çok Boyutlu Dizilerde Karşılaştırma ve Sıralama

Dizideki En Büyük Elemanı Bulma:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int a[3][2] = {3, 32, 2, 45, 14, 13};
	int satir = 3, sutun = 2; /* islemler daha iyi anlasilsin diye satir ve sutun 
	sayisini 'satir' ve 'sutun' degiskenlerine atadim */
	
	int i, j;
	int ref_deger = a[0][0]; /* dizide elemanlarin karsilastirilmasi icin herhangi bir
	referans deger 'ref_deger' degiskenine atanir */
	
	for(i = 0; i < satir; i++) {
		
		for(j = 0; j < sutun; j++) {
			
			if(ref_deger < a[i][j]) {
				
				/* dizideki elemanlar referans degeri ile karsilastirilir */
				
				ref_deger = a[i][j];
				
				/* dizide ref_deger den daha buyuk bir deger var ise 
			ref_deger atanir */ 
				
			}
			
		}
		
	}
	
	cout << "en buyuk deger: " << ref_deger; /* ref_deger yani en buyuk deger
	ekrana cikti olarak verilir */
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a[3][2] = {3, 32, 2, 45, 14, 13};
	int satir = 3, sutun = 2; /* islemler daha iyi anlasilsin diye satir ve sutun 
	sayisini 'satir' ve 'sutun' degiskenlerine atadim */
	
	int i, j;
	int ref_deger = a[0][0]; /* dizide elemanlarin karsilastirilmasi icin herhangi bir
	referans deger 'ref_deger' degiskenine atanir */
	
	for(i = 0; i < satir; i++) {
		
		for(j = 0; j < sutun; j++) {
			
			if(ref_deger < a[i][j]) {
				
				/* dizideki elemanlar referans degeri ile karsilastirilir */
				
				ref_deger = a[i][j];
				
				/* dizide ref_deger den daha buyuk bir deger var ise 
			ref_deger atanir */ 
				
			}
			
		}
		
	}
	
	printf("en buyuk deger: %d", ref_deger); /* ref_deger yani en buyuk deger
	ekrana cikti olarak verilir */
	
	return 0;
}
```

Dizideki En Küçük Elemanı Bulma:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int a[3][2] = {3, 32, 2, 45, 14, 13};
	int satir = 3, sutun = 2; /* islemler daha iyi anlasilsin diye satir ve sutun 
	sayisini 'satir' ve 'sutun' degiskenlerine atadim */
	
	int i, j;
	int ref_deger = a[0][0]; /* dizide elemanlarin karsilastirilmasi icin herhangi bir
	referans deger 'ref_deger' degiskenine atanir */
	
	for(i = 0; i < satir; i++) {
		
		for(j = 0; j < sutun; j++) {
			
			if(ref_deger < a[i][j]) {
				
				/* dizideki elemanlar referans degeri ile karsilastirilir */
				
				ref_deger = a[i][j];
				
				/* dizide ref_deger den daha kucuk bir deger var ise 
			ref_deger atanir */ 
				
			}
			
		}
		
	}
	
	cout << "en buyuk deger: " << ref_deger; /* ref_deger yani en kucuk deger
	ekrana cikti olarak verilir */
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a[3][2] = {3, 32, 2, 45, 14, 13};
	int satir = 3, sutun = 2; /* islemler daha iyi anlasilsin diye satir ve sutun 
	sayisini 'satir' ve 'sutun' degiskenlerine atadim */
	
	int i, j;
	int ref_deger = a[0][0]; /* dizide elemanlarin karsilastirilmasi icin herhangi bir
	referans deger 'ref_deger' degiskenine atanir */
	
	for(i = 0; i < satir; i++) {
		
		for(j = 0; j < sutun; j++) {
			
			if(ref_deger < a[i][j]) {
				
				/* dizideki elemanlar referans degeri ile karsilastirilir */
				
				ref_deger = a[i][j];
				
				/* dizide ref_deger den daha kucuk bir deger var ise 
			ref_deger atanir */ 
				
			}
			
		}
		
	}
	
	printf("en buyuk deger: %d", ref_deger); /* ref_deger yani en kucuk deger
	ekrana cikti olarak verilir */
	
	return 0;
}
```

Dizideki Elemanları Küçükten Büyüğe Sıralama:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {

	int a[3][2] = {3, 32, 2, 45, 14, 13};
	
	int i, j, temp = 0, boyut = 3 * 2; /* islemler daha iyi anlasilsin diye eleman sayisini 'boyut'
	degiskenine atadim */
	
	
	int satir = 3, sutun = 2, a1, a2, b1, b2; /* islemler daha iyi anlasilsin diye satir ve sutun 
	sayisini 'satir' ve 'sutun' degiskenlerine atadim */
	
	for(i = 0; i < boyut - 1; i++) {

		for(j = 0; j < boyut - 1 - i; j++)  {
	
			a1 = j / 10;
			a2 = (j + 1) / 10; //islemleri kolaylastirmak icin ek degiskenler kullandim
			b1 = j % 10;       
			b2 = (j + 1) % 10;
			
			if(a[a1][b1] > a[a2][b2]) {
				
				/* dizideki j. eleman ile (j + 1). eleman karsilastiriliyor */
				
				temp = a[a1][b1];
				a[a1][b1] = a[a2][b2];
				a[a2][b2] = temp;
				
				/* eger j. eleman (j + 1). elemandan buyuk ise j. eleman ile
				(j + 1). elemanin degerleri birbirleri ile degistiriliyor */
				
			}
			
		}
	
	}
	
	cout << "kucukten buyuge siralama: ";
	for(i = 0; i < satir; i++) {
		
		for(j = 0; j < sutun; j++) {
			
			cout << a[i][j] << " "; // ekrana siralama cikti olarak veriliyor
			
		}
		
	}
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>

int main() {

	int a[3][2] = {3, 32, 2, 45, 14, 13};
	
	int i, j, temp = 0, boyut = 3 * 2; /* islemler daha iyi anlasilsin diye eleman sayisini 'boyut'
	degiskenine atadim */
	
	
	int satir = 3, sutun = 2, a1, a2, b1, b2; /* islemler daha iyi anlasilsin diye satir ve sutun 
	sayisini 'satir' ve 'sutun' degiskenlerine atadim */
	
	for(i = 0; i < boyut - 1; i++) {

		for(j = 0; j < boyut - 1 - i; j++)  {
	
			a1 = j / 10;
			a2 = (j + 1) / 10; //islemleri kolaylastirmak icin ek degiskenler kullandim
			b1 = j % 10;       
			b2 = (j + 1) % 10;
			
			if(a[a1][b1] > a[a2][b2]) {
				
				/* dizideki j. eleman ile (j + 1). eleman karsilastiriliyor */
				
				temp = a[a1][b1];
				a[a1][b1] = a[a2][b2];
				a[a2][b2] = temp;
				
				/* eger j. eleman (j + 1). elemandan buyuk ise j. eleman ile
				(j + 1). elemanin degerleri birbirleri ile degistiriliyor */
				
			}
			
		}
	
	}
	
	printf("kucukten buyuge siralama: ");
	for(i = 0; i < satir; i++) {
		
		for(j = 0; j < sutun; j++) {
			
			printf("%d ", a[i][j]); // ekrana siralama cikti olarak veriliyor
			
		}
		
	}
	
	return 0;
}
```

Dizideki Elemanları Büyükten Küçüğe Sıralama:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {

	int a[3][2] = {3, 32, 2, 45, 14, 13};
	
	int i, j, temp = 0, boyut = 3 * 2; /* islemler daha iyi anlasilsin diye eleman sayisini 'boyut'
	degiskenine atadim */
	
	
	int satir = 3, sutun = 2, a1, a2, b1, b2; /* islemler daha iyi anlasilsin diye satir ve sutun 
	sayisini 'satir' ve 'sutun' degiskenlerine atadim */
	
	for(i = 0; i < boyut - 1; i++) {

		for(j = 0; j < boyut - 1 - i; j++)  {
	
			a1 = j / 10;
			a2 = (j + 1) / 10; //islemleri kolaylastirmak icin ek degiskenler kullandim
			b1 = j % 10;       
			b2 = (j + 1) % 10;
			
			if(a[a1][b1] < a[a2][b2]) {
				
				/* dizideki j. eleman ile (j + 1). eleman karsilastiriliyor */
				
				temp = a[a1][b1];
				a[a1][b1] = a[a2][b2];
				a[a2][b2] = temp;
				
				/* eger j. eleman (j + 1). elemandan kucuk ise j. eleman ile
				(j + 1). elemanin degerleri birbirleri ile degistiriliyor */
				
			}
			
		}
	
	}
	
	cout << "buyukten kucuge siralama: ";
	for(i = 0; i < satir; i++) {
		
		for(j = 0; j < sutun; j++) {
			
			cout << a[i][j] << " "; // ekrana siralama cikti olarak veriliyor
			
		}
		
	}
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>

int main() {

	int a[3][2] = {3, 32, 2, 45, 14, 13};
	
	int i, j, temp = 0, boyut = 3 * 2; /* islemler daha iyi anlasilsin diye eleman sayisini 'boyut'
	degiskenine atadim */
	
	
	int satir = 3, sutun = 2, a1, a2, b1, b2; /* islemler daha iyi anlasilsin diye satir ve sutun 
	sayisini 'satir' ve 'sutun' degiskenlerine atadim */
	
	for(i = 0; i < boyut - 1; i++) {

		for(j = 0; j < boyut - 1 - i; j++)  {
	
			a1 = j / 10;
			a2 = (j + 1) / 10; //islemleri kolaylastirmak icin ek degiskenler kullandim
			b1 = j % 10;       
			b2 = (j + 1) % 10;
			
			if(a[a1][b1] < a[a2][b2]) {
				
				/* dizideki j. eleman ile (j + 1). eleman karsilastiriliyor */
				
				temp = a[a1][b1];
				a[a1][b1] = a[a2][b2];
				a[a2][b2] = temp;
				
				/* eger j. eleman (j + 1). elemandan kucuk ise j. eleman ile
				(j + 1). elemanin degerleri birbirleri ile degistiriliyor */
				
			}
			
		}
	
	}
	
	printf("buyukten kucuge siralama: ");
	for(i = 0; i < satir; i++) {
		
		for(j = 0; j < sutun; j++) {
			
			printf("%d ", a[i][j]); // ekrana siralama cikti olarak veriliyor
			
		}
		
	}
	
	return 0;
}
```
