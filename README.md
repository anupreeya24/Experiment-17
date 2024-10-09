# Experiment-17

# Linked List

# Aim:
To study and implement linked list


### Theory of Linked Lists 

**1. Definition and Structure:**
A linked list is a linear data structure where elements, called nodes, are stored in a non-contiguous manner in memory. Each node consists of two parts:
- **Data**: Stores the value of the node.
- **Pointer/Reference**: Points to the next node in the sequence.

The last node’s pointer is typically set to null (or None), indicating the end of the list. Variants of linked lists include:
- **Singly Linked List**: Each node points to the next node.
- **Doubly Linked List**: Each node points to both the next and the previous nodes.
- **Circular Linked List**: The last node points back to the first node, forming a circle.

**2. Properties:**
- **Dynamic Size**: Unlike arrays, linked lists can grow or shrink in size during runtime without the need for reallocation.
- **Ease of Insertion/Deletion**: Nodes can be easily added or removed without shifting elements, which is advantageous in scenarios where frequent modifications are required.
- **Non-contiguous Memory Allocation**: Linked lists can utilize memory more flexibly as nodes are not stored in contiguous blocks.

**3. Advantages:**
- **Flexible Size**: Useful for applications where the size of the dataset is unpredictable.
- **Efficient Insertions/Deletions**: These operations can be performed in O(1) time if the position is known, making linked lists suitable for stack and queue implementations.
- **No Memory Waste**: Linked lists allocate memory as needed, avoiding the fixed-size limitations of arrays.

**4. Disadvantages:**
- **Memory Overhead**: Each node requires additional memory for the pointer/reference, which can lead to increased memory consumption, especially in large datasets.
- **Sequential Access**: Unlike arrays, linked lists do not support random access, resulting in O(n) time complexity for accessing an element by index.
- **Cache Performance**: Nodes are often scattered in memory, leading to poor cache locality and potentially lower performance in traversal operations.

Sure! Below is an algorithm for creating a linked list with basic operations like insertion and display, followed by the complete code in C++.

### Algorithm

1. **Define the Node Structure**: Create a class `link` that contains an integer `data` and a pointer to the next node.
2. **Insert a Node**: Write a function to insert a new node at the end of the linked list.
   - Create a new node with the given data.
   - If the list is empty, set the new node as the head.
   - Otherwise, traverse to the end of the list and link the new node.
3. **Display the List**: Write a function to traverse the linked list and print each node's data.
4. **Main Function**: In the main function, create the linked list, insert some nodes, and display the list.

### C++ Code

```cpp
#include<iostream>
using namespace std;
class link{
    public:
    int data;
    link* next;

    link(int num) {
        data = num;
        next = NULL;
    }
};
int main(){
    link* l1 = new link(6);
    cout<<l1->data<<" "<<l1->next;
}
```


### Algorithm

1. **Define the Node Structure**:
   - Create a class `link` that contains:
     - An integer `data` to store the node's value.
     - A pointer `next` to point to the next node in the list.
   - Implement a constructor to initialize `data` and set `next` to `NULL`.

2. **Insert Node at Head**:
   - Define a function `insert_head(link*& head, int data)`:
     - Create a new node using the provided `data`.
     - Set the `next` pointer of the new node to point to the current head.
     - Update the head to point to the new node.

3. **Display the Linked List**:
   - Define a function `disp(link* head)`:
     - Initialize a temporary pointer to the head.
     - Traverse the linked list while the current node is not `NULL`:
       - Print the `data` of the current node followed by an arrow (`->`).
       - Move to the next node.
     - Print `NULL` to indicate the end of the list.

4. **Main Function**:
   - Initialize a pointer `head` to `NULL` to represent an empty linked list.
   - Call `insert_head` to add nodes (e.g., 30, 32, 35) at the head of the list.
   - After each insertion, call `disp` to display the current state of the linked list.
  
   ```cpp
   #include <iostream>
using namespace std;

class link{
    public:
    int data ;
    
    link* next;

    link(int num){
        data= num;
        next= NULL;
    }
};

void insert_head(link* &head, int data){
    link* new_node = new link(data);
    new_node ->next =head;
    head = new_node;
}

void disp(link* head){
    link* temp = head;
    while(temp!=NULL){
        cout<<temp-> data<<"->";
        temp = temp->next; 
    }
    cout<<"NULL"<<endl;
}

int main(){
    link* head = NULL;
    insert_head (head,30);
    disp(head);

    insert_head(head, 32);
    disp(head);

    insert_head(head, 35);
    disp(head); 
} 
```


**5. Conclusion:**
Linked lists are a foundational data structure in computer science, offering unique properties that suit various scenarios, especially where dynamic size and efficient insertions/deletions are required. However, the trade-offs in memory usage and access speed must be carefully considered when choosing between linked lists and other data structures, such as arrays. Understanding the theory and mechanics of linked lists is essential for effective problem-solving and algorithm design in DSA.
