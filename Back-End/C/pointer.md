# pointer
```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void arypuls(int ary[], int n) {
	for (int i = 0; i < n; i++) {
		ary[i] = ary[i] + 1;
	}
}
void ptrplus(int *ptr, int n) {
	for (int i = 0; i < n; i++) {
		*(ptr + i) =  *(ptr + i) + 1;
	}
}

void ptrfunc(int *ptr, int isize, int jsize) {
	for (int i = 0; i < isize; i++) {
		for (int j = 0; j < jsize; j++){
			printf("%d", *((ptr + i * jsize) + j));
		}
		printf("\n");
	}
}

int main() {
	int a[] = { 10,20,30,40,50 };
	
	arypuls(a, 5);
	ptrplus(a, 5);

	int a1[2][4] = { 1,2,3,4,5,6,7,8 };
	int a2[3][4] = { 1,2,3,4,5,6,7,8,9,10,11,12 };
	int a3[3][3] = { 1,2,3,4,5,6,7,8,9 };

	printf("&a[0]=%u\n", &a[0]);
	printf("&a[1]=%u\n", &a[1]);
	printf("&a[2]=%u\n", &a[2]);
	printf("&a=%u\n", &a);
	printf("a=%u\n", a);
	printf("a=1=%u\n", a + 1);
```