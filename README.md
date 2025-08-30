# module-12




EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST. Aim: To write a C program to display stack elements using linked list.

Algorithm:

Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
Declare a global variable head representing the starting node of the linked list.
Define a function display to print the elements of the linked list.
Declare a pointer p and initialize it with the head of the linked list.
Use a while loop to traverse the linked list:
Print the data of the current node.
Move to the next node using the next pointer.
Program:

#include <stdio.h>
#include <stdlib.h>

// Structure for stack node
struct Node {
    int data;
    struct Node* next;
};

// Global top pointer
struct Node* top = NULL;

// Function to push element into stack
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = top;
    top = newNode;
}

// Function to display stack elements
void display() {
    struct Node* p = top;

    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements are:\n");
    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    // Push some elements
    push(10);
    push(20);
    push(30);
    push(40);

    // Display stack
    display();

    return 0;
}


Output:

<img width="1628" height="702" alt="image" src="https://github.com/user-attachments/assets/3bd43335-b962-49ad-a119-212827b60c9c" />


Result: Thus, the program to display stack elements using linked list is verified successfully.

EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST. Aim: To write a C program to pop an element from the given stack using liked list.

Algorithm:

Check for Empty Stack
If head is equal to NULL, Print "Stack is empty."
Else Proceed to the next step.
Set head to point to the next node in the stack.
Program:
#include <stdio.h>
#include <stdlib.h>

// Structure for stack node
struct Node {
    int data;
    struct Node* next;
};

// Global top pointer
struct Node* top = NULL;

// Function to push element into stack
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = top;
    top = newNode;
    printf("%d pushed to stack\n", value);
}

// Function to pop element from stack
void pop() {
    if (top == NULL) {
        printf("Stack is empty. Cannot pop.\n");
    } else {
        struct Node* temp = top;
        printf("Popped element: %d\n", temp->data);
        top = top->next;
        free(temp);
    }
}

// Function to display stack elements
void display() {
    struct Node* p = top;
    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Stack elements are:\n");
    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    // Push some elements
    push(10);
    push(20);
    push(30);

    // Display stack
    display();

    // Pop one element
    pop();

    // Display stack again
    display();

    return 0;
}


Output:

<img width="1664" height="633" alt="image" src="https://github.com/user-attachments/assets/16c7a068-2c0a-48b3-bf40-07ad55c7a311" />


Result: Thus, the program to pop an element from the given stack using liked list is verified successfully.

EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST. Aim: To write a C program to display queue elements using linked list. Algorithm:

Check if Queue is Empty
Display Queue Elements
Print the data of the current node pointed to by front
Update front to point to the next node.
End the display function.
Program:

#include <stdio.h>
#include <stdlib.h>

// Structure for queue node
struct Node {
    int data;
    struct Node* next;
};

// Global pointers for front and rear
struct Node* front = NULL;
struct Node* rear = NULL;

// Function to enqueue (insert) element into queue
void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (rear == NULL) {  // Queue is empty
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
    printf("%d enqueued to queue\n", value);
}

// Function to display queue elements
void display() {
    struct Node* temp = front;
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements are:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    // Enqueue some elements
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    // Display queue
    display();

    return 0;
}


Output:

<img width="1615" height="692" alt="image" src="https://github.com/user-attachments/assets/985f266a-b43e-4be4-8b25-b8c42eafef13" />


Result: Thus, the program to display queue elements using linked list is verified successfully.

EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim: To write a C program to insert elements in queue using linked list

Algorithm:

Allocate Memory for New Node
Set Data and Next Pointer
Check if Queue is Empty
Set both front and rear to point to the new node p.
Set the next pointer of the current rear to point to the new node p.
End of Enqueue Operation
Program:

// Function to enqueue (insert) element into queue
void enqueue(int value) {
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    p->data = value;
    p->next = NULL;

    // If queue is empty
    if (front == NULL && rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
    printf("%d enqueued to queue\n", value);
}

Output:

<img width="1615" height="692" alt="image" src="https://github.com/user-attachments/assets/671e7741-25f0-4897-acd2-a1f429014b1a" />


Result: Thus, the program to insert elements in queue using linked list is verified successfully.

EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.

Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

Check if the queue is empty: o If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
Access the front element: o If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).
Program:

#include <stdio.h>
#include <stdlib.h>

// Structure for queue node
struct Node {
    int data;
    struct Node* next;
};

// Global pointers for front and rear
struct Node* front = NULL;
struct Node* rear = NULL;

// Function to enqueue (insert) element into queue
void enqueue(int value) {
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    p->data = value;
    p->next = NULL;

    if (front == NULL && rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
    printf("%d enqueued to queue\n", value);
}

// Function to peek (get front element)
int peek() {
    if (front == NULL) {
        printf("Queue is empty. Nothing to peek.\n");
        return -1; // return error code
    } else {
        return front->data;
    }
}

// Function to display queue elements
void display() {
    struct Node* temp = front;
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements are:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();

    int frontElement = peek();
    if (frontElement != -1) {
        printf("Peek element of queue = %d\n", frontElement);
    }

    return 0;
}


Output:

<img width="1653" height="662" alt="image" src="https://github.com/user-attachments/assets/977386e1-7df8-43c1-b71f-1d089eea5db2" />


Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
