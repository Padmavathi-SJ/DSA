## TreeMap

* To get a sorted map.
* If we are using a TreeMap, by default in this key are in sorted by ascending order, if wants to sort by values we can use **sortByValue** map function
* We can sort a TreeMap by values in both **Ascending** and **Descending**


### sorting by values.
```
Map<Character, Integer> map = new TreeMap<>();
 map.put('a', 5);
        map.put('b', 2);
        map.put('c', 8);
        map.put('d', 3);
Map<Character, Integer> sortedAsce = new sortByValue(map, true); //true --> for sorting in ascending order

Map<Character, Integer> sortedDesc = new sortByValue(map, false); // false --> to sort in descending order

```
