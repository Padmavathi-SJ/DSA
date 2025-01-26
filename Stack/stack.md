## Stack Data Structure
### Built-in methods using in stack
* s.push() --add
* s.pop() --remove
* s.isEmpty() --check if empty
* s.peek() --get the top element, won't remove
* s.get()--> to get an element from a specific position
* Collections.sort(s)--> to sort a stack
* s.size() -> size of stack
* s.contains(element) --> to check is present or not
* s.insertElementAt(element, index);
* s.remove(index) --> to remove an element in a specific position

### insert into stack and print
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Stack<Integer> s = new Stack<>();
        s.push(1);
        s.push(2);
        s.push(3);
        s.push(4);
        s.push(5);
        for(int i=0; i<s.size(); i++){
            System.out.printf("%d ", s.get(i));
        }
    }
}
"""
1 2 3 4 5
"""
```

### sort a stack elements
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input= new Scanner(System.in);
        Stack<Integer> s = new Stack<>();
        for(int i=0; i<5; i++){
            s.push(input.nextInt());
        }
        Collections.sort(s);
        for(int i=0; i<5; i++){
            System.err.printf("%d ", s.get(i));
        }
    }
}
"""
9 4 2 8 1
1 2 4 8 9
"""
```

### find max and min in a stack
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input= new Scanner(System.in);
        Stack<Integer> s = new Stack<>();
        int n=6;
        for(int i=0; i<n; i++){
            s.push(input.nextInt());
        }
       Collections.sort(s);
        System.err.printf("Max: %d\n", s.get(n-1));
        System.err.printf("Min: %d", s.get(0));
    }
}
"""
6 4 8 7 1 2
Max:8
Min:1
"""
```

### remove all emelemnts in a stack
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input= new Scanner(System.in);
        Stack<Integer> s = new Stack<>();
        int n=6;
        for(int i=0; i<n; i++){
            s.push(input.nextInt());
        }
        System.err.println(s);
       s=new Stack<>();
       System.err.println(s);

    }
}
"""
1 2 3 4 5 6
[1, 2, 3, 4, 5, 6]
[]
"""
```

### remove duplicates
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input= new Scanner(System.in);
        Stack<Integer> s = new Stack<>();
        int n=input.nextInt();
        for(int i=0; i<n; i++){
            s.push(input.nextInt());
        }
      removeDuplicates(s);
      System.out.println(s);
    }
    public static void removeDuplicates(Stack<Integer> s){
        Stack<Integer> tempStack=new Stack<>();
        while(!s.isEmpty()){
            int element=s.pop();
            if(!tempStack.contains(element)){
                tempStack.push(element);
            }
        }
        while(!tempStack.isEmpty()){
            s.push(tempStack.pop());
        }
    }
}
"""
6
1 1 2 4 3 5
[1, 2, 4, 3, 5]
"""
```

### Right rotate
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input= new Scanner(System.in);
        Stack<Integer> s = new Stack<>();
        int n=input.nextInt();
        for(int i=0; i<n; i++){
            s.push(input.nextInt());
        }
        rotate(s);
         System.out.println(s);
    }
    public static void rotate(Stack<Integer> s){
        if(s.isEmpty()) return;

        int last=s.pop();
        s.insertElementAt(last, 0);
    }
}
"""
6
1 2 3 4 5 6
[6, 1, 2, 3, 4, 5]
"""
```

### merge two stacks
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input= new Scanner(System.in);
        Stack<Integer> s1 = new Stack<>();
        int n1=input.nextInt();
        for(int i=0; i<n1; i++){
            s1.push(input.nextInt());
        }
        Stack<Integer> s2=new Stack<>();
        int n2=input.nextInt();
        for(int i=0; i<n2; i++){
            s2.push(input.nextInt());
        }
        for(int i=0; i<n2; i++){
            s1.push(s2.get(i));
        }
        System.out.println(s1);
}
}
"""
5
1 2 3 4 5  
5
6 7 8 9 10
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
"""
```

### merge 2 stacks --> remove duplicates --> print in ascending order
```
import java.util.*;
class Main{
    public static void main(String[] args){
        Scanner input= new Scanner(System.in);
        Stack<Integer> s1 = new Stack<>();
        int n1=input.nextInt();
        for(int i=0; i<n1; i++){
            s1.push(input.nextInt());
        }
        Stack<Integer> s2=new Stack<>();
        int n2=input.nextInt();
        for(int i=0; i<n2; i++){
            s2.push(input.nextInt());
        }
        for(int i=0; i<n2; i++){
            if(!s1.contains(s2.get(i))){
            s1.push(s2.get(i));
            }
        }
        Collections.sort(s1);
        System.out.println(s1);
}
}
"""
5
6 7 9 4 1
5
6 2 1 4 5
[1, 2, 4, 5, 6, 7, 9]
"""
```
