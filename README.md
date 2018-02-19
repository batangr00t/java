# java study

## List
* uses zero based index
* allows duplicate elements and null values
* maintains the insertion order
* ListIterator can be used to traverse a List in both the directions(forward and backward) and Iterator also can be used 

### ArrayList
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

### LinkedList
* doubly-linked list implementation of the List and Deque interfaces
  * List and Deque example
  ``` java
  List<String> list = new LinkedList<>();
  Deque<String> deque = new LinkedList<>();
  ```
  * https://docs.oracle.com/javase/7/docs/api/java/util/List.html
  * https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html
* has APIs for STACK and double ended QUEUE

### Vector
* implements List
* synchronized so thread-safe
* in multi-threaded environment, use Vector class instead of ArrayList

## Set
* a collection that cannot contain duplicate elements.
* use Iterator to traverse its elements ( but not ListIterator )

### HashSet
* does not maintain any order
* allows null value but not duplicate
* non-synchronized
* better performance than TreeSet
* override equals() and hashCode() in order to detect duplication based on its value
```java
class Box {
	public String name;
	
	public Box(String s) {
		System.out.println( "created "+s );
		this.name = s;
	}
	
	@Override
	public boolean equals(Object other) {
		System.out.println( "---- Box.equals()");
		Box b = (Box)other;
		if ( name == null ) { 
			return ( b == null ) ? true : false;
		} else {
			return name.equals(b.name);
		}
	}
	
	@Override
	public int hashCode() {
		return ( name == null ) ? 0 : name.hashCode();
	}
}
```
* synchronize by 
 *
 ```java
 Set s = Collections.synchronizedSet(new HashSet(...));
 ```

### LinkedHashSet
* keeps insertion-order
* allows null value but not duplicate

### TreeSet
* orders its elements based on their values
* its element has to have compareTo() method ( implements Comparable<> )
  ```java
  class Box implements Comparable<Box> {
  	public String name;
  	@Override
	public int compareTo(Box arg0) {
		return name.compareTo(arg0.name);
	}
  }
  ```
* does not allow null value

## Map
* a collection that maps keys to values
* cannot contain duplicate keys but duplicate values

### HashMap
* map.forEach((k,v)->System.out.println(k+"=>"+v));
