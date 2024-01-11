
**Rus ruleti**, altıpatlarla oynanan ölümcül bir şans oyunu. Tabancaya tek bir kurşun yerleştirilir ve kurşunun yeri belli olmayacak şekilde top çevrilir. Oyuncular sırayla tabancayı şakaklarına dayarlar ve tetiği çekmek suretiyle şanslarını denerler. Rus ifadesi oyunun doğduğu ülkeye işaret etmektedir.

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
	
	char cevap = 'e';
	
	while(cevap == 'e' || cevap == 'E') {
	
		char atis = 's';
		int sayac = -1, i, kursun[6], olum_kursunu;
	
		srand(time(0));
	
		for(i = 0; i < 6; i++) {
		
			/* kursunlar sifirlaniyor */
		
			kursun[i] = 0;
			
		}
	
		olum_kursunu = (rand() % (5 - 0 + 1)) + 0; /*kursun dizisi icin 0 - 5 arasinda
		rastgele sayi olusturuluyor */
	
		kursun[olum_kursunu] = 1; /* olusturulan sayi degeri 0 dan farkli olacak indekstir */
		
		printf("\n");
		printf("************* RUS RULETI ************* \n");
	
		while(atis == 's') {
		
			printf("\n");
		
			printf("OYUNCU 1 in sirasi \n");
			printf("ates etmek icin 's' yaziniz: ");
			scanf(" %c", &atis);
		
			sayac++; /* sayac -1 den baslar ve birer birer artar */
		
			if(kursun[sayac] != 0) {
			
				/* oyuncunun olup olmedigi kontrol edilir */
			
				printf("oyuncu 1 oldu !!! \n");
				break;
			
			}		
		
			else {
			
				printf("oyuncu 1 olmedi \n");
			
			}	
		
			printf("\n");
		
			printf("OYUNCU 2 nin sirasi \n");
			printf("ates etmek icin 's' yaziniz: ");
			scanf(" %c", &atis);
		
			sayac++;
		
			if(kursun[sayac] != 0) {
			
				/* oyuncunun olup olmedigi kontrol edilir */
			
				printf("oyuncu 2 oldu !!! \n");
				break;
			
			}			
		
			else {
			
				printf("oyuncu 2 olmedi \n");
			
			}
		
		}
		
		printf("\n");
		printf("OYUNA DEVAM ETMEK ISTIYOR MUSUNUZ ? (e, h): ");
		scanf(" %c", &cevap);
	
	}
	
	return 0;
}
```
