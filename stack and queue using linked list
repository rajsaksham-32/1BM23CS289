#include <stdio.h>
#include <malloc.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* create_node(int data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    if (new_node == NULL) {
        printf("Memory allocation failed!\n");
        return NULL;
    }
    new_node->data = data;
    new_node->next = NULL;
    return new_node;
}

void stack_push(struct Node** top, int data) {
    struct Node* new_node = create_node(data);
    if (new_node == NULL) return;
    new_node->next = *top;
    *top = new_node;
}

void stack_pop(struct Node** top) {
    if (*top == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    struct Node* temp = *top;
    printf("Deleted node from stack: %d\n", temp->data);
    *top = temp->next;
    free(temp);
}

void queue_push(struct Node** rear, struct Node** front, int data) {
    struct Node* new_node = create_node(data);
    if (new_node == NULL) return;
    if (*rear == NULL) {
        *rear = new_node;
        *front = new_node;
        return;
    }
    (*rear)->next = new_node;
    *rear = new_node;
}

void queue_pop(struct Node** rear, struct Node** front) {
    if (*front == NULL) {
        printf("Queue underflow.\n");
        return;
    }
    struct Node* temp = *front;
    printf("Deleted data from queue: %d\n", temp->data);
    *front = temp->next;
    if (*front == NULL) { // Queue is now empty
        *rear = NULL;
    }
    free(temp);
}

int main() {
    // Stack operations
    struct Node* top = NULL;
    stack_push(&top, 10);
    stack_push(&top, 20);
    stack_push(&top, 30);
    stack_pop(&top);

    // Queue operations
    struct Node* rear = NULL;
    struct Node* front = NULL;
    queue_push(&rear, &front, 10);
    queue_push(&rear, &front, 20);
    queue_push(&rear, &front, 30);
    queue_pop(&rear, &front);

    return 0;
}
