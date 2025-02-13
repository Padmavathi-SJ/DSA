## Tree 
* root
* children
* leaf node
* ancestors
  
### Types 
* Full Binary Tree --> a parent will have 0 or 2 children 
* Complete Binary Tree --> All levels of tree should be filled completely except the last level, The last level has all nodes **left** as possible
* Perfect Binary Tree --> All **leaf nodes** are at the same level
* Balanced Binary Tree -->
* Degenerate Tree --> Every node has a **single children**


## Binary Tree implementation and Traversal
```
class Main{
    public static class Node{
        int data;
        Node left;
        Node right;

        public Node(int data){
            this.data=data;
            this.left=null;
            this.right=null;
        }
    }
    public static class BinaryTree{
        Node root;

        public void insert(int data){
            root=insertRec(root, data);
        }

        public Node insertRec(Node root, int data){
            if(root==null){
                return new Node(data);
            }
            else if(data < root.data){
                root.left=insertRec(root.left, data);
            }
            else if(data > root.data){
                root.right=insertRec(root.right, data);
            }
            return root;
        }
        public void inOrder(){
            inOrderRec(root);
        }
        public void inOrderRec(Node root){
            if(root!=null){
                inOrderRec(root.left);
                System.out.print(root.data + " ");
                inOrderRec(root.right);
            }
        }
        public void preOrder(){
            preOrderRec(root);
        }
        public void preOrderRec(Node root){
            if(root!=null){
                System.out.print(root.data + " ");
                preOrderRec(root.left);
                preOrderRec(root.right);
            }
        }
        public void postOrder(){
            postOrderRec(root);
        }
        public void postOrderRec(Node root){
            if(root!=null){
                postOrderRec(root.left);
                postOrderRec(root.right);
                System.out.print(root.data + " ");
            }
        }

    }
    public static void main(String[] args){
        BinaryTree tree=new BinaryTree();
        tree.insert(10);
        tree.insert(12);
        tree.insert(2);
        tree.insert(4);
        tree.insert(6);
        tree.insert(7);
        tree.inOrder();
        System.out.println("\n");
        tree.preOrder();
        System.out.println("\n");
        tree.postOrder();
    }
}
"""
2 4 6 7 10 12  // InOrder

10 2 4 6 7 12  // PreOrder

7 6 4 2 12 10  // PostOrder
"""
```

