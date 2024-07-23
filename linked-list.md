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

   -use dummy node in above questions

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

### Floyd’s Tortoise and Hare (Cycle Detection) Algorithm

#### Overview:
Floyd’s Tortoise and Hare algorithm is a pointer algorithm used to detect cycles in a linked list. It uses two pointers that move at different speeds to determine whether a cycle exists.

#### Key Concepts:
1. **Slow Pointer**: Moves one step at a time.
2. **Fast Pointer**: Moves two steps at a time.

#### Steps:

1. **Initialization**:
   - Initialize `slow` and `fast` pointers to the head of the linked list.

2. **Traversal**:
   - Move the `slow` pointer by one step.
   - Move the `fast` pointer by two steps.

3. **Cycle Detection**:
   - If `fast` becomes `null` or `fast.next` becomes `null`, it means there is no cycle in the list, so return `false`.
   - If `slow` and `fast` pointers meet at any point, it indicates there is a cycle in the list, so return `true`.

#### Example Code:

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} head
 * @return {boolean}
 */
var hasCycle = function(head) {
    if (!head) {
        return false;  // Return false for an empty list
    }

    let slow = head;
    let fast = head;

    while (fast !== null && fast.next !== null) {
        fast = fast.next.next;
        slow = slow.next;
        if (fast === slow) {
            return true;  // Cycle detected
        }
    }
    
    return false;  // No cycle detected
};
```

#### Example Usage:

```javascript
// Test case: empty list
console.log(hasCycle(null));  // Expected output: false

// Test case: no cycle
let head = new ListNode(1);
head.next = new ListNode(2);
head.next.next = new ListNode(3);
console.log(hasCycle(head));  // Expected output: false

// Test case: cycle exists
let cycleHead = new ListNode(1);
cycleHead.next = new ListNode(2);
cycleHead.next.next = new ListNode(3);
cycleHead.next.next.next = cycleHead.next;  // Creates a cycle
console.log(hasCycle(cycleHead));  // Expected output: true
```

#### Key Points:

- **Time Complexity**: O(n), where n is the number of nodes in the linked list.
- **Space Complexity**: O(1), constant space usage since no additional data structures are used.
- **Use Cases**: Cycle detection in linked lists, finding loops in data structures.

This algorithm is efficient and commonly used for detecting cycles in linked lists due to its simplicity and low space complexity.

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