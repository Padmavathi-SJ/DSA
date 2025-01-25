## Stack Data Structure
### Built-in methods using in stack
* s.push() --add
* s.pop() --remove
* s.isEmpty() --check if empty
* s.peek() --get the top element, won't remove

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
