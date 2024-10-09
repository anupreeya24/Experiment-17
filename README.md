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

**5. Conclusion:**
Linked lists are a foundational data structure in computer science, offering unique properties that suit various scenarios, especially where dynamic size and efficient insertions/deletions are required. However, the trade-offs in memory usage and access speed must be carefully considered when choosing between linked lists and other data structures, such as arrays. Understanding the theory and mechanics of linked lists is essential for effective problem-solving and algorithm design in DSA.
