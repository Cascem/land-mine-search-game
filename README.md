# land-mine-search-game
My first big C project
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <Windows.h>
#include "evolution.h"
int main() {
	int i, j, x, y, c = 0;
	for (i = 1; i <= 9; i++) {
		for (j = 1; j <= 9; j++) {
			map2[i][j] = 'O';
		}
	}
	for (i = 0; i < 11; i++) {
		for (j = 0; j < 11; j++) {
			if (i == 0) {
				if (j == 0)
					printf(" ┌");
				else if (j == 10)
					printf("┐");
				else
					printf("──");
			}
			else if (i == 10) {
				if (j == 0)
					printf(" └");
				else if (j == 10)
					printf("┘");
				else
					printf("──");
			}
			else if (i >= 1 && j >= 1 && i <= 9 && j <= 9) {
				printf("%2c",map2[i][j]);
			}
			else if (j == 0 || j == 10) {
					if (j == 0)
						printf("%d", 10 - i);
					printf("│");
				}
		}
		printf("\n");
	}
	printf("  ");
	for (i = 1; i <= 9; i++) {
		printf("%2d", i);
	}
	while (1) {
		printf("\n위치를 입력하세요!!");
		scanf_s("%d %d", &y, &x);
		x = 10 - x;
		paint(x, y);
		system("cls");
		if (map1[x][y] == 9) {
			printf("지뢰를 밟았습니다!!\n");
			break;

		}
		for (i = 0; i < 11; i++) {
			for (j = 0; j < 11; j++) {
				if (i == 0) {
					if (j == 0)
						printf(" ┌");
					else if (j == 10)
						printf("┐");
					else
						printf("──");
				}
				else if (i == 10) {
					if (j == 0)
						printf(" └");
					else if (j == 10)
						printf("┘");
					else
						printf("──");
				}
				else if (i >= 1 && j >= 1 && i <= 9 && j <= 9) {
					printf("%2c", map2[i][j]);
				}
				else if (j == 0 || j == 10) {
					if (j == 0)
						printf("%d", 10 - i);
					printf("│");
				}
			}
			printf("\n");
		}
		printf("  ");
		for (i = 1; i <= 9; i++) {
			printf("%2d", i);
		}
	}
	for (i = 0; i < 11; i++) {
		for (j = 0; j < 11; j++) {
			if (i == 0) {
				if (j == 0)
					printf(" ┌");
				else if (j == 10)
					printf("┐");
				else
					printf("──");
			}
			else if (i == 10) {
				if (j == 0)
					printf(" └");
				else if (j == 10)
					printf("┘");
				else
					printf("──");
			}
			else if (i >= 1 && j >= 1 && i <= 9 && j <= 9) {
				printf("%2d", map1[i][j]);
			}
			else if (j == 0 || j == 10) {
				if (j == 0)
					printf("%d", 10 - i);
				printf("│");
			}
		}
		printf("\n");
	}
	printf("  ");
	for (i = 1; i <= 9; i++) {
		printf("%2d", i);
	}
	return 0;
}
