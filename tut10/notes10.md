## Linked List in Java

A **linked list** is a linear val structure where each element is stored in a **node**. Each node contains:

```java
val
next
```

Unlike arrays, linked lists do not store elements in continuous memory.

---

## Singly Linked List

Each node points only to the **next** node.

```java
class Node {
    int val;
    Node next;

    Node(int val) {
        this.val = val;
        this.next = null;
    }
}
```

### Basic Structure

```java
class LinkedList {
    Node head;

    void insertAtEnd(int val) {
        Node newNode = new Node(val);

        if (head == null) {
            head = newNode;
            return;
        }

        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }

        temp.next = newNode;
    }

    void display() {
        Node temp = head;

        while (temp != null) {
            System.out.print(temp.val + " -> ");
            temp = temp.next;
        }

        System.out.println("null");
    }
}
```

### Example

```java
public class Main {
    public static void main(String[] args) {
        LinkedList list = new LinkedList();

        list.insertAtEnd(10);
        list.insertAtEnd(20);
        list.insertAtEnd(30);

        list.display();
    }
}
```

Output:

```java
10 -> 20 -> 30 -> null
```

---

## Important Functions in Singly Linked List

### Insert at Beginning

```java
void insertAtBeginning(int val) {
    Node newNode = new Node(val);
    newNode.next = head;
    head = newNode;
}
```

### Delete by Value

```java
void delete(int key) {
    if (head == null) return;

    if (head.val == key) {
        head = head.next;
        return;
    }

    Node temp = head;

    while (temp.next != null && temp.next.val != key) {
        temp = temp.next;
    }

    if (temp.next != null) {
        temp.next = temp.next.next;
    }
}
```

### Search

```java
boolean search(int key) {
    Node temp = head;

    while (temp != null) {
        if (temp.val == key) return true;
        temp = temp.next;
    }

    return false;
}
```

---

# Doubly Linked List in Java

A **doubly linked list** has nodes that point to both:

```java
previous node
next node
```

Each node contains:

```java
val
prev
next
```

---

## Node Class

```java
class DNode {
    int val;
    DNode prev;
    DNode next;

    DNode(int val) {
        this.val = val;
        this.prev = null;
        this.next = null;
    }
}
```

---

## Doubly Linked List Structure

```java
class DoublyLinkedList {
    DNode head;

    void insertAtEnd(int val) {
        DNode newNode = new DNode(val);

        if (head == null) {
            head = newNode;
            return;
        }

        DNode temp = head;

        while (temp.next != null) {
            temp = temp.next;
        }

        temp.next = newNode;
        newNode.prev = temp;
    }

    void displayForward() {
        DNode temp = head;

        while (temp != null) {
            System.out.print(temp.val + " <-> ");
            temp = temp.next;
        }

        System.out.println("null");
    }
}
```

### Example

```java
public class Main {
    public static void main(String[] args) {
        DoublyLinkedList list = new DoublyLinkedList();

        list.insertAtEnd(5);
        list.insertAtEnd(15);
        list.insertAtEnd(25);

        list.displayForward();
    }
}
```

Output:

```java
5 <-> 15 <-> 25 <-> null
```

---

## Important Functions in Doubly Linked List

### Insert at Beginning

```java
void insertAtBeginning(int val) {
    DNode newNode = new DNode(val);

    if (head != null) {
        head.prev = newNode;
    }

    newNode.next = head;
    head = newNode;
}
```

### Delete by Value

```java
void delete(int key) {
    if (head == null) return;

    DNode temp = head;

    while (temp != null && temp.val != key) {
        temp = temp.next;
    }

    if (temp == null) return;

    if (temp.prev != null) {
        temp.prev.next = temp.next;
    } else {
        head = temp.next;
    }

    if (temp.next != null) {
        temp.next.prev = temp.prev;
    }
}
```

### Display Backward

```java
void displayBackward() {
    if (head == null) return;

    DNode temp = head;

    while (temp.next != null) {
        temp = temp.next;
    }

    while (temp != null) {
        System.out.print(temp.val + " <-> ");
        temp = temp.prev;
    }

    System.out.println("null");
}
```

---

# Singly vs Doubly Linked List

| Feature     | Singly Linked List | Doubly Linked List   |
| ----------- | ------------------ | -------------------- |
| Direction   | Forward only       | Forward and backward |
| Node fields | val, next         | val, prev, next     |
| Memory      | Less               | More                 |
| Deletion    | Harder             | Easier               |
| Traversal   | One direction      | Two directions       |

---

# Things to Beware About

## 1. Null Pointer Errors

Always check if `head == null`.

```java
if (head == null) return;
```

## 2. Losing References

Wrong:

```java
head = head.next;
newNode.next = head;
```

Correct:

```java
newNode.next = head;
head = newNode;
```

## 3. Infinite Loops

Always move the pointer:

```java
temp = temp.next;
```

## 4. Updating Both Links in Doubly Linked List

For doubly linked lists, update both:

```java
prev.next
next.prev
```

## 5. Edge Cases

Always test:

```java
empty list
one-node list
delete head
delete tail
insert at beginning
insert at end
search missing value
```

---

# Time Complexity

| Operation           | Time |
| ------------------- | ---- |
| Insert at beginning | O(1) |
| Insert at end       | O(n) |
| Search              | O(n) |
| Delete by value     | O(n) |
| Display             | O(n) |

If you maintain a `tail` pointer, insertion at end becomes:

```java
O(1)
```
