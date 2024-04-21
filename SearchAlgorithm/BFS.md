#### BFS（广度优先搜索）

深度优先搜索的实现需要借助“队列”来实现，队列的特点是先进先出（区分于栈的先进后出）。 一般来说，BFS的用途有：树/图的层序遍历、求最短路问题等。



```java
queue;//队列
queue.add(start); //队列中加入初始化节点
while (queue) {
    curnode = queue.getFirst();
    for (child in curnode.children) queue.add(child)
}
```



```java
queue;//队列
queue.add(start); //队列中加入初始化节点
while (queue) {
    n = queue.length; //当前层的元素数量
    for (i: 0-> n) {
        node = queue.getFirst();
        for (child in node.children) queue.add(child);
    }
}
```

