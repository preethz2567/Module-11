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
# EX 03- Singly Linked List : Find the Middle Node of a Singly Linked List Using Recursion

This Python program demonstrates how to find the middle node of a singly linked list using recursion. The program calculates the middle element by utilizing two pointers, with one pointer moving one step at a time (slow) and the other moving two steps at a time (fast). When the fast pointer reaches the end of the list, the slow pointer will be at the middle node.

##  Aim

To write a Python program that:
- Creates a singly linked list.
- Uses recursion to find the middle node of the list.
- In case of an even number of nodes, it returns the second middle element.

##  Algorithm

1. **Node Class**: 
   - Define a `Node` class to represent each node in the singly linked list. Each node has two attributes: `data` and `next`.
   
2. **LinkedList Class**:
   - Define a `LinkedList` class that manages the linked list with methods to:
     - `append(data)`: Add a new node to the end of the list.
     - `get_middle_recursive(slow, fast)`: A recursive helper function to find the middle node using two pointers (slow and fast).
     - `find_middle()`: A method to call the recursive function and return the middle node's data.

3. **Input**:
   - First, the program reads an integer `n`, representing the number of elements in the linked list.
   - Then, it reads `n` space-separated integers to form the linked list.

4. **Recursive Middle Finding**:
   - The `get_middle_recursive` method uses two pointers to traverse the list:
     - The `slow` pointer moves one step at a time.
     - The `fast` pointer moves two steps at a time.
   - When the `fast` pointer reaches the end, the `slow` pointer will be at the middle node.

5. **Output**:
   - The program prints the middle element. If the list has an even number of nodes, it returns the second middle element.

---

##  Program
```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        curr = self.head
        while curr.next:
            curr = curr.next
        curr.next = new_node

    def get_middle_recursive(self, slow, fast):
        if fast is None or fast.next is None:
            return slow.data
        return self.get_middle_recursive(slow.next, fast.next.next)

    def find_middle(self):
        if not self.head:
            return None
        return self.get_middle_recursive(self.head, self.head)

# Input reading and execution
n = int(input())
elements = list(map(int, input().split()))

ll = LinkedList()
for elem in elements:
    ll.append(elem)

print(ll.find_middle())

```

## Sample Input & Output
![image](https://github.com/user-attachments/assets/2da7ed2b-ae9d-4c51-97e9-6450125c998d)

## Result

Therefore the given Python Program has been executed successfully and the output has been verified.
# EX04- Singly Linked List-To Search an Element in a Linked List

This project contains a simple implementation of a **singly linked list** in Python, allowing insertion and searching of elements.

---

##  Aim

To write a Python program to search for a given element in a singly linked list using object-oriented programming principles.

---

##  Algorithm

1. **Define a Node class** with `data` and `next` attributes.
2. **Define a LinkedList class** with:
   - A `head` pointer initialized to `None`.
   - A `push()` method to add elements at the beginning.
   - A `search()` method to check whether a given value exists.
3. Create a `LinkedList` instance.
4. Insert the elements **10, 30, 11, 21, 14** using `push()` (which results in reverse order).
5. Read an integer input from the user.
6. Use `search()` to check if the element exists in the list.
7. Output **"Yes"** if found, else **"No"**.

---

##  Program

```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def push(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node

    def search(self, key):
        current = self.head
        while current:
            if current.data == key:
                return True
            current = current.next
        return False

ll = LinkedList()
for value in [10, 30, 11, 21, 14]:
    ll.push(value)

key = int(input())
print("Yes" if ll.search(key) else "No")

```
## Sample Output
![image](https://github.com/user-attachments/assets/5a8c5ee0-4fc3-4078-b5ce-c2284e5de4c1)

## Result
Therefore the given Python Program has been executed successfully and the output has been verified.

# EX 05- Singly Linked List: Add Element at the Start

This Python program demonstrates the implementation of a **Singly Linked List** where a new element can be added at the **start** of the list.

---

## Aim

To write a Python program that adds a **new element** at the **start** of a singly linked list. The program implements a `push_front` method that inserts an element at the front of the list, followed by a method to print the list.

---

##  Algorithm

1. **Step 1:** Define a class `Node` with:
   - `data` to store the node's value.
   - `next` to store the reference to the next node.
   
2. **Step 2:** Define a class `LinkedList` with:
   - `head` to point to the first node.
   
3. **Step 3:** In the `LinkedList` class, define a method `push_front(newElement)`:
   - Create a new node with `newElement`.
   - Set the new node's next pointer to the current head node.
   - Set the head to the new node.

4. **Step 4:** Define a method `PrintList()` to display the list:
   - Print the elements of the list or display "The list is empty." if the list is empty.

5. **Step 5:** Instantiate a `LinkedList` object, `MyList`, and add elements at the start using the `push_front()` method.

6. **Step 6:** Call the `PrintList()` method to display the list.

---

## Program
```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def push_front(self, newElement):
        new_node = Node(newElement)
        new_node.next = self.head
        self.head = new_node

    def PrintList(self):
        if self.head is None:
            print("The list is empty.")
            return
        current = self.head
        while current:
            print(current.data, end=" ")
            current = current.next
        print()


MyList = LinkedList()
MyList.push_front(10)
MyList.push_front(20)
MyList.push_front(30)

MyList.PrintList()

```
## Sample Output
![image](https://github.com/user-attachments/assets/5a8d087f-3efc-4f44-9eec-967f82748367)

## Result
Therefore the given Python Program has been executed successfully and the output has been verified.
