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

###
```
import java.util.*;
class Main{
    public static void main(String[] args){
        HashMap<Integer, String> map1=new HashMap<>();
        map1.put(1, "padma");
        map1.put(2, "kavi");
        map1.put(3, "akil");
        map1.put(4, "ddas");
        HashMap<Integer, String> map2=new HashMap<>(map1);
        System.out.println(map2);
    }
}
"""
{1=padma, 2=kavi, 3=akil, 4=ddas}
"""
```

### print elements of  HashMap using iterator
* Map.Entry<genric type> entry(variable name to access key and values)  : mapName.entrySet()
```
import java.util.*;
class Main{
    public static void main(String[] args){
        HashMap<Integer, String> map1=new HashMap<>();
        map1.put(1, "padma");
        map1.put(2, "kavi");
        map1.put(3, "akil");
        map1.put(4, "ddas");
        map1.put(5, "asdsa");
        HashMap<Integer, String> map2=new HashMap<>(map1);
        map2.put(4, "sai");
        map2.remove(5);
        for(Map.Entry<Integer, String> e: map2.entrySet()){
            System.out.printf("%d - %s\n", e.getKey(), e.getValue());
        }
        //System.out.println(map2);
    }
}
"""
1 - padma
2 - kavi
3 - akil
4 - sai
"""
```


### count frequencies of elements and print in descending order
```
import java.util.*;
class Main{
    public static void printNum(int num, int n){
        for(int i=0; i<n; i++){
            System.out.printf("%d ", num);
        }
    }
    public static void main(String[] args){
        String s="10 20 20 10 10 20 5 20";
        String[] arr=s.split(" ");
        int[] nums=new int[arr.length];
        for(int i=0; i<arr.length; i++){
            nums[i] = Integer.parseInt(arr[i].trim());
        }
        HashMap<Integer, Integer> map=new HashMap<>();
        for(int i=0; i<nums.length; i++){
            if(nums[i] != Integer.MIN_VALUE){
                int count=1;
                for(int j=i+1; j<nums.length; j++){
                    if(nums[i] == nums[j]){
                        count++;
                        nums[j]=Integer.MIN_VALUE;
                    }
                }
                map.put(nums[i], count);
            }
        }
        List<Map.Entry<Integer, Integer>> l=new ArrayList<>(map.entrySet());
        l.sort(Map.Entry.comparingByValue(Comparator.reverseOrder()));
        LinkedHashMap<Integer, Integer> sorted=new LinkedHashMap<>();
        for(Map.Entry<Integer, Integer> e: l){
            sorted.put(e.getKey(), e.getValue());
        }
        for(Map.Entry<Integer, Integer> e:sorted.entrySet()){
            printNum(e.getKey(), e.getValue());
            System.out.printf("\n");
        }
    }
}
"""
20 20 20 20 
10 10 10
5
"""
```
