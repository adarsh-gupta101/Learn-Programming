[![Adarsh gupta](https://miro.medium.com/fit/c/96/96/1*t-ya5MdH4ALyrJ-TMnWneQ.png)

Adarsh gupta
9 Min read

Implementation of Data Structures in JavaScript
===============================================

How to Create Lists, Dictionaries, Stacks, Linked Lists, Queues, and more in JS
-------------------------------------------------------------------------------

JavaScript, like many other programming languages, provides built-in support for common data structures such as arrays, lists, and dictionaries. In this blog post, we will discuss how to implement some of the most common data structures in JavaScript.

Arrays
------

Arrays are one of the simplest and most commonly used data structures. In JavaScript, arrays are zero-indexed and can hold elements of any data type. To create an array, you can use the `Array` constructor or the array literal syntax, which is more concise and easier to read.

```
// Using the Array constructor  
const numbers = new Array(1, 2, 3, 4, 5);  
  
// Using the array literal syntax  
const colors = \['red', 'green', 'blue'\];
```

Once you have created an array, you can access and modify its elements using the square bracket notation.

```
// Accessing elements  
console.log(colors\[0\]);  // Output: 'red'  
console.log(colors\[1\]);  // Output: 'green'  
  
// Modifying elements  
colors\[2\] = 'orange';  
console.log(colors\[2\]);  // Output: 'orange'  
  
// Adding elements  
colors.push('purple');  
console.log(colors);  // Output: \['red', 'green', 'orange', 'purple'\]
```

Lists
-----

Lists are similar to arrays, but they are typically used to store a variable number of elements and provide more flexibility in terms of inserting and removing elements. In JavaScript, you can implement a list using an array and some additional methods to manipulate the elements.

```
// List constructor  
function List() {  
  this.items = \[\];  
  
  // Methods to add, remove, and find elements  
  this.add = function(item) {  
    this.items.push(item);  
  };  
  this.remove = function(item) {  
    const index = this.items.indexOf(item);  
    if (index !== -1) {  
      this.items.splice(index, 1);  
    }  
  };  
  this.find = function(item) {  
    return this.items.indexOf(item);  
  };  
}  
  
// Creating a list and adding some elements  
const fruits = new List();  
fruits.add('apple');  
fruits.add('banana');  
fruits.add('cherry');  
  
// Removing an element  
fruits.remove('banana');  
  
// Finding an element  
const index = fruits.find('cherry');  
console.log(index);  // Output: 1
```

Dictionaries
------------

A dictionary is a data structure that maps keys to values. In JavaScript, you can implement a dictionary using an object and some additional methods to manipulate the key-value pairs

```
// Dictionary constructor  
function Dictionary() {  
  this.items = {};  
  
  // Methods to add, remove, and find elements  
  this.add = function(key, value) {  
    this.items\[key\] = value;  
  };  
  this.remove = function(key) {  
    if (this.has(key)) {  
      delete this.items\[key\];  
      return true;  
    }  
    return false;  
  };  
  this.has = function(key) {  
    return key in this.items;
```

Stack
-----

A stack is a data structure that operates on a last-in-first-out (LIFO) basis. In other words, elements are added to the top of the stack and removed from the top of the stack. This allows for fast insertion and deletion of elements.

In JavaScript, you can implement a stack using an array and some additional methods to push and pop elements.

```
// Stack constructor  
function Stack() {  
  this.items = \[\];  
  
  // Methods to push and pop elements  
  this.push = function(item) {  
    this.items.push(item);  
  };  
  this.pop = function() {  
    if (this.items.length) {  
      return this.items.pop();  
    }  
    return null;  
  };  
}  
  
// Creating a stack and pushing some elements  
const stack = new Stack();  
stack.push(1);  
stack.push(2);  
stack.push(3);  
  
// Popping an element  
const popped = stack.pop();  
console.log(popped);  // Output: 3  
console.log(stack.items);  // Output: \[1, 2\]
```

Linked List
-----------

A linked list is a data structure that consists of a group of nodes that together represent a sequence. In a linked list, each node contains a value and a reference (link) to the next node in the sequence.

In JavaScript, you can implement a linked list using an object to represent each node and a class to represent the linked list.

```
// Node class  
class Node {  
  constructor(value) {  
    this.value = value;  
    this.next = null;  
  }  
}  
  
// LinkedList class  
class LinkedList {  
  constructor() {  
    this.head = null;  
    this.tail = null;  
    this.length = 0;  
  }  
  
  // Methods to add, remove, and find elements  
  add(value) {  
    const node = new Node(value);  
    if (!this.head) {  
      this.head = node;  
      this.tail = node;  
    } else {  
      this.tail.next = node;  
      this.tail = node;  
    }  
    this.length++;  
    return this;  
  }  
  remove(value) {  
    if (!this.head) {  
      return null;  
    }  
  
    let current = this.head;  
    let previous = null;  
  
    while (current) {  
      if (current.value === value) {  
        if (previous) {  
          previous.next = current.next;  
          if (current.next === null) {  
            this.tail = previous;  
          }  
        } else {  
          this.head = current.next;  
          if (this.head === null) {  
            this.tail = null;  
          }  
        }  
        this.length--;  
        return current;  
      }  
      previous = current;  
      current = current.next;  
    }  
    return null;  
  }  
  find(value) {  
    if (!this.head) {  
      return null;  
    }  
  
    let current = this.head;  
  
    while (current) {  
      if (current.value === value) {  
        return current;  
      }  
      current = current.next;  
    }  
    return null;  
  }  
}  
  
// Creating a linked list and adding some elements  
const list = new LinkedList();  
list.add(1);  
list.add(2);  
list.add(3);  
  
// Removing an element  
list.remove(2);  
  
// Finding an element  
const node = list.find(3);  
console.log(node);  // Output: Node { value: 3, next: null }
```

Queue
-----

A queue is a data structure that operates on a first-in-first-out (FIFO) basis. In other words, elements are added to the end of the queue and removed from the front of the queue. This allows for fast insertion and deletion of elements.

In JavaScript, you can implement a queue using an array and some additional methods to enqueue and dequeue elements.

```
// Queue constructor  
function Queue() {  
  this.items = \[\];  
  
  // Methods to enqueue and dequeue elements  
  this.enqueue = function(item) {  
    this.items.push(item);  
  };  
  this.dequeue = function() {  
    if (this.items.length) {  
      return this.items.shift();  
    }  
    return null;  
  };  
}  
  
// Creating a queue and enqueueing some elements  
const queue = new Queue();  
queue.enqueue(1);  
queue.enqueue(2);  
queue.enqueue(3);  
  
// Dequeueing an element  
const dequeued = queue.dequeue();  
console.log(dequeued);  // Output: 1  
console.log(queue.items);  // Output: \[2, 3\]
```

Binary Tree
-----------

A binary tree is a data structure that consists of a hierarchy of nodes. Each node has at most two children, which are referred to as the left child and the right child. The topmost node in the tree is called the root node.

In JavaScript, you can implement a binary tree using an object to represent each node and a class to represent the tree.

```
// Node class  
class Node {  
  constructor(value) {  
    this.value = value;  
    this.left = null;  
    this.right = null;  
  }  
}  
  
// BinaryTree class  
class BinaryTree {  
  constructor() {  
    this.root = null;  
  }  
  
  // Method to insert a new node in the tree  
  insert(value) {  
    const newNode = new Node(value);  
    if (!this.root) {  
      this.root = newNode;  
      return this;  
    }  
    let current = this.root;  
    while (true) {  
      if (value === current.value) {  
        return undefined;  
      }  
      if (value < current.value) {  
        if (current.left === null) {  
          current.left = newNode;  
          return this;  
        }  
        current = current.left;  
      } else {  
        if (current.right === null) {  
          current.right = newNode;  
          return this;  
        }  
        current = current.right;  
      }  
    }  
  }  
  
  // Method to find a node with a specific value  
  find(value) {  
    if (!this.root) {  
      return undefined;  
    }  
    let current = this.root;  
    let found = false;  
    while (current && !found) {  
      if (value < current.value) {  
        current = current.left;  
      } else if (value > current.value) {  
        current = current.right;  
      } else {  
        found = true;  
      }  
    }  
    if (!found) {  
      return undefined;  
    }  
    return current;  
  }  
}  
  
// Creating a binary tree and inserting some nodes  
const tree = new BinaryTree();  
tree.insert(10);  
tree.insert(6);  
tree.insert(15);  
tree.insert(3);  
tree.insert(8);  
tree.insert(20);  
  
// Finding a node in the tree  
const node = tree.find(15);  
console.log(node);  // Output: Node { value: 15, left: null, right: null }
```

Graph
-----

A graph is a data structure that consists of a finite set of nodes (or vertices) and a set of edges connecting the nodes. Each edge has a weight, which represents the distance or cost between two nodes.

In JavaScript, you can implement a graph using an object to represent each node and an adjacency list to represent the edges. An adjacency list is an array of linked lists, where each linked list stores the neighbors (or adjacent nodes) of a specific node.

```
// Graph constructor  
function Graph() {  
  this.nodes = {};  
  
  // Method to add a new node to the graph  
  this.addNode = function(node) {  
    this.nodes\[node\] = this.nodes\[node\] || \[\];  
  };  
  
  // Method to add a new edge to the graph  
  this.addEdge = function(node1, node2, weight) {  
    this.nodes\[node1\].push({ node: node2, weight });  
    this.nodes\[node2\].push({ node: node1, weight });  
  };  
}  
  
// Creating a graph and adding some nodes and edges  
const graph = new Graph();  
graph.addNode('A');  
graph.addNode('B');  
graph.addNode('C');  
graph.addEdge('A', 'B', 4);  
graph.addEdge('A', 'C', 2);  
graph.addEdge('B', 'C', 3);  
  
console.log(graph.nodes);  
// Output:  
// {  
//   A: \[{ node: 'B', weight: 4 }, { node: 'C', weight: 2 }\],  
//   B: \[{ node: 'A', weight: 4 }, { node: 'C', weight: 3 }\],  
//   C: \[{ node: 'A', weight: 2 }, { node: 'B', weight: 3 }\]  
// }
```

A graph is a data structure that consists of a finite set of nodes (or vertices) and a set of edges connecting the nodes. Each edge has a weight, which represents the distance or cost between two nodes.

In JavaScript, you can implement a graph using an object to represent each node and an adjacency list to represent the edges. An adjacency list is an array of linked lists, where each linked list stores the neighbors (or adjacent nodes) of a specific node.

```
// Graph constructor  
function Graph() {  
  this.nodes = {};   
 // Method to add a new node to the graph  
  this.addNode = function(node) {  
    this.nodes\[node\] = this.nodes\[node\] || \[\];  
  };  
// Method to add a new edge to the graph  
  this.addEdge = function(node1, node2, weight) {  
    this.nodes\[node1\].push({ node: node2, weight });  
    this.nodes\[node2\].push({ node: node1, weight });  
  };  
}  
// Creating a graph and adding some nodes and edges  
const graph = new Graph();  
graph.addNode('A');  
graph.addNode('B');  
graph.addNode('C');  
graph.addEdge('A', 'B', 4);  
graph.addEdge('A', 'C', 2);  
graph.addEdge('B', 'C', 3);  
console.log(graph.nodes);  
// Output:  
// {  
//   A: \[{ node: 'B', weight: 4 }, { node: 'C', weight: 2 }\],  
//   B: \[{ node: 'A', weight: 4 }, { node: 'C', weight: 3 }\],  
//   C: \[{ node: 'A', weight: 2 }, { node: 'B', weight: 3 }\]  
// }
```

In the example above, we used an object to represent the nodes and an adjacency list to represent the edges of the graph. Alternatively, you can also use a class to represent the graph and its nodes and edges.

```
// Node class  
class Node {  
  constructor(value) {  
    this.value = value;  
  }  
}  
  
// Edge class  
class Edge {  
  constructor(node1, node2, weight) {  
    this.node1 = node1;  
    this.node2 = node2;  
    this.weight = weight;  
  }  
}  
  
// Graph class  
class Graph {  
  constructor() {  
    this.nodes = {};  
    this.edges = \[\];  
  }  
  
  // Method to add a new node to the graph  
  addNode(value) {  
    this.nodes\[value\] = new Node(value);  
  }  
  
  // Method to add a new edge to the graph  
  addEdge(node1, node2, weight) {  
    const edge = new Edge(node1, node2, weight);  
    this.edges.push(edge);
```

Hash Table
----------

A hash table is a data structure that maps keys to values using a hash function. The hash function calculates the index of an array where a given value should be stored or retrieved. This allows for efficient insertion and retrieval of values in the table.

In JavaScript, you can implement a hash table using an array and a hash function.

```
// HashTable constructor  
function HashTable() {  
  this.table = \[\];  
  
  // Hash function to calculate the index for a given key  
  this.hash = function(key) {  
    let total = 0;  
    for (let i = 0; i < key.length; i++) {  
      total += key.charCodeAt(i);  
    }  
    return total % this.table.length;  
  };  
  
  // Method to add a new key-value pair to the hash table  
  this.add = function(key, value) {  
    const index = this.hash(key);  
    if (!this.table\[index\]) {  
      this.table\[index\] = \[\];  
    }  
    this.table\[index\].push(\[key, value\]);  
  };  
  
  // Method to retrieve the value for a given key  
  this.get = function(key) {  
    const index = this.hash(key);  
    if (!this.table\[index\]) {  
      return null;  
    }  
    for (let i = 0; i < this.table\[index\].length; i++) {  
      if (this.table\[index\]\[i\]\[0\] === key) {  
        return this.table\[index\]\[i\]\[1\];  
      }  
    }  
    return null;  
  };  
}  
  
// Creating a hash table and adding some key-value pairs  
const table = new HashTable();  
table.add('abc', 123);  
table.add('def', 456);  
table.add('ghi', 789);  
  
// Retrieving a value from the table  
console.log(table.get('def'));  // Output: 456
```

Wrapping it Up
--------------

Thanks for reaching this far, you are a fantastic reader!

We have checked the most used data structures and their implementation in JavaScript.

Follow [Adarsh gupta](https://medium.com/u/4323d7b9f6b1?source=post_page-----bf8916532329--------------------------------) for more and follow me on [Twitter](http://twitter.com/@Adarsh____gupta) as well.

You can support my work by giving a tip(since medium doesn’t pay Indian folks l like me).
