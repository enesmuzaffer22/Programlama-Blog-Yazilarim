
Tic-tac-toe, üçe üç ızgarada boşlukları X veya O ile işaretleyen iki oyuncu için bir kağıt-kalem oyunudur. Yatay, dikey veya çapraz sıradaki işaretlerinden üçünü yerleştirmeyi başaran oyuncu kazanır.

```cpp
#include <iostream>
#include <string>
using namespace std;

/*

   |   |
---|---|---
   |   |   
---|---|---
   |   |

*/

char tablo[3][3];

void bos_tablo();
int tablo_ciz(int, int);
int kazanan();
int bosluk_kontrol(int, int);

void bos_tablo() {
	
		//baslangicta bos tablo cizmek icin kullanilan fonksiyon
	
		cout << " " << tablo[0][0] << " " << "|" << " " << tablo[0][1] << " " << "|" << " " << tablo[0][2] << " " << endl;
		cout << "---|---|---" << endl;
		cout << " " << tablo[1][0] << " " << "|" << " " << tablo[1][1] << " " << "|" << " " << tablo[1][2] << " " << endl;
		cout << "---|---|---" << endl;
		cout << " " << tablo[2][0] << " " << "|" << " " << tablo[2][1] << " " << "|" << " " << tablo[2][2] << " " << endl;
	
}

int kazanan() {
	
	//kazanma olasiliklarina gore degerler donuyor

	if (tablo[0][0] == 'X' && tablo[0][1] == 'X' && tablo[0][2] == 'X') {

		return 2;

	}

	else if (tablo[1][0] == 'X' && tablo[1][1] == 'X' && tablo[1][2] == 'X') {

		return 2;

	}

	else if (tablo[2][0] == 'X' && tablo[2][1] == 'X' && tablo[2][2] == 'X') {

		return 2;

	}

	else if (tablo[0][0] == 'X' && tablo[1][0] == 'X' && tablo[2][0] == 'X') {

		return 2;

	}


	else if (tablo[0][1] == 'X' && tablo[1][1] == 'X' && tablo[2][1] == 'X') {

		return 2;

	}

	else if (tablo[0][2] == 'X' && tablo[1][2] == 'X' && tablo[2][2] == 'X') {

		return 2;

	}

	else if (tablo[0][0] == 'X' && tablo[1][1] == 'X' && tablo[2][2] == 'X') {

		return 2;

	}

	else if (tablo[0][2] == 'X' && tablo[1][1] == 'X' && tablo[2][0] == 'X') {

		return 2;

	}

	else if (tablo[0][0] == 'O' && tablo[0][1] == 'O' && tablo[0][2] == 'O') {

		return 1;

	}

	else if (tablo[1][0] == 'O' && tablo[1][1] == 'O' && tablo[1][2] == 'O') {

		return 1;

	}

	else if (tablo[2][0] == 'O' && tablo[2][1] == 'O' && tablo[2][2] == 'O') {

		return 1;

	}

	else if (tablo[0][0] == 'O' && tablo[1][0] == 'O' && tablo[2][0] == 'O') {

		return 1;

	}


	else if (tablo[0][1] == 'O' && tablo[1][1] == 'O' && tablo[2][1] == 'O') {

		return 1;

	}

	else if (tablo[0][2] == 'O' && tablo[1][2] == 'O' && tablo[2][2] == 'O') {

		return 1;

	}

	else if (tablo[0][0] == 'O' && tablo[1][1] == 'O' && tablo[2][2] == 'O') {

		return 1;

	}

	else if (tablo[0][2] == 'O' && tablo[1][1] == 'O' && tablo[2][0] == 'O') {

		return 1;

	}

	else {
		
		
		return 0;
		
	}

}

int bosluk_kontrol(int x_kontrol, int y_kontrol) {
	
	//bosluk kontrolu yapiliyor ve sonuclara gore degerler donuyor

	int a, b, bosluk = 0;

	for(a = 0; a < 3; a++) {
			
		for(b = 0; b < 3; b++) {
				
			if(tablo[a][b] == ' ') {
				
				bosluk = 1;
				
			}
				
		}
			
	}

	if (tablo[x_kontrol][y_kontrol] == ' ') {

		return 1;
		
	}
	
	else if(bosluk == 0) {
		
		return 2;
		
	}

	else {

		return 0;

	}
	


}

int tablo_ciz(int x, int y, int sayac) {
	
	//tablo cizimi icin fonksiyon
	
	if ((sayac % 2) == 1) {

		tablo[x][y] = 'X';
		cout << " " << tablo[0][0] << " " << "|" << " " << tablo[0][1] << " " << "|" << " " << tablo[0][2] << " " << endl;
		cout << "---|---|---" << endl;
		cout << " " << tablo[1][0] << " " << "|" << " " << tablo[1][1] << " " << "|" << " " << tablo[1][2] << " " << endl;
		cout << "---|---|---" << endl;
		cout << " " << tablo[2][0] << " " << "|" << " " << tablo[2][1] << " " << "|" << " " << tablo[2][2] << " " << endl;

	}

	if ((sayac % 2) == 0) {

		tablo[x][y] = 'O';
		cout << " " << tablo[0][0] << " " << "|" << " " << tablo[0][1] << " " << "|" << " " << tablo[0][2] << " " << endl;
		cout << "---|---|---" << endl;
		cout << " " << tablo[1][0] << " " << "|" << " " << tablo[1][1] << " " << "|" << " " << tablo[1][2] << " " << endl;
		cout << "---|---|---" << endl;
		cout << " " << tablo[2][0] << " " << "|" << " " << tablo[2][1] << " " << "|" << " " << tablo[2][2] << " " << endl;

	}

}

int main() {

	int i, j, x_main, y_main, kontrol = 1, sayac_main = 1, kazanan_kontrol;

	for (i = 0; i < 3; i++) {

		for (j = 0; j < 3; j++) {

			tablo[i][j] = ' ';

		}

	}
	
	bos_tablo();

	while (kontrol == 1) {
	
		kontrol = 0;

		while (kontrol == 0) {
			
			//satir ve sutun numaralari giriliyor ve bosluk kontrolu yapiliyor
			
			cout << "satir numarasi giriniz (1, 3): ";
			cin >> x_main;
			cout << "sutun numarasi giriniz (1, 3): ";
			cin >> y_main;
			
			x_main--;
			y_main--;
			
			kontrol = bosluk_kontrol(x_main, y_main);

		}
		
		system("cls");

		if (kontrol == 1) {
			
			//bosluk var ise girilen numaralara gore tablo ciziliyor
			
			sayac_main++;
			
			tablo_ciz(x_main, y_main, sayac_main);
			kazanan_kontrol = kazanan(); //kazanan var mi diye kontrol ediliyor

			if (kazanan_kontrol == 1) {

				cout << "kazanan 'O' oldu ";
				break;

			}

			else if (kazanan_kontrol == 2) {

				cout << "kazanan 'X' oldu ";
				break;

			}

		}

		else if (kontrol == 2) {

			// bos yer kalmaz ise dongu duruyor

			cout << "bos yer kalmadi" << endl;
			break;
			
		}

	}

	return 0;
}
```
