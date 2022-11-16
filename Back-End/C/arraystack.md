# arraystack
```c
#include <stdio.h>
#include <stdlib.h>
#define STACK_SIZE	10
int topIdx = -1;           
int aryStack[STACK_SIZE];
void init() {
	topIdx = -1;  
}
void push(int data) {
	if (topIdx < STACK_SIZE - 1)
		aryStack[++topIdx] = data;
}
int pop() {
	if (topIdx >= 0)
		return aryStack[topIdx--];
	return -1;
}
int peek() {
	return aryStack[topIdx];
}

int main() {
	push(1); push(2); push(3); push(4); push(5);
	push(11); push(22); push(33); push(44); push(55);
	push(111); push(222);

	printf("pop 연산 수행: %d 꺼냄\n", pop());
	printf("pop 연산 수행: %d 꺼냄\n", pop());
	printf("pop 연산 수행: %d 꺼냄\n", pop());

	printf("peek 연산으로 맨위 데이터 확인: %d", peek());
}
```