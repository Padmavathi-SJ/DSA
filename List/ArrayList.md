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
* set(index, newValue) --> update an eleemnt in a specific posiiton
* indexOf(elemnt) --> to get an elemnet's index
* lastIndexOf()
* contains(element) --> to check list contains this element or not

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

}
}
"""
Hii pamd ahow are your job
job
3
pamd
Oii
false
"""
```
