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
struct Node* concate(struct Node** head1,struct Node* head2){
    if(head1==NULL){
        *head1=head2;
        return *head1;
    }
    struct Node* temp=*head1;
    while(temp->next!=NULL){
        temp=temp->next;
    }
    temp->next=head2;
    return *head1;
}
void sort(struct Node* head){
    struct Node* i=head;
    while(i->next!=NULL){
       
        struct Node* j=i->next;
        while(j!=NULL){
            if(i->data > j->data){
                int temp=j->data;
                j->data=i->data;
                i->data=temp;
            }
            j=j->next;
        }
        i=i->next;
    }
}
struct Node* reverse(struct Node* head){
    struct Node* prev=NULL;
    struct Node* current=head;
    while(current!=NULL){
        struct Node* temp=current->next;
        current->next=prev;
        prev=current;
        current=temp;
    }
    return prev;
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
      insert_at_end(&head,10);
      insert_at_end(&head,20);
      insert_at_end(&head,40);
      insert_at_end(&head,30);
      printf("List before\n");
      print_list(head);
      struct Node* rev=reverse(head);
      printf("List After reverse\n");
      print_list(rev);
      sort(rev);
      printf("after sorting\n");
      print_list(rev);
      struct Node* head1 = NULL;
      insert_at_end(&head1,70);
      insert_at_end(&head1,50);
      insert_at_end(&head1,100);
      insert_at_end(&head1,35);
        struct Node* head2 = NULL;
      insert_at_end(&head2,10);
      insert_at_end(&head2,20);
      insert_at_end(&head2,30);
      insert_at_end(&head2,40);
      printf("List 1\n");
     
      print_list(head2);
     
      printf("List 2\n");
      print_list(head1);
      printf("after concatenation\n");
      struct Node* c=concate(&head2,head1);
      print_list(c);
     
    
    return 0;
   
}
