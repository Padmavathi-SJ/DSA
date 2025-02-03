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
