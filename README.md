## [👋Guide for Data Structures and Algorithms](https://carolzhangzz.github.io/DataStructure_Algorithm_HandBook_PreForLeetCode/)
 
 ## [Switch To： Reading Mode📚](https://carolzhangzz.github.io/LeetCode_Data-Structure_and_Algorithm/) 

`This HandBook it currently developed by gitHub page.`

## Basic Language Features

[右移和左移操作](./javaBasic.md)

[Java Script 基本数据结构](./jsBasic.md)

#### 前端开发面试代码题

[字符串解析](./前端面试题汇总/解析字符串.md)

[ConvertToTree](./前端面试题汇总/convertToTree.md)

[可取消的 promise](//前端面试题汇总/cancelPromise.md)


## Basic Data Structure

---
### LinkedList


[206. Reverse Linked List](./Linkedlist/206.md)

[92. Reverse Linked List II](./Linkedlist/92.md)

[83. Remove Duplicates from Sorted List](./Linkedlist/83.md)

[19. Remove Nth Node From End of List](./Linkedlist/19.md)

[21. Merge Two Sorted Lists](./Linkedlist/21.md)

[160. Intersection of Two Linked Lists](./Linkedlist/160.md)

[2. Add Two Numbers](./Linkedlist/2.md)

[142. Linked List Cycle II](./Linkedlist/142.md)

---
### Hash Map

[1160. Find Words That Can Be Formed by Characters](./HashTable/1160.md)

[1189. Maximum Number of Balloons](./HashTable/1189.md)

[1207. Unique Number of Occurrences](./HashTable/1207.md)

[217. Contains Duplicate](./HashTable/217.md)

[20. Valid Parentheses](./HashTable/20.md)

---

### Search Algorithm

[DFS（深度优先搜索)](./SearchAlgorithm/DFS.md)

[BFS（广度优先搜索）](./SearchAlgorithm/BFS.md)

### Binary tree

A binary tree is a simple directed graph where each node has a left node and a right node.

The main traversal methods of binary trees are BFS and DFS.

[226. Invert Binary Tree](./BinaryTree/226.md)

[101. Symmetric Tree](./BinaryTree/101.md)

[104. Maximum Depth of Binary Tree](./BinaryTree/104.md)

[111. Minimum Depth of Binary Tree](./BinaryTree/111.md)

[222. Count Complete Tree Nodes](/BinaryTree/222.md)

[110. Balanced Binary Tree](/BinaryTree/110.md)

[257. Binary Tree Paths](./BinaryTree/275.md)

[404. Sum of Left Leaves](./BinaryTree/404.md)
 
[513. Find Bottom Left Tree Value](./BinaryTree/513.md)

[112. Path Sum](./BinaryTree/112.md) 

[654. Maximum Binary Tree](./BinaryTree/654.md)


[617. Merge Two Binary Trees](./BinaryTree/617.md)

[235. Lowest Common Ancestor of a Binary Search Tree](./BinaryTree/235.md)

[108. Convert Sorted Array to Binary Search Tree](./BinaryTree/108.md)


### [Backtracking algorithm](./Backtracking/backtracking.md)

这个模块是一个小进阶的模块，涉及到了很多的递归，由于递归的思想和我们大脑的思考方法是相反的，但是回溯并不是一个很高效的算法，只适合解决一些数据规模比较小的场景。

[77. Combinations](./Backtracking/77.md)

[39. Combination Sum](./Backtracking/39.md)

[40. Combination Sum II](./Backtracking/40.md)

[216. Combination Sum III](./Backtracking/216.md)

[93. Restore IP Addresses](./Backtracking/93.md) 

[78. Subsets](./Backtracking/78.md)
 
[491. Non-decreasing Subsequences](./Backtracking/491.md)
 
[46. Permutations](./Backtracking/46.md) 

[47. Permutations II](./Backtracking/47.md)

[698. Partition to K Equal Sum Subsets](./Backtracking/698.md)

[51. N-Queens](/Backtracking/51.md)

---

## 记忆化搜索


[198. House Robber](./记忆化搜索/198.md)

[213. House Robber II](./记忆化搜索/213.md)

[494. Target Sum](./记忆化搜索/494.md)

[64. Minimum Path Sum](./记忆化搜索/64.md)

[62. Unique Paths](./记忆化搜索/62.md)

[63. Unique Paths II](./记忆化搜索/63.md)



这个算法的核心就是在递归的基础上记录已经算过的状态，如果下次运算过相同的状态，直接返回已经算过的状态，避免重复运算。

优点：掌握了暴力搜索，比如回溯和递归的写法之后，入门会非常的简单，时间复杂度与常规的（自底向上）动态规划是一致的。

缺点：由于依然是使用递归，所以当数据规模大的时候会有比较大的栈消耗

总结：如果笔试的时候想不出自底向上的动态规划，那么直接使用记忆搜索就可以了

因为暴力搜索二叉树的复杂度是 2 的 n 次方，因此只要 n 的规模大一点点，就肯定会超时。
但可以发现递归的时候有很多重复的运算

```java
int n;

int[] dp = new int[n+1];
//dp 初始值不一定是-1，只要是不可能出现的值就可以了
Arrays.fill(dp,-1);
int dfs(int cur){
    if(cur >= n) return cur == n? 1 : 0;
    //在暴力搜索的基础上改造成 dp 
    //如果不等于-1，说明已经遍历过了 
    if(dp[cur]!=-1) return dp[cur];
    return dp[cur] = dfs[cur+1] + dfs[cur+2];
}
```
如果是 c++ 和 java，就用 dp 就行了，如果是js 或者 python，可以用 map 来做，当然用数组也可以

记忆化搜索是必须要带着``返回值``的
1 递归调用
2 判断该状态是否被计算过
3 递归调用并且计算对应的返回值










 



 




