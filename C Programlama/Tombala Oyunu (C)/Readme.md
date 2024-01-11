
Tombala oyununda oyuncuların tek bir taş havuzu vardır ve taş havuzunda “90” tane taş vardır. Oyuncuların amacı kartlarındaki sayıları çektikleri sayılar ile eşleştirmektir. Yazdığım programda 2 tane oyuncu vardır. Her oyuncunun 15 sayılık kartı vardır. Taş havuzundaki taşlar bittikçe yenilenmektedir.

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

/* TOMBALA */

int main() {
	
	srand(time(0)); 
		
	int taslar[90], oyuncu1[15], oyuncu2[15], i, cekilen_tas = -1, oyuncu1_temp[15], oyuncu2_temp[15];
	int j, taslar_temp, kontrol, kontrol_2;
	char tas_cek_oyuncu1 = 's';
	char tas_cek_oyuncu2 = 's';
	
	for(i = 0; i < 90; i++) {
		
		/* oyuncularin tas havuzu olusturuluyor */
		
		taslar[i] = i + 1;
		
	}
	
	for(i = 0; i < 15; i++) {
		
		/* oyuncularin tombala kartlari olusturuluyor */
		
		oyuncu1[i] = (rand() % (90 - 1 + 1)) + 1;
		
		for(j = 0; j < i; j++) {
			
			if(oyuncu1[j] == oyuncu1[i]) {
				
				/* oyuncunun kartinda ayni sayidan var mi diye kontrol ediliyor */
			
				while(oyuncu1[j] == oyuncu1[i])	{
				
					/* var ise sayi degistiriliyor */
				
					oyuncu1[i] = (rand() % (90 - 1 + 1)) + 1;
				
				}
				
			}
			
		}
		
		oyuncu2[i] = (rand() % (90 - 1 + 1)) + 1;
		
		for(j = 0; j < i; j++) {
			
			if(oyuncu2[j] == oyuncu2[i]) {
				
				/* oyuncunun kartinda ayni sayidan var mi diye kontrol ediliyor */
			
				while(oyuncu2[j] == oyuncu2[i])	{
					
					/* var ise sayi degistiriliyor */
				
					oyuncu2[i] = (rand() % (90 - 1 + 1)) + 1;
				
				}
				
			}
			
		}
		
		oyuncu1_temp[i] = 0; //kart kontrol dizileri
		oyuncu2_temp[i] = 0;
		
	}
	
	printf("OYUNCU 1 \n");
	
	for(i = 0; i < 15; i++) {
		
		/* oyunculara kartlari gosteriliyor */
		
		printf(" [%d] \n", oyuncu1[i]);
		
	}
	
	printf("\n***************************************\n");
	
	printf("OYUNCU 2 \n");
	
	for(i = 0; i < 15; i++) {
		
		/* oyunculara kartlari gosteriliyor */
		
		printf(" [%d] \n", oyuncu2[i]);
		
	}
	
	while(tas_cek_oyuncu1 == 's' || tas_cek_oyuncu2 == 's') {
		
		kontrol = 0;
		kontrol_2 = 0;
		
		/* 's' yazilarak tas cekiliyor */
	
		printf("oyuncu1 in sirasi (torbadan tas cekmek icin 's' yaziniz): ");
		scanf(" %c", &tas_cek_oyuncu1);
		
		while(cekilen_tas == -1) {
		
			/*tas havuzundan ayni tasin cekilip cekilmedigi kontrol ediliyor */
		
			taslar_temp = (rand() % (89 - 0 + 1)) + 0;
			cekilen_tas = taslar[taslar_temp]; // bu formulu internetten buldum linki en alt satirda
		
		}
		
		/* oyuncu1 icin rastgele tas cekiliyor */
		
		system("cls");
		
		printf("\n");
		
		printf("cekilen tas: %d \n", cekilen_tas);
		
		printf("OYUNCU1 \n");
		printf("\n");
		
		for(i = 0; i < 15; i++) {
			
			/* cekilen tasin karttaki herhangi bir sayi ile es olup olmadigina
			bakiliyor */
			
			if(cekilen_tas == oyuncu1[i]) {
				
				oyuncu1_temp[i] = oyuncu1[i];
				
				printf("\t [%d] = [%d] \n", oyuncu1[i], oyuncu1_temp[i]);
				
			}
			
			else {
				
				printf("\t [%d] = [%d] \n", oyuncu1[i], oyuncu1_temp[i]);
				
			}
			
		}
		
		for(i = 0; i < 15; i++) {
			
			/* oyuncu1 oyunu kazandi mi kazanmadi mi kontrol ediliyor */
			
			if(oyuncu1[i] != oyuncu1_temp[i]) {
				
				kontrol_2 = 1;
				break;
				
			}
			
		}
		
		if(kontrol_2 == 0) {
			
			/* kazandi ise ekrana yazdiriliyor */
			
			printf("OYUNCU 1 OYUNU KAZANDI !!!");
			break;
			
		} 
		
		
		printf("\n");
		
		kontrol_2 = 0;
		taslar[taslar_temp] = -1;
		taslar_temp = 0;
		
		printf("oyuncu2 in sirasi (torbadan tas cekmek icin 's' yaziniz): ");
		scanf(" %c", &tas_cek_oyuncu2);
		
		cekilen_tas = -1;
		
		while(cekilen_tas == -1) {
		
			/*tas havuzundan ayni tasin cekilip cekilmedigi kontrol ediliyor */
		
			taslar_temp = (rand() % (89 - 0 + 1)) + 0;
			cekilen_tas = taslar[taslar_temp]; // bu formulu internetten buldum linki en alt satirda
		
		}
		
		/* oyuncu2 icin rastgele tas cekiliyor */
		
		system("cls");
		
		printf("\n");
		
		printf("cekilen tas: %d \n", cekilen_tas);
		
		printf("OYUNCU2 \n");
		printf("\n");
		
		for(i = 0; i < 15; i++) {
			
			/* cekilen tasin karttaki herhangi bir sayi ile es olup olmadigina
			bakiliyor */
			
			if(cekilen_tas == oyuncu2[i]) {
				
				oyuncu2_temp[i] = oyuncu2[i];
				
				printf("\t [%d] = [%d] \n", oyuncu2[i], oyuncu2_temp[i]);
				
			}
			
			else {
				
				printf("\t [%d] = [%d] \n", oyuncu2[i], oyuncu2_temp[i]);
				
			}
			
		}
		
		for(i = 0; i < 15; i++) {
			
			/* oyuncu2 oyunu kazandi mi kazanmadi mi kontrol ediliyor */
			
			if(oyuncu2[i] != oyuncu2_temp[i]) {
				
				kontrol_2 = 1;
				break;
				
			}
			
		}
		
		if(kontrol_2 == 0) {
			
			/* kazandi ise ekrana yazdiriliyor */
			
			printf("OYUNCU 2 OYUNU KAZANDI !!!");
			break;
			
		}
		
		printf("\n");
		
		taslar[taslar_temp] = -1;
		taslar_temp = 0;
		cekilen_tas = -1; // cekilen tas sifirlaniyor
		
		for(i = 0; i < 90; i++) {
			
			/* taslarin bitip bitmedigi kontrol ediliyor */
			
			if(taslar[i] == -1) {
				
				kontrol++;
				
			}
			
		}
		
		if(kontrol == 90) {
			
			for(i = 0; i < 90; i++) {
			
				/* bitti ise tas havuzu yeniden olusturuluyor */
		
				taslar[i] = i + 1;
		
			}
			
			printf("\n TASLAR YENILENDI \n");
			
		}
	
	}

	return 0;

}

/* https://www.geeksforgeeks.org/generating-random-number-range-c/ */
```
