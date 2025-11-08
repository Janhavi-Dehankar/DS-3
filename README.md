# DS-3
DS code
#include <stdio.h>
#include <stdlib.h>

#define SIZE 10

int arr[SIZE];
int top1 = -1;
int top2 = SIZE;

void push1(int x) {
    if (top1 < top2 - 1)
        arr[++top1] = x;
    else
        printf("Stack Overflow in Stack 1\n");
}

void push2(int x) {
    if (top1 < top2 - 1)
        arr[--top2] = x;
    else
        printf("Stack Overflow in Stack 2\n");
}

void pop1() {
    if (top1 >= 0)
        printf("Popped element from Stack 1: %d\n", arr[top1--]);
    else
        printf("Stack Underflow in Stack 1\n");
}

void pop2() {
    if (top2 < SIZE)
        printf("Popped element from Stack 2: %d\n", arr[top2++]);
    else
        printf("Stack Underflow in Stack 2\n");
}

void display() {
    int i;
    printf("\nStack 1: ");
    for (i = 0; i <= top1; i++)
        printf("%d ", arr[i]);
    printf("\nStack 2: ");
    for (i = SIZE - 1; i >= top2; i--)
        printf("%d ", arr[i]);
    printf("\n");
}

int main() {
    int choice, value;
    while (1) {
        printf("\n1. Push in Stack 1\n2. Push in Stack 2\n3. Pop from Stack 1\n4. Pop from Stack 2\n5. Display\n6. Exit\nEnter choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1: printf("Enter value: "); scanf("%d", &value); push1(value); break;
            case 2: printf("Enter value: "); scanf("%d", &value); push2(value); break;
            case 3: pop1(); break;
            case 4: pop2(); break;
            case 5: display(); break;
            case 6: exit(0);
            default: printf("Invalid choice\n");
        }
    }
    return 0;
}
