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

## Nested Lists

### split even and odd 
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        int n=input.nextInt();
        List<Integer> l=new ArrayList<>();
        for(int i=0; i<n; i++){
            l.add(input.nextInt());
        }
        List<List<Integer>> ll=new ArrayList<>();
        List<Integer> even=new ArrayList<>();
        List<Integer> odd=new ArrayList<>();
        for(int i=0; i<n; i++){
           if(l.get(i) % 2 == 0){
            even.add(l.get(i));
           }
           else{
            odd.add(l.get(i));
           }
        }
        ll.add(even);
        ll.add(odd);
       System.out.println(ll);
    }
}
"""
6
1 2 3  4 5 6
[[2, 4, 6], [1, 3, 5]]
"""
```

### print sublists
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        int n=input.nextInt();
        List<List<Integer>> ll=new ArrayList<>();

        for(int i=0; i<n; i++){
            ll.add(new ArrayList<>());
        }
        System.out.println(ll);
    }
}
"""
3
[[], [], []]
"""
```

### subarray of target sum
```
import java.util.*;
class Main{
    public static int findSum(List<Integer> l, int s, int e){
        int sum=0;
        for(int i=s; i<=e; i++){
            sum+=l.get(i);
        }
        return sum;
    }
    public static void addElements(List<Integer> l, List<Integer> curr, int s, int e){
        for(int i=s; i<=e; i++){
            curr.add(l.get(i));
        }
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        int n=input.nextInt();
        List<Integer> l=new ArrayList<>();
        for(int i=0; i<n; i++){
            l.add(input.nextInt());
        }
        int target=input.nextInt();
        List<List<Integer>> ll=new ArrayList<>();
        int sum=0;
        for(int i=0; i<n; i++){
            for(int j=i; j<n; j++){
                sum=findSum(l, i, j);
                if(sum==target){
                    int len=j-i+1;
                    List<Integer> curr = new ArrayList<>(len);
                    addElements(l, curr, i, j);
                    ll.add(curr);
                }
            } 
        }
        System.out.println(ll);
    }
}
"""
8
1 2 4 3 6 5 1 2
10
[[1, 2, 4, 3]]
"""
```

### get and print lists of list
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        int n=input.nextInt();
       List<List<Integer>> ll=new ArrayList<>();
       for(int i=0; i<n; i++){
        int len=input.nextInt();
        List<Integer> sub=new ArrayList<>();
        for(int j=0; j<len; j++){
            sub.add(input.nextInt());
        }
        ll.add(sub);
       }
       System.out.println(ll);
    }
}
"""
4
3
1 2 3
5
8 6 4 2 5
2
3 5
6
1 4 6 5 2 3
[[1, 2, 3], [8, 6, 4, 2, 5], [3, 5], [1, 4, 6, 5, 2, 3]]
"""
```

### Sum of Each Sublist
```
import java.util.*;
class Main{
    public static int findSum(List<Integer> l){
        int sum=0;
        for(int i=0; i<l.size(); i++){
            sum+=l.get(i);
        }
        return sum;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        int n=input.nextInt();
       List<List<Integer>> ll=new ArrayList<>();
       for(int i=0; i<n; i++){
        int len=input.nextInt();
        List<Integer> sub=new ArrayList<>();
        for(int j=0; j<len; j++){
            sub.add(input.nextInt());
        }
        ll.add(sub);
       }
       List<Integer> res=new ArrayList<>();
       for(int i=0; i<n; i++){
        int sum=findSum(ll.get(i));
        res.add(sum);
       }
       System.out.println(res);
    }
}
"""
3
2
1 2
3
5 2 3
3
1 2 3
[3, 10, 6]
"""
```

### Find Maximum in Each Sublist
```
import java.util.*;
class Main{
    public static int findmax(List<Integer> l){
        return Collections.max(l);
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        int n=input.nextInt();
       List<List<Integer>> ll=new ArrayList<>();
       for(int i=0; i<n; i++){
        int len=input.nextInt();
        List<Integer> sub=new ArrayList<>();
        for(int j=0; j<len; j++){
            sub.add(input.nextInt());
        }
        ll.add(sub);
       }
       List<Integer> res=new ArrayList<>();
       for(int i=0; i<n; i++){
        int max=findmax(ll.get(i));
        res.add(max);
       }
       System.out.println(res);
    }
}
"""
3
3
5 2 1
3
6 4 5
3 
7 8 9
[5, 6, 9]
"""
```

### Reverse Each Sublist

```
import java.util.*;
class Main{
    public static void reversed(List<Integer> l){
        Collections.reverse(l);
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        int n=input.nextInt();
       List<List<Integer>> ll=new ArrayList<>();
       for(int i=0; i<n; i++){
        int len=input.nextInt();
        List<Integer> sub=new ArrayList<>();
        for(int j=0; j<len; j++){
            sub.add(input.nextInt());
        }
        ll.add(sub);
       }

       for(int i=0; i<n; i++){
        reversed(ll.get(i));
       }
       System.out.println(ll);
    }
}
"""
3
5
1 2 3 4 5
3
2 5 6
3
7 8 9
[[5, 4, 3, 2, 1], [6, 5, 2], [9, 8, 7]]
"""
```

###  Flatten the List of Lists
* Convert a list of lists into a single list containing all elements.
```
import java.util.*;
class Main{
    public static void adding(List<Integer> org, List<Integer> temp){
       for(int i=0; i<temp.size(); i++){
        org.add(temp.get(i));
       }
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        int n=input.nextInt();
       List<List<Integer>> ll=new ArrayList<>();
       for(int i=0; i<n; i++){
        int len=input.nextInt();
        List<Integer> sub=new ArrayList<>();
        for(int j=0; j<len; j++){
            sub.add(input.nextInt());
        }
        ll.add(sub);
       }
       List<Integer> res=new ArrayList<>();
       for(int i=0; i<n; i++){
        adding(res, ll.get(i));
        }
       System.out.println(res);
    }
}
"""
3
2
1 2
3
4 5 6
3
7 8 9
[1, 2, 4, 5, 6, 7, 8, 9]
"""
```
