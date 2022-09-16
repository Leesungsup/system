# system
이상한 출석 번호 부르기3
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
void main() {
	int n,temp;
	int a[10000];
	scanf("%d",&n);
	for (int i = 0; i < n; i++) {
		scanf("%d", &a[i]);
	}
	for (int i = 0; i < n; i++) {
		for (int j = 0; j < n - i; j++) {
			if (a[i] > a[j]) {
				temp = a[i];
				a[i] = a[j];
				a[j] = a[i];
			}
		}
	}
	printf("%d", a[0]);
}

바둑알십자 뒤집기
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
void main() {
    int n, i, j, x, y;
    int map[20][20];
    for (i = 1; i <= 19; i++) { //한 줄씩 바둑판 상황 입력 받기
        for (j = 1; j <= 19; j++) {
            scanf("%d", &map[i][j]);
        }
    }

    scanf("%d", &n); //좌표 개수 입력받기

    for (i = 1; i <= n; i++) //좌표의 개수만큼
    {
        scanf("%d %d", &x, &y);
        for (j = 1; j <= 19; j++) //가로 줄 흑<->백 바꾸기
        {
            if (map[x][j] == 0) {
                map[x][j] = 1;
            }
            else {
                map[x][j] = 0;
            }
        }
        for (j = 1; j <= 19; j++) //세로 줄 흑<->백 바꾸기
        {
            if (map[j][y] == 0) {
                map[j][y] = 1;
            }
            else {
                map[j][y] = 0;
            }
        }
    }
    for (i = 1; i <= 19; i++) { //한 줄씩 바둑판 상황 출력
        for (j = 1; j <= 19; j++) {
            printf("%d ", map[i][j]);
        }
        printf("\n");
    }
}
