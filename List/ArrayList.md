## List:
## java list interfaces --> ArrayList, LinkedList, Stack, Vector

### ArrayList Interface
* To store & manage ordered collections of data we go to List concept
* for the reason of dynamic resizing & efficient performance!
* sequential order
* order of insert is maintained
* can have duplicate values
* cad add null values
* by using index we can traverse list
* in ArrayList by using listIterator() we can traverse arrayList in forward and backward directions
  

### Operations used in ArrayList Interface
* add() --> add an element
* get() --> get an element
* remove() --> remove an element
* removeAll() --> to remove all elements
* removeRange(fromIndex, toIndex)
* set(index, newValue) --> update an eleemnt in a specific posiiton
* indexOf(elemnt) --> to get an elemnet's index
* lastIndexOf()
* contains(element) --> to check list contains this element or not
* list1.containsAll(list2) 
* list.size() --> to get size of list
* clear(list) --> to remove/delete all the elements in a list
* Collections.sort(l) --> to sort elements
* Collections.copy(list1, list2);
* Collections.reverse(list)
* Collections.suffle(list)
* Collections.swap(list, index1, index2)
* list.isEmpty()
* list1.addAll(list2);
* list1.equals(list2)



### operations performed in ArrayList
```
import java.util.*;
class Main{
public static void main(String[] args){
    Scanner input = new Scanner(System.in);

    List<String> l =new ArrayList<>();
    int n=6;
    for(int i=0; i<n; i++){
        l.add(input.next());
    }
    l.set(0, "Oii");
    System.out.println(l.remove(5));
    System.out.println(l.indexOf("are"));
    System.out.println(l.get(1));
    System.out.println(l.get(0));
    System.out.println(l.contains("dii"));
 System.out.println(l);

}
}
"""
Hi padma how is your job
job
-1
padma
Oii
false
[Oii, padma, how, is, your]
"""
```

### Methods of list interface performed
```
import java.util.*;
class Main{
public static void main(String[] args){
    Scanner input = new Scanner(System.in);

    List<String> l =new ArrayList<>();
    List<String> l1=new ArrayList<>();
    int n=6;
    for(int i=0; i<n; i++){
        l.add(input.next());
    }
    l.set(0, "Oii");
    System.out.println(l.remove(5));
    l.remove("your");
    System.out.println(l.indexOf("are"));
    System.out.println(l.get(1));
    System.out.println(l.get(0));
    System.out.println(l.contains("dii"));
    l.add(2, "vathi");
    System.out.println(l);
    l1.add("Engineer");
    l1.addAll(1, l);
    System.out.println(l1);
    System.out.println(l1.size());
    // l1.clear(); //clear the all elements in this list, but the structure won't
    System.out.println(l.equals(l1));
    System.out.println(l1.isEmpty());
    System.out.println(l.contains("Oii"));
    System.out.println(l1.containsAll(l));
}
}
"""
Hi padma how is your job
job
-1
padma
Oii
false
[Oii, padma, vathi, how, is]
[Engineer, Oii, padma, vathi, how, is]
6
false
false
true
true
"""
```

### Sort an ArrayList<Integer> in ascending order without using Collections.sort().
```
import java.util.*;
class Main{
public static void main(String[] args){
    Scanner input = new Scanner(System.in);

    List<Integer> l=new ArrayList<>();
    for(int i=0; i<6; i++){
        l.add(input.nextInt());
    }
for(int i=0; i<l.size(); i++){
    for(int j=i+1; j<l.size(); j++){
        if(l.get(i) > l.get(j))
        Collections.swap(l, i, j);
    }
}
System.out.println(l);
}
}
"""
2 6 5 1 3 4
[1, 2, 3, 4, 5, 6]
"""
```

### Subarray with Given Sum
* Find a subarray whose sum equals the target.
```
import java.util.*;
class Main{
    public static int check(List<Integer> l, int s, int e){
        int sum=0;
        for(int i=s; i<=e; i++){
            sum+=l.get(i);
        }
        return sum;
    }
    public static void copy(List<Integer> l, int s, int e){
        List<Integer> result=new ArrayList<>();
        for(int i=s; i<=e; i++){
            result.add(l.get(i));
        }
        System.out.println(result);
    }
public static void main(String[] args){
    Scanner input = new Scanner(System.in);

    List<Integer> l=new ArrayList<>();
    for(int i=0; i<6; i++){
        l.add(input.nextInt());
    }
    boolean found=false;
    int t=33;
    for(int i=0; i<6; i++){
        for(int j=i+1; j<6; j++){
            int sum=check(l, i,j);
            if(sum == t){
                copy(l, i, j);
                //found=true;
                //break;
            }
        }
    }
}
}
"""
1 4 20 3 10 5
[20, 3, 10]
"""
```

### Find Leaders in an ArrayList
* An element is a "leader" if it is greater than all elements to its right.
```
import java.util.*;
class Main{
    public static boolean check(List<Integer> l, int n, int j, int len){
        for(int i=j; i<len; i++){
            if(l.get(i) > n){
                return false;
            }
        }
        return true;
    }
public static void main(String[] args){
    Scanner input = new Scanner(System.in);

    List<Integer> l=new ArrayList<>();
    for(int i=0; i<6; i++){
        l.add(input.nextInt());
    }
    List<Integer> res=new ArrayList<>();
    boolean found=false;
    int t=33;
    for(int i=0; i<6; i++){
        if(check(l, l.get(i), i+1,  6 )){
            res.add(l.get(i));
        }
        }
        System.out.println(res);
    }
    
}
"""
16 17 4 3 5 2
[17, 5, 2]
"""
```
