## Stack Data Structure
### Built-in methods using in stack
* s.push() --add
* s.pop() --remove
* s.isEmpty() --check if empty
* s.peek() --get the top element, won't remove
* s.get()--> to get an element from a specific position
* Collections.sort(s)--> to sort a stack

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
