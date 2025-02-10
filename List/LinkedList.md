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
"""
```
