# linkedlist
```c
#include <stdio.h>
#include <stdlib.h>

typedef struct _node {
    int data;
    struct _node* next;
} Node;

Node* head, * tail;


void insert(int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));

    newNode->data = data;
    newNode->next = NULL;


    if (head == NULL) { 
        head = newNode;
    }
    else {
        tail->next = newNode;
    }
    tail = newNode;
}



void printAll() {
    Node* cur = head;
    while (cur != NULL) {
        printf("[%d]", cur->data); 
        cur = cur->next; 
    }
    printf("\n");
}


int find(int findData) {
    Node* cur = head;
    while (cur != NULL) {
        if (cur->data == findData) {
            return cur->data;
        }
        cur = cur->next;
    }
    return -1;
}

// 변경
void update(int targetData, int updateData) {
    Node* cur = head;
    while (cur != NULL) {
        if (cur->data == targetData) {
            cur->data = updateData;
        }
        cur = cur->next;
    }
    return;
}

void deleteNode(int deleteData) {
    Node* delNode = NULL;
    Node* cur = head;
    Node* prev = NULL;
    if (cur->data == deleteData && head == tail) {     
        delNode = cur;
        free(delNode);       
        head = NULL;
        tail = NULL;
        return;
    }
    
    while (cur != NULL) {
        if (cur->data == deleteData) {
            delNode = cur;
            if (cur == head) {     
                head = cur->next;
                cur = cur->next;
            }
            else {  
                cur = cur->next;
                prev->next = cur;
                if (delNode == tail)
                    tail = prev;
            }
            free(delNode);
        }
        else {
            prev = cur;
            cur = cur->next;
        }
    }
    return;
}

int main() {
    insert(1);
    insert(1);
    printAll();
    deleteNode(1);
    printAll();

    insert(0);
    insert(1);  insert(1);
    insert(3); insert(4);
    insert(5); insert(5);
    insert(7); insert(9); insert(9);
    insert(11);
    deleteNode(0);
    printAll();

    deleteNode(1);
    printAll();

    deleteNode(7);
    printAll();
    deleteNode(5);
    printAll();

    deleteNode(11);
    printAll();
    deleteNode(9);
    printAll();
}
```