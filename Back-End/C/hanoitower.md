# hanoitower
```c
#include <stdio.h>
void hanoiTower(int numOfDisk, char start, char temp, char goal) {
	static int count = 0;
	if (numOfDisk == 1) {
		printf("%d번째 원반을 %c -> %c 이동함\n",++count, start, goal);
	}
	else {
		hanoiTower(numOfDisk - 1, start, goal, temp);
		printf("%d번쨰 원반을 %c -> %c 이동함\n", ++count, start, goal);
		hanoiTower(numOfDisk - 1, temp, start, goal);
	}
}

int main() {
	hanoiTower(4, 'A', 'B', 'C');
}
```