---
title: 二叉搜索树的遍历方式
date: 2019-11-19 22:06:54
tags:
---

## 二叉搜索树代码

```java
@Slf4j
public class BST<Key extends Comparable, Value> {
    private Node root;
    
    private int count;
    
    private class Node {
        private Key key;
        
        private Value value;
        
        private Node left;
        
        private Node right;
        
        public Node(Key key, Value value) {
            this.key = key;
            this.value = value;
        }
    }
}
```



## 前序遍历

先输出节点自身的数据，再遍历左子树和右子树的数据。最普通的遍历。

```java
public void preOrder() {
    preOrder(root);
}

private void preOrder(Node node) {
    if(node != null) {
  		log.info("{}", node.key);
        preOrder(node.left);
        preOrder(node.right);
    }
}
```



## 中序遍历

先遍历左子树的数据，再输出自身的数据，最后遍历右子树的数据。通过中序遍历得出的结果就是排序后的结果。

```java

public void inOrder() {
    inOrder(root);
}

private void inOrder(Node node) {
    if(node != null) {
        inOrder(node.left);
        log.info("{}", node.key);
        inOrder(node.right);
    }
}
```



## 后序遍历

先遍历左子树和右子树的数据，最后才输出自身的数据。多用于释放树资源时使用。

```java
public void postOrder() {
    postOrder(root);
}

private void postOrder(Node node) {
    if(node != null) {
        postOrder(node.left);
        postOrder(node.right);
        log.info("{}", node.key);
    }
} 
```



## 结论

前中后序遍历实际就是看看在遍历过程中执行代码在递归遍历左右子树时的相对位置决定。

根据实际应用可以选择不同的遍历方式。