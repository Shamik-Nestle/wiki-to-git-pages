<br />
Given a Linked List, the task is to insert a new node in this given Linked List at the following positions: 

1. **At the front of the linked list-**
To insert a new node at the front, we create a new node and point its next reference to the current head of the linked list. Then, we update the head to be this new node. This operation is efficient because it only requires adjusting a few pointers.

<IMG  src="https://media.geeksforgeeks.org/wp-content/uploads/20240726182404/Insertion-at-the-Beginning-of-Singly-Linked-List.webp"  alt="Insertion-at-the-Beginning-of-Singly-Linked-List"/>

**Algorithm:**

Make the first node of Linked List linked to the new node
Remove the head from the original first node of Linked List
Make the new node as the Head of the Linked List.


**Code-**
```c++
// C++ Program to insert the node at the beginning of
// Linked List

#include <bits/stdc++.h>
using namespace std;

struct Node {

    int data;
    Node* next;

    Node(int new_data) {
        data = new_data;
        next = nullptr; 
    }
};

// Function to insert a new node at the beginning of the
// list
Node* insertAtFront(Node* head, int new_data) {
  
    // Create a new node with the given data
    Node* new_node = new Node(new_data);

    // Make the next of the new node point to the current
    // head
    new_node->next = head;

    // Return the new node as the new head of the list
    return new_node;
}

void printList(Node* head) {
  
    // Start from the head of the list
    Node* curr = head;

    // Traverse the list
    while (curr != nullptr) {
      
        // Print the current node's data
        cout << " " << curr->data;

        // Move to the next node
        curr = curr->next;
    }

    // Print a newline at the end
    cout << endl;
}

int main() {
  
    // Create the linked list 2->3->4->5
    Node* head = new Node(2);
    head->next = new Node(3);
    head->next->next = new Node(4);
    head->next->next->next = new Node(5);

    int data = 1;
    head = insertAtFront(head, data);
    printList(head);

    return 0;
}

```