# Experiment-22
Aim:
To study and implement Doubly Linked List.

Theory:
A doubly linked list is another implementation of linked structures defined as a collection of nodes in a linear order.
Each node consists of:
Data - the value or information contained in the node.
Two pointers:
Pointer to the previous node in the order (called as prev).
Pointer to the next node in the order (called as next).

Advantages of Doubly Linked Lists:
→ Bidirectional Traversal
→ Efficient Deletions
→ Efficient Insertions


Disadvantages of Doubly Linked Lists:
→ Complexity
→ Increased Memory Usage

CODE:-
```
#include <iostream>
using namespace std;

struct node 
{
    int data;        
    node* next;      
    node* prev;      
};

node* createnode(int value) 
{
    node* newnode = new node();  
    newnode->data = value;       
    newnode->next = nullptr;    
    newnode->prev = nullptr;   
    return newnode;
}


void insertdata(node*& head, int value) 
{

    node* newnode = createnode(value);
    if (head == nullptr) 
    {
        head = newnode;
    } 

    else 
    {
        node* temp = head;
        while (temp->next != nullptr) 
        {
            temp = temp->next;
        }

        temp->next = newnode;
        newnode->prev = temp;
    }
}


void displayfwd(node* head) 
{
    node* temp = head;
    cout << "Forward: ";

    while (temp != nullptr) 
    {
        cout << temp->data << "  ";
        temp = temp->next;
    }
}

void displayrev(node* head) 
{
    node* temp = head;

    if (temp == nullptr) 
    {
        return;
    }

    while (temp->next != nullptr) 
    {
        temp = temp->next;
    }
    cout << "Reverse: ";

    while (temp != nullptr) 
    {
        cout << temp->data << " ";
        temp = temp->prev;
    }
}

int main() 
{
    node* head = nullptr; 
    insertdata(head, 11);
    insertdata(head, 22);
    insertdata(head, 33);
    insertdata(head, 44);

    cout << "Doubly Linked List: "<<endl;
    displayfwd(head);
    cout<<endl;
    displayrev(head);

    return 0;
}
```

OUTPUT:-

![Ex 22 JPG](https://github.com/user-attachments/assets/c4342915-080d-45ea-a7d1-1a492f0e8175)


CONCLUSION- We will learn how to perform double linked list

