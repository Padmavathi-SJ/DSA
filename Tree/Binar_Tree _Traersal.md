## Binary Tree 

### 01. tree implementation (InOrder Traversal) 
```
import java.util.*;
class Node{
    int data;
    Node left, right;
    public Node(int data){
        this.data=data;
    }
}
class BinaryTree {
    Node root;
    public BinaryTree(int data){
        root=new Node(data);
    }
    void printTree(Node root){
        if(root==null) return;
        printTree(root.left);
System.out.print(root.data + " ");
        printTree((root.right));
    }
}

class Main {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        BinaryTree tree=new BinaryTree(1);
        
        tree.root.left=new Node(2);
        tree.root.right=new Node(3);
        tree.root.left.left=new Node(4);
        tree.root.left.right=new Node(5);
        tree.root.right.left=new Node(6);
        tree.root.right.right=new Node(7);
        tree.printTree(tree.root);
    }
    }

"""
4 2 5 1 6 3 7
"""
```
