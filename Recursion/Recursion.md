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
