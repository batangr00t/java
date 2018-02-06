# java study

## ArrayList
* allows duplicate elements and null values
* uses zero based index
* uses array data structure
* faster for searching than LinkedList ( O(1) vs O(n) ), 
* slower for adding/removing than LinkedList ( O(n) vs O(1) ) 
* grows or shrinks automatically, can reseve capacity by ensureCapacity() or constructor
* grows by half of its size ( Vector doubles the size by default )
* can be sorted by Comparator or lambda 
  * example
  ``` java
  arrayList.sort( comparator ); 
  arrayList.sort( (a,b) -> b.compareTo(a) ); )
  ```
* iterator is fail-fast ( Vector's iterator is same. but the Enumeration returned by Vector is not fail-fast ) 
* non-synchronized ( Vector is synchronized )
  * synchronize version
  ``` java
  List<String> syncArrayList = Collections.synchronizedList(new ArrayList<String>());
  CopyOnWriteArrayList<String> copyOnWriteArrayList = new CopyOnWriteArrayList<String>();
  ```
* in read only and single thread environment, ArrayList is the best choice

## LinkedList
* doubly-linked list implementation of the List and Deque interfaces
  * List and Deque example
  ``` java
  List<String> list = new LinkedList<>();
  Deque<String> deque = new LinkedList<>();
  ```
  * https://docs.oracle.com/javase/7/docs/api/java/util/List.html
  * https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html
