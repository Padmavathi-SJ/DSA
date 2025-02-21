## Map Interface
## Map Interface ---> extends AbstractMap ---> implements ----> HashMap

### HashMap
* data will be stored as key value pairs
* for key --> only one null key allowed
* for values --> any no of null values can be allowed
* order is not preserved
* No thread safe , if we want thread safe go for --> concurrent HashMap
* Duplicates not allowed , if we try to insert duplicates it will replace(overwrite) with existing values
  
### 1. insert and print elements in Hashmap
```
import java.util.*;
class Main{
    public static void main(String[] args){
        HashMap<Integer, String> map1=new HashMap<>();
        map1.put(1, "padma");
        map1.put(2, "kavi");
        map1.put(3, "akil");
        map1.put(4, "ddas");
        System.out.println(map1);
    }
}
"""
{1=padma, 2=kavi, 3=akil, 4=ddas}
"""
```
