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


### Maximum path sum
 ```java
 public int maxPathSum(TreeNode root) {
        int[] diameter = new int[1];
        diameter[0] = Integer.MIN_VALUE;
        maxDepth(root, diameter);
        return diameter[0];
    }

    public int maxDepth(TreeNode root, int[] diameter){
        if(root == null) return 0;

        int lh = Math.max(0,maxDepth(root.left, diameter));
        int rh = Math.max(0,maxDepth(root.right, diameter));

        diameter[0] = Math.max(diameter[0], lh+rh+root.val);

        return root.val + Math.max(lh,rh);

    }
 ```


### Zig Zag Traversal
 ```java
 public List<List<Integer>> zigzagLevelOrder(TreeNode root) {
        Queue <TreeNode > queue = new LinkedList <> ();
        List<List<Integer>> wrapList = new ArrayList <>();

        if (root == null) return wrapList; 
        queue.offer(root);
        boolean flag = true;
        while (!queue.isEmpty()) {
            int levelNum = queue.size();
            ArrayList < Integer > subList = new ArrayList < Integer > (levelNum);
            for (int i = 0; i < levelNum; i++) {
                int index = i;
                if (queue.peek().left != null) queue.offer(queue.peek().left);
                if (queue.peek().right != null) queue.offer(queue.peek().right);
                if (flag == true) subList.add(queue.poll().val);
                else subList.add(0, queue.poll().val);
            }
            flag = !flag;
            wrapList.add(subList);
        }
        return wrapList;
    }
 ```
## BST
### Search in BST
 ```java
 public TreeNode searchBST(TreeNode root, int val) {
        if(root == null) return null;

        if(val<root.val) return searchBST(root.left, val);

        if(val>root.val) return searchBST(root.right, val);

        if(val == root.val) return root;
        
        return null;                                }
 ```


### Insertion in BST
 ```java
  public TreeNode insertIntoBST(TreeNode root, int val) {
        if(root == null) { return new TreeNode(val);}
        if(val<root.val) root.left = insertIntoBST(root.left, val);
        else root.right = insertIntoBST(root.right, val);

        return root;
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