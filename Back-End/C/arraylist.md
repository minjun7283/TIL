# arraylist
```c
#include <stdio.h>
#define LIST_SIZE 5

int list[LIST_SIZE] = { 0 };
int numOfDatas = 0;

void listinit() {
	numOfDatas = 0;
}

void insert(int data) {
	if (numOfDatas < LIST_SIZE) 
		list[numOfDatas++] = data;
	else
	printf("꽉참");
}

int search(int searchData) {
	if (numOfDatas == 0) {
		printf("없음");
		return -1;
	}
	for (int i = 0; i < numOfDatas; i++) {
		if (list[i] == searchData)
			return i;
		return -1;
	}
}

void updata(int targetData,int updateData) {
	if (numOfDatas == 0) {
		printf("없음");
		return;
	}
	for (int i = 0; i < numOfDatas; i++) {
		if (list[i] == targetData)
			list[i] = updateData;
	}
}

void doDelete(int deleteData) {
	if (numOfDatas == 0) {
		printf("없음");
		return;
	}
	for (int i = 0; i < numOfDatas; i++) {
		if (list[i] == deleteData) {
			for (int j = i; j < numOfDatas - 1; j++) {
				list[j] = list[j + 1];
			}
			numOfDatas -= 1;
			i -= i;
		}
			
	}
}

void printfAll() {
	for (int i = 0; i < numOfDatas; i++) {
		printf("%d", list[i]);
		printf("\n\n");
	}
}

int main() {
	listinit();

	insert(1);
	insert(2);
	insert(4);
	insert(5);
	insert(3);
	insert(5);
	insert(5);

	printfAll();
	doDelete(5);
	printfAll();
	printf("리스트 내에 %d가 있는지 탐색: %d\n", 30, search(30));
	
}
```