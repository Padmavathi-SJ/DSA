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
        l.clear();
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
