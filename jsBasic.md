## JS 的一些数据结构

动态和弱类型
JavaScript 是一种有着动态类型的动态语言。JavaScript 中的变量与任何特定值类型没有任何关联，任何变量都可以被赋予（和重新赋予）各种类型的值：


```js
Copy to Clipboard
let foo = 42; // foo 现在是一个数值
foo = "bar"; // foo 现在是一个字符串
foo = true; // foo 现在是一个布尔值
```

JavaScript 也是一个弱类型语言，这意味着当操作涉及不匹配的类型时，它允许隐式类型转换，而不是抛出类型错误。

```js
const foo = 42; // foo 现在是一个数值
const result = foo + "1"; // JavaScript 将 foo 强制转换为字符串，因此可以将其与另一个操作数连接起来
console.log(result); // 421
```

BigInt 类型
BigInt 类型在 Javascript 中是一个数字的原始值，它可以表示任意大小的整数。使用 BigInt，你可以安全地存储和操作巨大的整数，甚至超过 Number 的安全整数限制（Number.MAX_SAFE_INTEGER）。

BigInt 是通过将 n 附加到整数末尾或调用 BigInt() 函数来创建的。

本例演示了递增 Number.MAX_SAFE_INTEGER 会返回预期结果：

```js
// BigInt
const x = BigInt(Number.MAX_SAFE_INTEGER); // 9007199254740991n
x + 1n === x + 2n; // false，因为 9007199254740992n 和 9007199254740993n 不相等

// Number
Number.MAX_SAFE_INTEGER + 1 === Number.MAX_SAFE_INTEGER + 2; // true，因为都等于 9007199254740992
```

你可以使用大多数运算符处理 BigInt，包括 +、*、-、** 和 %。——唯一被禁止的是 >>>。BigInt 并不是严格等于有着相同数学值的 Number，而是宽松的相等。


## Map：

ES6 引入了 Map 数据结构，它提供了一种更灵活的键值对集合方式。Map 对象存储键值对，并且能够记住键的原始插入顺序。与对象不同的是，Map 中的键可以是任意类型的值，而不仅仅是字符串或符号。示例：

```js
let map = new Map();
map.set("name", "John");
map.set("age", 30);
map.set("city", "New York");
```


在计算机科学中，数据结构是指在计算机内部组织和存储数据的方式。它们是为了实现高效的访问和修改而设计的。常见的数据结构包括数组、链表、栈、队列、树等等。

JavaScript中的内置数据类型包括数字、字符串、布尔值、undefined和null。除此之外，JavaScript还提供了多种自定义数据类型，例如对象、数组和函数。接下来我们将介绍这些自定义数据类型，并展示如何使用它们来创建更复杂的数据结构。

# 二、对象

在JavaScript中，对象是最常见的自定义数据类型之一。一个对象可以有无数个属性，并且每个属性都可以包含不同类型的值。以下是创建一个简单对象的语法：

上面这个例子中，我们创建了一个名为`obj`的对象，并给它添加了三个属性：`name`、`age`和`isMarried`。在这个例子中，属性的值可能是字符串、数字或布尔值。

对象是一种非常有用的数据结构，因为它们提供了一种可扩展的、动态的方式来存储数据。您可以随时添加或删除属性，并且还可以通过使用“点”语法或方括号语法来访问属性。



````
```javascript
let obj = {
  name: 'John',
  age: 30,
  isMarried: true
};
```
````

# 三、数组

另一个重要的JavaScript数据类型是数组。数组是一个有序集合，其中每个元素都有一个数字索引。以下是创建一个简单数组的语法：

````
```javascript
let arr = [1, 2, 3, 4, 5];
```
````

在这个例子中，我们创建了一个名为`arr`的数组，并将五个数字添加到其中。您可以通过使用索引来访问数组中的元素。



数组也是非常有用的数据结构，因为它们允许您轻松地存储和操作多个值。您可以使用各种内置方法对数组进行操作，例如push()、pop()、shift()和unshift()等等。



# 四、栈

栈是另一种很常用的数据结构，在JavaScript中也很容易实现。栈是一种后进先出（LIFO）的数据结构，其中最后添加到栈中的项最先被移除。

以下是如何使用JavaScript实现栈：

````
```javascript
class Stack {
  constructor() {
    this.items = [];
  }
  
  push(element) {
    this.items.push(element);
  }
  pop() {
    if (this.items.length == 0)
      return "Underflow";
    return this.items.pop();
  }
  peek() {
    return this.items[this.items.length - 1];
  }
  isEmpty() {
    return this.items.length == 0;
  }
}
```
````

在这个例子中，我们使用JavaScript类来定义一个栈数据结构。这个类有四个方法：push()、pop()、peek()和isEmpty()。push()方法将一个元素添加到栈的顶部，pop()方法将栈顶的元素移除并返回它，peek()方法返回栈顶的元素但不会将其移除，isEmpty()方法检查栈是否为空。



# 五、队列

另一种很常用的数据结构是队列。队列是一种先进先出（FIFO）的数据结构，其中最先添加到队列中的项最先被移除。

以下是如何使用JavaScript实现队列：

```
class Queue {
  constructor() {
    this.items = [];
  }
  
  enqueue(element) {
    this.items.push(element);
  }
  dequeue() {
    if (this.isEmpty())
      return "Underflow";
    return this.items.shift();
  }
  front() {
    if (this.isEmpty())
      return "No elements in Queue";
    return this.items[0];
  }
  isEmpty() {
    return this.items.length == 0;
  }
}

```



在这个例子中，我们使用JavaScript类来定义一个队列数据结构。这个类有四个方法：enqueue()、dequeue()、front()和isEmpty()。enqueue()方法将一个元素添加到队列的末尾，dequeue()方法将队首的元素移除并返回它，front()方法返回队首的元素但不会将其移除，isEmpty()方法检查队列是否为空。



# 六、链表

链表是一种动态数据结构，用于表示一系列元素。每个元素都由一个节点表示，并且每个节点包含指向下一个节点的指针。以下是如何使用JavaScript实现链表：

````
```javascript
class Node {
  constructor(element) {
    this.element = element;
    this.next = null;
  }
}
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }
  add(element) {
    let node = new Node(element);
    let current;
    if (this.head == null)
      this.head = node;
    else {
      current = this.head;
      while (current.next)
        current = current.next;
      current.next = node;
    }
    this.size++;
  }
  remove(element) {
    let current = this.head;
    let previous = null;
    while (current != null) {
      if (current.element === element) {
        if (previous == null)
          this.head = current.next;
        else
          previous.next = current.next;
        this.size--;
        return true;
      }
      previous = current;
      current = current.next;
    }
    return false;
  }
  printList() {
     let currNode = head
     console.log("Linked List:")
     while (currNode) {
        console.log(currNode.element);
        currNode= currNode.next;
     }
  }
}
```
````

在这个例子中，我们使用JavaScript类来定义一个链表数据结构。这个类有三个方法：add()、remove()和printList()。add()方法将一个元素添加到链表的末尾，remove()方法从链表中删除指定的元素，printList()方法将链表中的所有元素打印出来。



# 七、树

树是一种非常重要的数据结构，用于存储和操作层次结构。在计算机科学中，树是由节点和边组成的图形结构。以下是如何使用JavaScript实现树：

````
```javascript
class Node {
  constructor(data) {
    this.data = data;
    this.left = null;
    this.right = null;
  }
}
class BinarySearchTree {
  constructor() {
    this.root = null;
  }
  insert(data) {
    let newNode = new Node(data);
    if (this.root === null)
      this.root = newNode;
    else
      this.insertNode(this.root, newNode);
  }
  insertNode(node, newNode) {
    if (newNode.data < node.data) {
      if (node.left === null)
        node.left = newNode;
      else
        this.insertNode(node.left, newNode);
    } else {
      if (node.right === null)
        node.right = newNode;
      else
        this.insertNode(node.right, newNode);
    }
  }
  remove(data) {
    this.root = this.removeNode(this.root, data);
  }
 removeNode(node, key) {
   if(node === null){
     return null;
   }else if(key < node.data){
     node.left = removeNode(node.left,key);
     return node;
   }else if(key > node.data){
     node.right= removeNode(node.right,key);
     return node;
   }else{
     //no children
     if(node.left === null && node.right == null){
       node= null;
       return node;
     }
     //one child
     if(node.left === null){
       node = node.right;
       return node;
     }else if(node.right === null){
       node = node.left;
       return node;
     }
     //two children
     let aux = this.findMinNode(node.right);
     node.data = aux.data;
     node.right= removeNode(node.right, aux.data);
     return node;
   }
}
  findMinNode(node) {
    if (node.left === null)
      return node;
    else
      return this.findMinNode(node.left);
  }
  getRootNode() {
    return this.root;
  }
  inorder(node) {
    if (node !== null) {
      this.inorder(node.left);
      console.log(node.data);
      this.inorder(node.right);
    }
  }
  preorder(node) {
    if (node != null) {
      console.log(node.data);
      this.preorder(node.left);
      this.preorder(node.right);
    }
  }
  postorder(node) {
    if (node != null) {
      this.postorder(node.left);
      this.postorder(node.right);
      console.log(node.data);
    }
  }
}
```
````

在这个例子中，我们使用JavaScript类来定义一个二叉搜索树数据结构。这个类有七个方法：insert()、remove()、removeNode()、findMinNode()、getRootNode()、inorder()、preorder()和postorder()。insert()方法将一个元素添加到树中，remove()方法从树中删除指定的元素，findMinNode()方法查找树中的最小元素，getRootNode()方法返回树的根节点，inorder()、preorder()和postorder()方法分别以不同的顺序遍历树中的所有节点。