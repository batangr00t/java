# java study

## ArrayList
* allows duplicate elements and null values
* use zero based index
* grows or shrinks automatically, can reseve capacity by ensureCapacity() or constructor
* grows by half of its size ( Vector doubles the size by default )
* can be sorted
* iterator is fail-fast ( Vector's iterator is same. but the Enumeration returned by Vector is not fail-fast ) 
* non-synchronized ( Vector is synchronized )
* List<String> syncArrayList = Collections.synchronizedList(new ArrayList<String>());
* CopyOnWriteArrayList<String> copyOnWriteArrayList = new CopyOnWriteArrayList<String>();

