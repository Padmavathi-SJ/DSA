## Linked List Data Structure

###
* A Node contians 2 parts --> data and address/reference of next node


### Difference between **LinkedList & Arrays**
### LinkedLists
* Data structure -> Non-Contigious
* Insertion & Deletio  -> Efficient
* Access --> sequential
* Memory Allocation --> Typically allocates memory one by one to individual elements

### Arrays
* Data Structure --> Contigious
* Insertion & Deletion --> Inefficient
* Access --> Random
* Memory Allocation --> Typically allocated to the whole array

### 01. Operations performed on linkedlist
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        int n=input.nextInt();
        LinkedList<String> l=new LinkedList<>();
        for(int i=0; i<n; i++){
            l.add(input.next());
        }
        l.remove("Hi");
        l.remove(1);
        System.out.println(l.size());
        System.out.println(l.get(4));
        System.out.println(l);
        l.set(1, "kavi");
        System.out.println(l.contains("dii"));
        System.out.println(l.size());
        System.out.println(l);
        System.out.println(l.indexOf("you"));
        l.clear(); //l.removeAll (both are same)
        System.out.println(l);
    }
    
}
"""
6
hi padma how are you dii
5
dii
[hi, how, are, you, dii]
true
5
[hi, kavi, are, you, dii]
3
[]
"""
```

### All operations performed on linkedlists
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        int n=input.nextInt();
        LinkedList<Object> l=new LinkedList<>();
        for(int i=0; i<n; i++){
            l.add(input.next());
        }
        //String x=input.next();
        l.addFirst("kavi");
        l.addLast("vathi");
        l.add(1, "akila");
        LinkedList<Object> l2=new LinkedList<>();
        l2.add(5);
        l2.add(10);
        l.addAll(1, l2);
        System.out.println(l);
        System.out.println(l.getFirst());
        System.out.println(l.getLast());
        System.out.println(l.indexOf("akila"));
        l.remove(4);
        l.removeFirst();
        l.removeLast();
        System.out.println(l);
        Collections.swap(l, 0, 3);
        System.out.println(l);
      //  Collections.shuffle(l); will shuffle the elements
        System.out.println(l);
        LinkedList<Object> x=new LinkedList<>();
        x.addAll(l);
        x.addAll(l2);
        System.out.println(x);
        x.pop();
        System.out.println(x);
        System.out.println(x.peekFirst()); //peek or peekFirst (both are same)
        System.out.println(x.peekLast());
        System.out.println(l.contains("akila"));

        List<Object> y=new ArrayList<>(x); //convert a linkedlist to aarraylist
        System.out.println(y);
        System.out.println(l.containsAll(l2));
        System.out.println(x.isEmpty());
 System.out.println(x.get(0);
    }
    
}
"""
2
Hi padma
[kavi, 5, 10, akila, Hi, padma, vathi]
kavi
vathi
3
[5, 10, akila, padma]
[padma, 10, akila, 5]
[padma, 10, akila, 5]
[padma, 10, akila, 5, 5, 10]
[10, akila, 5, 5, 10]
10
10
true
[10, akila, 5, 5, 10]
true
false
10
"""
```

### Without any java inbuilt methods insert and values in a linkedlist
### insert values **at the end of linkedlist**
```
class Main{
    public static class Node{
        int data;
        Node next;
    }
    public static class LinkedList{
        Node head;

        public void insert(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(head==null){
                head=node;
            }
            else{
                Node n=head;
                while(n.next!=null){
                    n=n.next;
                }
                n.next=node;
            }
        }

        public void show(){
            Node node=head;
            while(node.next!=null){
                System.out.println(node.data);
                node=node.next;
            }
            System.out.println(node.data);
        }

    }
public static void main(String[] args){

    LinkedList l=new LinkedList();
    l.insert(5);
    l.insert(10);
    l.insert(15);
    l.insert(20);
    l.show();
}
}
"""
5
10
15
20
"""
```

### Insert elements **at the start of LinkedList**
```
class Main{
    public static class Node{
        int data;
        Node next;
    }
    public static class LinkedList{
        Node head;

        public  void insert(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(head==null){
                head=node;
            }
            else{
                Node n=head;
                while(n.next!=null){
                    n=n.next;
                }
                n.next=node;
            }
        }
        public void insertAtStart(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;
            node.next=head;
            head=node;
        }

        public void show(){
            Node node=head;
            while(node.next!=null){
                System.out.println(node.data);
                node=node.next;
            }
            System.out.println(node.data);
        }
    }
    public static void main(String[] args){
        LinkedList l=new LinkedList();
        l.insert(5);
        l.insert(20);
        l.insert(100);
        l.insertAtStart(10);
        l.insertAtStart(55);
        l.show();
    }
}
"""
55
10
5
20
100
"""
```

### Insert elements at a specific position in a linkedlist
```
class Main{
    public static class Node{
        int data;
        Node next;
    }
    public static class LinkedList{
        Node head;

        public  void insert(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(head==null){
                head=node;
            }
            else{
                Node n=head;
                while(n.next!=null){
                    n=n.next;
                }
                n.next=node;
            }
        }
        public void insertAtStart(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;
            node.next=head;
            head=node;

        }
        public void insertAt(int index, int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(index==0){
                insertAtStart(data);
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                node.next=n.next;
                n.next=node;
            }
        }

        public void show(){
            Node node=head;
            while(node.next!=null){
                System.out.println(node.data);
                node=node.next;
            }
            System.out.println(node.data);
        }
    }
    public static void main(String[] args){
        LinkedList l=new LinkedList();
        l.insert(5);
        l.insert(20);
        l.insert(100);
        l.insertAt(2, 55);
        l.insertAt(0, 200);
       

        l.show();
    }
}
"""
200
5
20
55
100
"""
```

### Delete LinkedList elements at the given position
```
class Main{
    public static class Node{
        int data;
        Node next;
    }
    public static class LinkedList{
        Node head;

        public  void insert(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(head==null){
                head=node;
            }
            else{
                Node n=head;
                while(n.next!=null){
                    n=n.next;
                }
                n.next=node;
            }
        }
        public void insertAtStart(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;
            node.next=head;
            head=node;

        }
        public void insertAt(int index, int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(index==0){
                insertAtStart(data);
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                node.next=n.next;
                n.next=node;
            }
        }
        public void deleteAt(int index){
            if(index==0){
                head=head.next;
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                Node temp=n.next;
                n.next=temp.next;
                temp=null;
            }
        }

        public void show(){
            Node node=head;
            while(node.next!=null){
                System.out.println(node.data);
                node=node.next;
            }
            System.out.println(node.data);
        }
    }
    public static void main(String[] args){
        LinkedList l=new LinkedList();
        l.insert(5);
        l.insert(20);
        l.insert(100);
        l.insertAt(2, 55);
        l.insertAt(0, 200);
        l.deleteAt(2);
        l.deleteAt(0);
       

        l.show();
    }
}
"""
5
55
100
"""
```

### find length of linkedlist
```
class Main{
    public static class Node{
        int data;
        Node next;
    }
    public static class LinkedList{
        Node head;

        public  void insert(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(head==null){
                head=node;
            }
            else{
                Node n=head;
                while(n.next!=null){
                    n=n.next;
                }
                n.next=node;
            }
        }
        public void insertAtStart(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;
            node.next=head;
            head=node;

        }
        public void insertAt(int index, int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(index==0){
                insertAtStart(data);
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                node.next=n.next;
                n.next=node;
            }
        }
        public void deleteAt(int index){
            if(index==0){
                head=head.next;
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                Node temp=n.next;
                n.next=temp.next;
                temp=null;
            }
        }
        public int len(){
            Node n=head;
            int count=0;
            while(n!=null){
                count++;
                n=n.next;
            }
            return count;
        }

        public void show(){
            Node node=head;
            while(node.next!=null){
                System.out.println(node.data);
                node=node.next;
            }
            System.out.println(node.data);
        }
    }
    public static void main(String[] args){
        LinkedList l=new LinkedList();
        l.insert(5);
        l.insert(20);
        l.insert(100);
        l.insertAt(2, 55);
        l.insertAt(0, 200);
        l.deleteAt(2);
        l.deleteAt(0);
        int l2=l.len();
        l.show();
        System.out.println(l2);
    }
}
"""
5
55
100
3 //length of linkedlist
"""
```

### Search elements in a linkedlist
```
class Main{
    public static class Node{
        int data;
        Node next;
    }
    public static class LinkedList{
        Node head;

        public  void insert(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(head==null){
                head=node;
            }
            else{
                Node n=head;
                while(n.next!=null){
                    n=n.next;
                }
                n.next=node;
            }
        }
        public void insertAtStart(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;
            node.next=head;
            head=node;

        }
        public void insertAt(int index, int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(index==0){
                insertAtStart(data);
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                node.next=n.next;
                n.next=node;
            }
        }
        public void deleteAt(int index){
            if(index==0){
                head=head.next;
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                Node temp=n.next;
                n.next=temp.next;
                temp=null;
            }
        }
        public int len(){
            Node n=head;
            int count=0;
            while(n!=null){
                count++;
                n=n.next;
            }
            return count;
        }
        public boolean  search(int data){
            Node n=head;
            while(n!=null){
                if(n.data==data){
                    return true;
                }
                n=n.next;
            }
            return false;
        }

        public void show(){
            Node node=head;
            while(node.next!=null){
                System.out.println(node.data);
                node=node.next;
            }
            System.out.println(node.data);
        }
    }
    public static void main(String[] args){
        LinkedList l=new LinkedList();
        l.insert(5);
        l.insert(20);
        l.insert(100);
        l.insertAt(2, 55);
        l.insertAt(0, 200);
        l.deleteAt(2);
        l.deleteAt(0);
        int l2=l.len();
        System.out.println(l.search(55));
        System.out.println(l.search(200));

        
    }
}
"""
true
false
"""
```

### Reverse a linkedList using a stack
```
import java.util.*;
class Main{
    public static class Node{
        int data;
        Node next;
    }
    public static class LinkedList{
        Node head;

        public  void insert(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(head==null){
                head=node;
            }
            else{
                Node n=head;
                while(n.next!=null){
                    n=n.next;
                }
                n.next=node;
            }
        }
        public void insertAtStart(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;
            node.next=head;
            head=node;

        }
        public void insertAt(int index, int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(index==0){
                insertAtStart(data);
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                node.next=n.next;
                n.next=node;
            }
        }
        public void deleteAt(int index){
            if(index==0){
                head=head.next;
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                Node temp=n.next;
                n.next=temp.next;
                temp=null;
            }
        }
        public int len(){
            Node n=head;
            int count=0;
            while(n!=null){
                count++;
                n=n.next;
            }
            return count;
        }
        public boolean  search(int data){
            Node n=head;
            while(n!=null){
                if(n.data==data){
                    return true;
                }
                n=n.next;
            }
            return false;
        }
        public void reverse(){
           Stack<Integer> s=new Stack<>();
           Node n=head;
           while(n!=null){
            s.push(n.data);
            n=n.next;
           }
           Node m=head;
           while(m!=null){
            m.data=s.pop();
            m=m.next;
           }
        }

        public void show(){
            Node node=head;
            while(node.next!=null){
                System.out.println(node.data);
                node=node.next;
            }
            System.out.println(node.data);
        }
    }
    public static void main(String[] args){
        LinkedList l=new LinkedList();
        l.insert(5);
        l.insert(20);
        l.insert(100);
        int l2=l.len();
       
        l.reverse();
       l.show();
        
    }
}
"""
100
20
5
"""
```

### Reverse LinkedList
```
import java.util.*;
class Main{
    public static class Node{
        int data;
        Node next;
    }
    public static class LinkedList{
        Node head;

        public  void insert(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(head==null){
                head=node;
            }
            else{
                Node n=head;
                while(n.next!=null){
                    n=n.next;
                }
                n.next=node;
            }
        }
        public void insertAtStart(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;
            node.next=head;
            head=node;

        }
        public void insertAt(int index, int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(index==0){
                insertAtStart(data);
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                node.next=n.next;
                n.next=node;
            }
        }
        public void deleteAt(int index){
            if(index==0){
                head=head.next;
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                Node temp=n.next;
                n.next=temp.next;
                temp=null;
            }
        }
        public int len(){
            Node n=head;
            int count=0;
            while(n!=null){
                count++;
                n=n.next;
            }
            return count;
        }
        public boolean  search(int data){
            Node n=head;
            while(n!=null){
                if(n.data==data){
                    return true;
                }
                n=n.next;
            }
            return false;
        }
        public void reverse(){
           Node current=head;
           Node prev=null;
           Node next;
           while(current != null){
            next=current.next;
            current.next=prev;
            prev=current;
            current=next;
           }
           head=prev;
        }
        public void printhead(){
            Node n=head;
            System.err.println(n.data);
        }

        public void show(){
            Node node=head;
            while(node.next!=null){
                System.out.println(node.data);
                node=node.next;
            }
            System.out.println(node.data);
        }
    }
    public static void main(String[] args){
        LinkedList l=new LinkedList();
        l.insert(5);
        l.insert(20);
        l.insert(100);
        l.insert(200);
        int l2=l.len();
       
        l.reverse();
       l.show();
   // l.printhead();
    }
}
"""
200
100
20
5
"""
```

### find middly element
```
import java.util.*;
class Main{
    public static class Node{
        int data;
        Node next;
    }
    public static class LinkedList{
        Node head;

        public  void insert(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(head==null){
                head=node;
            }
            else{
                Node n=head;
                while(n.next!=null){
                    n=n.next;
                }
                n.next=node;
            }
        }
        public void insertAtStart(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;
            node.next=head;
            head=node;

        }
        public void insertAt(int index, int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(index==0){
                insertAtStart(data);
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                node.next=n.next;
                n.next=node;
            }
        }
        public void deleteAt(int index){
            if(index==0){
                head=head.next;
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                Node temp=n.next;
                n.next=temp.next;
                temp=null;
            }
        }
        public int len(){
            Node n=head;
            int count=0;
            while(n!=null){
                count++;
                n=n.next;
            }
            return count;
        }
        public boolean  search(int data){
            Node n=head;
            while(n!=null){
                if(n.data==data){
                    return true;
                }
                n=n.next;
            }
            return false;
        }
        public void reverse(){
           Node current=head;
           Node prev=null;
           Node next;
           while(current != null){
            next=current.next;
            current.next=prev;
            prev=current;
            current=next;
           }
           head=prev;
        }
        public void printhead(){
            Node n=head;
            System.out.println(n.data);
        }
        public void findMiddle(int l){
            int mid=l/2;
            Node n=head;
            int i=0;
            while(n!=null){
                if(i==mid){
            System.out.println(n.data);
                }
                i++;
                n=n.next;
        }
    }

        public void show(){
            Node node=head;
            while(node.next!=null){
                System.out.println(node.data);
                node=node.next;
            }
            System.out.println(node.data);
        }
    }
    public static void main(String[] args){
        LinkedList l=new LinkedList();
        l.insert(5);
        l.insert(20);
        l.insert(100);
        l.insert(200);
        int l2=l.len();
       
        l.reverse();
       l.show();
       l.findMiddle(l2);
   // l.printhead();
    }
}
"""
200
100
20
5
20 //mid element
"""
```

### Merger two sorted linkedlists
```
import java.util.*;
class Main{
    public static class Node{
        int data;
        Node next;
    }
    public static class LinkedList{
        Node head;
        public  void insert(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(head==null){
                head=node;
            }
            else{
                Node n=head;
                while(n.next!=null){
                    n=n.next;
                }
                n.next=node;
            }
        }
        public void insertAtStart(int data){
            Node node=new Node();
            node.data=data;
            node.next=null;
            node.next=head;
            head=node;

        }
        public void insertAt(int index, int data){
            Node node=new Node();
            node.data=data;
            node.next=null;

            if(index==0){
                insertAtStart(data);
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                node.next=n.next;
                n.next=node;
            }
        }
        public void deleteAt(int index){
            if(index==0){
                head=head.next;
            }
            else{
                Node n=head;
                for(int i=0; i<index-1; i++){
                    n=n.next;
                }
                Node temp=n.next;
                n.next=temp.next;
                temp=null;
            }
        }
        public int len(){
            Node n=head;
            int count=0;
            while(n!=null){
                count++;
                n=n.next;
            }
            return count;
        }
        public boolean  search(int data){
            Node n=head;
            while(n!=null){
                if(n.data==data){
                    return true;
                }
                n=n.next;
            }
            return false;
        }
        public void reverse(){
           Node current=head;
           Node prev=null;
           Node next;
           while(current != null){
            next=current.next;
            current.next=prev;
            prev=current;
            current=next;
           }
           head=prev;
        }
        public void printhead(){
            Node n=head;
            System.out.println(n.data);
        }
        public void findMiddle(int l){
            int mid=l/2;
            Node n=head;
            int i=0;
            while(n!=null){
                if(i==mid){
            System.out.println(n.data);
                }
                i++;
                n=n.next;
        }
    }
    public void findNthNode(int index){
        Node n=head;
        for(int i=0; i<index; i++){
            n=n.next;
        }
        System.out.println(n.data);
    }
    public static Node merge(Node head1, Node head2){
       if(head1==null) return head2;
       if(head2==null) return head1;
       Node dummy=new Node();
       dummy.data=-1;
       Node temp=dummy;
       while(head1!=null && head2!=null){
        if(head1.data < head2.data){
            temp.next=head1;
            temp=head1;
            head1=head1.next;
        }
        else{
            temp.next=head2;
            temp=head2;
            head2=head2.next;
        }
     //   temp=temp.next;
       }
       if(head1!=null) temp.next=head1;
       if(head2!=null) temp.next=head2;
       return dummy.next;

    }
        public void show(){
            Node node=head;
            while(node.next!=null){
                System.out.print(node.data + " -> ");
                node=node.next;
            }
            System.out.print(node.data + " -> ");
            System.out.println("null");
        }

    }
    public static void main(String[] args){
        LinkedList l1=new LinkedList();
        l1.insert(1);
        l1.insert(5);
        l1.insert(6);
        l1.insert(6);
        int length=l1.len();
        LinkedList l2=new LinkedList();
        l2.insert(5);
        l2.insert(6);
        l2.insert(7);
        l2.insert(8);
       
       LinkedList mergeList=new LinkedList();
       mergeList.head = LinkedList.merge(l1.head, l2.head);
       mergeList.show();

    }
}
"""
1 -> 5 -> 5 -> 6 -> 6 -> 6 -> 7 -> 8 -> null
"""
```
