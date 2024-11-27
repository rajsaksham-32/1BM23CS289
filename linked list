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

void insert_at_beginning(struct Node** head, int data) {
    struct Node* new_node = create_node(data);
    if (new_node == NULL) return;
    new_node->next = *head;
    *head = new_node;
}

void insert_at_end(struct Node** head, int data) {
    struct Node* new_node = create_node(data);
    if (new_node == NULL) return;
    if (*head == NULL) {
        *head = new_node;
        return;
    }
    struct Node* last = *head;
    while (last->next != NULL) {
        last = last->next;
    }
    last->next = new_node;
}

void insert_at_position(struct Node** head, int data, int position) {
    struct Node* new_node = create_node(data);
    if (new_node == NULL) return;
    if (position == 0) {
        new_node->next = *head;
        *head = new_node;
        return;
    }
    struct Node* current = *head;
    int count = 0;
    while (current != NULL && count < position - 1) {
        current = current->next;
        count++;
    }
    if (current == NULL) {
        printf("Position out of range.\n");
        free(new_node);
        return;
    }
    new_node->next = current->next;
    current->next = new_node;
}

void delete_from_beginning(struct Node** head) {
    if (*head == NULL) {
        printf("List is empty.\n");
        return;
    }
    struct Node* temp = *head;
    *head = temp->next;
    free(temp);
}

void delete_from_end(struct Node** head) {
    if (*head == NULL) {
        printf("List is empty.\n");
        return;
    }
    struct Node* current = *head;
    struct Node* prev = NULL;
    if (current->next == NULL) {
        free(current);
        *head = NULL;
        return;
    }
    while (current->next != NULL) {
        prev = current;
        current = current->next;
    }
    prev->next = NULL;
    free(current);
}

void delete_from_position(struct Node** head, int position) {
    if (*head == NULL) {
        printf("List is empty.\n");
        return;
    }
    struct Node* current = *head;
    struct Node* prev = NULL;
    if (position == 0) {
        *head = current->next;
        free(current);
        return;
    }
    int count = 0;
    while (current != NULL && count < position) {
        prev = current;
        current = current->next;
        count++;
    }
    if (current == NULL) {
        printf("Position out of range.\n");
        return;
    }
    prev->next = current->next;
    free(current);
}

void print_list(struct Node* head) {
    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }
    struct Node* current = head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    insert_at_beginning(&head, 10);
    insert_at_beginning(&head, 20);
    insert_at_beginning(&head, 30);
    printf("After Inserting at Beginning: ");
    print_list(head);
    insert_at_end(&head, 40);
    insert_at_end(&head, 50);
    printf("After Inserting at End: ");
    print_list(head);
    insert_at_position(&head, 25, 2);
    printf("After Inserting at Position 2: ");
    print_list(head);
    delete_from_beginning(&head);
    printf("After Deleting from Beginning: ");
    print_list(head);
    delete_from_end(&head);
    printf("After Deleting from End: ");
    print_list(head);
    delete_from_position(&head, 1);
    printf("After Deleting from Position 1: ");
    print_list(head);
    return 0;
}
