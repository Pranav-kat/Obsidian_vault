---
share: true
---

## Binary Trees
Types:
 Full Binary Tree
 Complete Binary Tree
 Perfect Binary Tree
 Skewed Binary Tree

In Binary Search Trees, all the computations take O(logN) time.

### Single Traversal pre-in-post code using a Stack
 ```java
 void allTraversals(TreeNode root){
 Stack<Pair> stack = new Stack<>();
 stack.push(new Pair(root, 1));
 ArrayList<Integer> preorder = new ArrayList<>();
 ArrayList<Integer> inorder = new ArrayList<>();
 ArrayList<Integer> postorder = new ArrayList<>();
 if(root == null){
 return;
 }
 while(!stack.isEmpty()){
 Pair it = stack.pop();
 if(it.getValue)




 }

 
 }
 ```


### Maximum Depth of a Binary Tree
 ```java
	public int maxDept(TreeNode root){
	if(root == null){ return 0;}

	return 1 + Math.max(maxDepth(root.left), maxDepth(root.right));
	} 
 ```

## AVL 
Adelson Velskii Lendis
- A self balancing binary tree
- Right shift a tree || Left shift a tree
	- Four methods/rules to apply these methods
		1. 

### Steps to balance a tree {AVL}
1. Insert the node N normally until it makes the tree unbalanced
2. Start from node N and find the node which makes the tree unbalanced, **BOTTOM UP**
3. Using one of the 4 rules -> Rotate