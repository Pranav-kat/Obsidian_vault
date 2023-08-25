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

### Balanced tree?
 ```java
 public boolean isBalanced(TreeNode root){
 return maxDepth(root)!=-1;
 }
 
 public int maxDepth(TreeNode root){
 if(root == null) return 0;

 int lh = maxDepth(root.left);
 if(lh==-1) return -1;
 int rh = maxDepth(root.right);
 if(rh==-1) return -1;

if(Math.abs(lh-rh)>1) return -1;

 return 1+ Math.max(lh,rh);
  }


 ```

### Diameter of a tree
 Definition: Longest path between any two nodes. 
 PS: Need not pass through the root node. 
 ```java
 public int diameterOfBinaryTree(TreeNode root) {
        int[] diameter = new int[1];
        maxDepth(root, diameter);
        return diameter[0];
    }

    public int maxDepth(TreeNode root, int[] diameter){
        if(root == null) return 0;

        int lh = maxDepth(root.left, diameter);
        int rh = maxDepth(root.right, diameter);
        diameter[0] = Math.max(lh+rh, diameter[0]);
        return 1 + Math.max(lh, rh);
    }
 ```


### Identical Trees
 ```java 
 public boolean isSameTree(TreeNode p, TreeNode q) {
        if(p == null && q == null) return true;
        if(p == null || q == null || p.val != q.val) return false;
        return isSameTree(p.left, q.left) && isSameTree(p.right, q.right);          
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