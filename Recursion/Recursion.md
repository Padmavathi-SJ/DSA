## Recursion
* A function is calling itself is called **Recursion**


### factorial of a num:
```
import java.util.*;
class Main{
    public static int factorial(int n){
        if(n==1) return 1;
        else return n*factorial(n-1);
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        int n=input.nextInt();
        int fact=factorial(n);
        System.out.println(fact);
    }
}
"""
5
120
"""
```

### Recursive Sum from 1 to N
```
import java.util.*;
class Main{
    public static int sum(int n){
        if(n==0) return 0;
        if(n==1) return 1;
        else return n+sum(n-1);
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        int n=input.nextInt();
        int result=sum(n);
        System.out.println(result);
    }
}
"""
5
15
"""
```

### sum of elements in an array
```
import java.util.*;
class Main{
    public static int find(int[] arr, int sum, int i){
        if(arr.length==0) return 0;
        if(arr.length==1) return arr[0];
        if(i==arr.length) return sum;
        else sum=sum+arr[i++];
        return find(arr, sum, i);
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    int[] arr={};
    int sum=0;
    sum=find(arr, sum, 0);
    System.out.println(sum);
    }
}
"""
0
"""
```

### product of an array
```
import java.util.*;
class Main{
    public static int find(int[] arr, int pro, int i){
        if(arr.length==0) return 0;
        if(arr.length==1) return arr[0];
        if(i==arr.length) return pro;
        else pro=pro*arr[i++];
        return find(arr, pro, i);
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    int[] arr={1,2,3};
    int pro=1;
    pro=find(arr, pro, 0);
    System.out.println(pro);
    }
}
"""
6
"""
```

### find max in an array
```
import java.util.*;
class Main{
    public static int find(int[] arr, int max, int i){
        if(arr.length==0) return 0;
        if(arr.length==1) return arr[0];
        if(i==arr.length) return max;
        if(arr[i] > max) {
            max=arr[i];
    } 
        return find(arr, max, i+1); 
    }

    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    int[] arr={1,10,2,3,4,5};
    int max=find(arr, 0, 0);
    System.out.println(max);
    }
}
"""
10
"""
```

### sum of digits
```
import java.util.*;
class Main{
    public static int find(int n, int sum){
        if(n==0) return sum;
        sum+=n%10;
        n=n/10;
        return find(n, sum);

    }

    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    int n=input.nextInt();
    int sum=find(n, 0);
    System.out.println(sum);
    }
}
"""
12
3
"""
```

### reverse a string
```
import java.util.*;
class Main{
    public static void reverse(String str, int i){
        if(str.length()==1) System.out.println(str);
        if(i<0) return;
        System.out.println(str.charAt(i));
        reverse(str, i-1);
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str=input.next();
    reverse(str, str.length()-1);
    
    }
}
"""
Hello
o
l
l
e
H
"""
```

### power calculation
```
import java.util.*;
class Main{

    public static int find(int x, int y, int pow){
        //if(y==1) return x;
        //if(x==0) return 1;
        if(y==0) return pow;
        pow=pow*x;
        return find(x, y-1, pow);
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    int pow=find(3, 0, 1);
    System.out.println(pow);
    
    }
}
"""
1
"""
```

### Palindrome check
```
import java.util.*;
class Main{
    public static boolean check(String str, int l, int r){
        if(l>=r) return true;
        if(str.charAt(l) != str.charAt(r)) return false;
        return check(str, l+1, r-1); 
    }

    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str=input.next();
    boolean find=check(str, 0, str.length()-1);
    System.out.println(find);
    }
}
"""
padma
false

madam
true

p
true
"""
```

### check element present or not (Binary search)
```
import java.util.*;
class Main{
    public static int find(int[] arr, int element, int i){
        if(i==arr.length) return -1;
        if(arr[i] == element) return i;
        return find(arr, element, i+1);
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    int[] arr={1,2,3,4,5};
    int element=15;
    int index=find(arr, element, 0);
    System.out.println(index);
    }
}
"""
-1
"""
```

### find all the subarrays whose sum is equal to given target
```
import java.util.*;
class Main{
    public static void find(List<List<Integer>> ans, List<Integer> ds, int[] nums, int t, int i, int sum){
        if(sum==t){
            ans.add(new ArrayList<>(ds));
            return;
        }
        if(i>=nums.length || sum>t){
            return;
        }
        ds.add(nums[i]);
        find(ans, ds, nums, t, i+1, sum+nums[i]);
        ds.remove(ds.size()-1);

        find(ans, ds, nums, t, i+1, sum);

    }
    public static void main(String[] args){
        int[] nums={1,2,3,4,5,6,7,10};
        int t=10;
        List<List<Integer>> ans=new ArrayList<>();
        find(ans, new ArrayList<>(), nums, t, 0, 0);
        System.out.println(ans);
    }
}
"""
[[1, 2, 3, 4], [1, 2, 7], [1, 3, 6], [1, 4, 5], [2, 3, 5], [3, 7], [4, 6], [10]]
"""
```

### get unique subArrays whose sum is equal to given target using HashSet
```
import java.util.*;
class Main{
    public static void find(Set<List<Integer>> ans, List<Integer> ds, int[] nums, int t, int i, int sum){
        if(sum==t){
            ans.add(new ArrayList<>(ds));
            return;
        }
        if(i>=nums.length || sum>t){
            return;
        }
        ds.add(nums[i]);
        find(ans, ds, nums, t, i+1, sum+nums[i]);
        ds.remove(ds.size()-1);

        find(ans, ds, nums, t, i+1, sum);
    }
    public static void main(String[] args){
        int[] nums={4,2,3,1,5,8,6,4,2};
        Arrays.sort(nums);
        int t=10;
        Set<List<Integer>> set=new HashSet<>();
        find(set, new ArrayList<>(), nums, t, 0, 0);
        List<List<Integer>> ans=new ArrayList<>(set);
        System.out.println(ans);
    }
}
"""
[[1, 4, 5], [2, 4, 4], [1, 3, 6], [2, 3, 5], [4, 6], [2, 2, 6], [2, 8], [1, 2, 2, 5], [1, 2, 3, 4]]
"""
```


## Kunal Kushwaha youtube channel recursion series
### problems learned & solved using recursion

* natural nums till n
* factorial of a num
* sum of digits
* print nums till n in ascending and descending order
* multiplication of digits
* nth fibonacci num
* reverse a num
* check a num is palindrome or not
* count 0s in a num
