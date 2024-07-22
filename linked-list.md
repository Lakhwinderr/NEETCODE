To help you study and understand linked lists in JavaScript, here are some key concepts, basic operations, and approaches you can use to solve the provided questions:

### Key Concepts

1. **Linked List Structure**: A linked list is a linear data structure where each element (node) contains a value and a pointer (reference) to the next node in the sequence. There are different types of linked lists: singly linked lists, doubly linked lists, and circular linked lists.

2. **Node Class**: In JavaScript, you typically define a `Node` class to represent each element in the linked list. Each node has at least two properties: `value` (or `data`) and `next`.

3. **Linked List Class**: You can define a `LinkedList` class to manage the nodes, which includes methods to add, remove, and search for elements.

### Basic Operations

1. **Traversal**: Going through each node starting from the head until you reach the end (where `next` is `null`).

2. **Insertion**: Adding a node at the beginning, end, or at a specific position.

3. **Deletion**: Removing a node from the beginning, end, or a specific position.

4. **Searching**: Finding a node with a specific value.

### Study Materials

1. **Node Class Example**:
   ```javascript
   class ListNode {
       constructor(value = 0, next = null) {
           this.value = value;
           this.next = next;
       }
   }
   ```

2. **Singly Linked List Class Example**:
   ```javascript
   class LinkedList {
       constructor() {
           this.head = null;
       }

       append(value) {
           if (this.head === null) {
               this.head = new ListNode(value);
               return;
           }

           let current = this.head;
           while (current.next !== null) {
               current = current.next;
           }
           current.next = new ListNode(value);
       }

       prepend(value) {
           this.head = new ListNode(value, this.head);
       }

       // More methods for deletion, searching, etc.
   }
   ```

### Approaches for Specific Questions

1. **Reverse a Singly Linked List**:
   - Use three pointers: `prev`, `current`, and `next`.
   - Iterate through the list, reversing the direction of each node’s `next` pointer.

2. **Merge Two Sorted Linked Lists**:
   - Use a dummy node to build the new list.
   - Compare the nodes of both lists one by one and link the smaller node to the merged list.

3. **Reorder List**:
   - Use a slow and fast pointer to find the middle of the list.
   - Reverse the second half of the list.
   - Merge the two halves by alternating nodes.

4. **Remove N-th Node from End**:
   - Use two pointers with a gap of `n` nodes.
   - Move both pointers until the end of the list is reached, then remove the targeted node.

5. **Deep Copy a List with Random Pointers**:
   - Use a hash map to create a mapping from the original nodes to the new nodes.
   - Traverse the original list to create new nodes and update the `next` and `random` pointers.

6. **Add Two Numbers (Reverse Order)**:
   - Traverse both lists and simulate the addition of each pair of nodes, handling carry-over.

7. **Detect Cycle in a Linked List**:
   - Use a slow and fast pointer.
   - If they meet, there is a cycle; otherwise, the list is acyclic.

8. **Find the Duplicate Number**:
   - Use the Floyd’s Tortoise and Hare (Cycle Detection) algorithm.

9. **LRU Cache**:
   - Use a combination of a doubly linked list and a hash map for O(1) operations.

10. **Merge k Sorted Lists**:
   - Use a min-heap (priority queue) to efficiently merge k sorted lists.

11. **Reverse Nodes in k-Group**:
   - Reverse every group of k nodes using a helper function to reverse a sublist.

### Resources

1. **MDN Web Docs on JavaScript Classes**: [Classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)
2. **LeetCode Linked List Problems**: LeetCode has a variety of problems related to linked lists which can help you practice.
3. **GeeksforGeeks Linked List Tutorials**: [GeeksforGeeks Linked List](https://www.geeksforgeeks.org/data-structures/linked-list/)

By understanding these concepts and practicing with the provided examples, you will be well-prepared to solve the linked list problems you've mentioned.