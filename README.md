# PYTHON PROGRAMMING MODULE - 11
## NAME : PREETHI D
## REGISTER NUMBER : 212224040250
# EX 01- Doubly Linked List: Insert Elements at the End of a Doubly Linked List

This Python program demonstrates the creation and manipulation of a **Doubly Linked List** where elements can be inserted at the **end** of the list. The program also provides a method to traverse the list and display the elements.

---

##  Aim

To write a Python program that:
- Implements a **Doubly Linked List**.
- Allows insertion of elements at the end of the list.
- Provides functionality to traverse the list and display its elements.

---

##  Algorithm

1. **Step 1:** Define a class `Node` to represent each node in the doubly linked list with attributes:
   - `item` for storing the data of the node.
   - `nref` for storing the reference to the next node.
   - `pref` for storing the reference to the previous node.

2. **Step 2:** Define a class `DoublyLinkedList` with:
   - `start_node` to point to the first node of the list.

3. **Step 3:** Define methods in the `DoublyLinkedList` class:
   - `insert_in_emptylist(data)` to insert an element when the list is empty.
   - `insert_at_end(data)` to insert elements at the end of the list.
   - `traverse_list()` to traverse the list and print the elements.

4. **Step 4:** Create an instance of `DoublyLinkedList` and use the `insert_at_end()` method to insert elements into the list.

5. **Step 5:** Use the `traverse_list()` method to print the elements of the list.

---

##  Program
```
class Node:
    def __init__(self, data):
        self.item = data
        self.nref = None
        self.pref = None

class DoublyLinkedList:
    def __init__(self):
        self.start_node = None

    def insert_in_emptylist(self, data):
        new_node = Node(data)
        self.start_node = new_node

    def insert_at_end(self, data):
        if self.start_node is None:
            self.insert_in_emptylist(data)
            return
        new_node = Node(data)
        n = self.start_node
        while n.nref is not None:
            n = n.nref
        n.nref = new_node
        new_node.pref = n

    def traverse_list(self):
        if self.start_node is None:
            print("List is empty")
            return
        n = self.start_node
        while n is not None:
            print(n.item, end=' ')
            n = n.nref
        print()

# Example usage
dll = DoublyLinkedList()
dll.insert_at_end(10)
dll.insert_at_end(20)
dll.insert_at_end(30)
dll.traverse_list()

```

## Sample Output
![image](https://github.com/user-attachments/assets/0b51f9be-2cb3-4e1f-9695-e3c5a22e85bc)

## Result
Therefore the given Python Program has been executed successfully and the output has been verified.

# EX 02- Doubly Linked List: Search an Element

This Python program demonstrates the implementation of a **Doubly Linked List** where you can insert elements at both the beginning and the end of the list. Additionally, it allows you to search for a specific element in the list.

---

##  Aim

To write a Python program that:
- Implements a **Doubly Linked List** with functions to insert elements at the beginning and the end of the list.
- Implements a search function to check if a given element exists in the list.

---

##  Algorithm

1. **Step 1:** Define a class `Nodeq` with:
   - `data` to store the node's value.
   - `next` to store the reference to the next node.
   - `prev` to store the reference to the previous node.

2. **Step 2:** Define a class `DoublyLinkedList` with:
   - `head` to point to the first node.

3. **Step 3:** In the `DoublyLinkedList` class, define methods:
   - `insert_beginning(data)` to insert a node at the beginning.
   - `insert_end(data)` to insert a node at the end.
   - `search(data)` to search for an element in the list.

4. **Step 4:** Create an instance of `DoublyLinkedList`.
   - Insert elements at the beginning and end.
   - Search for specific elements.

---

## Program
```
class Nodeq:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None

class DoublyLinkedList:
    def __init__(self):
        self.head = None

    def insert_beginning(self, data):
        new_node = Nodeq(data)
        if self.head is None:
            self.head = new_node
            return
        new_node.next = self.head
        self.head.prev = new_node
        self.head = new_node

    def insert_end(self, data):
        new_node = Nodeq(data)
        if self.head is None:
            self.head = new_node
            return
        n = self.head
        while n.next:
            n = n.next
        n.next = new_node
        new_node.prev = n

    def search(self, data):
        n = self.head
        while n:
            if n.data == data:
                return True
            n = n.next
        return False

# Example usage
dll = DoublyLinkedList()
dll.insert_beginning(10)
dll.insert_end(20)
dll.insert_beginning(5)
dll.insert_end(30)

print("Search 20:", dll.search(20))  # True
print("Search 40:", dll.search(40))  # False

```
## Sample Output
![image](https://github.com/user-attachments/assets/98d64d5b-097a-4379-8b0f-776c14ba148a)
![image](https://github.com/user-attachments/assets/ec862d64-a29e-4220-9fbb-bb8507ad5201)

## Result
Therefore the given Python Program has been executed successfully and the output has been verified.
