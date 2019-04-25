---
ID: 990
post_title: Java Generics and Collections
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/java/java-generics-and-collections/
published: true
post_date: 2019-04-25 15:18:45
---
<h2>Java Generics and Collections</h2>

<h3>Java Collections</h3>
<p>A collection is a group of objects contained in a single object. The Java Collections Framework includes classes that implement List, Map, Queue, and Set.</p>
<p>Notice that Map doesn’t implement the Collection interface. It is considered part of the Java Collections Framework, even though it isn’t technically a Collection. It is a collection (note the lower-case), though, in that it contains a group of objects. The reason why maps are treated differently is that they need different methods due to being key/value pairs.</p>

<b>Comparing Collection Types</b>
<table>
<thead>
<tr><td>Type</td><td>Can contain duplicate elements?</td><td>Elements ordered?</td><td>Has keys and values?</td><td>Must add/remove in specific order?</td></tr>
</thead>
<tbody>
<tr><td>List</td><td>Yes</td><td>Yes (by index)</td><td>No</td><td>No</td></tr>
<tr><td>Map</td><td>Yes (for values)</td><td>No</td><td>Yes</td><td>No</td></tr>
<tr><td>Queue</td><td>Yes</td><td>Yes (retrieved in defined order)</td><td>No</td><td>Yes</td></tr>
<tr><td>Set</td><td>No</td><td>No</td><td>No</td><td>No</td></tr>
</tbody>
</table>

<h4>Java Lists</h4>
<b>Java List Methods</b>
<ul>
<li>void add(E element) - Adds element to end</li>
<li>void add(int index, E element) - Adds element at index and moves the rest toward the end</li>
<li>E get(int index) - Returns element at index</li>
<li>int indexOf(Object o) - Returns first matching index or -1 if not found</li>
<li>int lastIndexOf(Object o) - Returns last matching index or -1 if not found</li>
<li>void remove(int index) - Removes element at index and moves the rest toward the front</li>
<li>E set(int index, E e) - Replaces element at index and returns original</li>
</ul>

<h4>Java Sets</h4>
<p>A HashSet stores its elements in a hash table. This means that it uses the hashCode()
method of the objects to retrieve them more efficiently.</p>
<p>A TreeSet stores its elements in a sorted tree structure. The main benefit is that the set
is always in sorted order. The tradeoff is that adding and checking if an element is present are both O(log n).</p>

<p>TreeSet implements the NavigableSet interface. This interface provides some interesting methods. Their method signatures are as follows:</p>
<ul>
<li>E lower(E e) - Returns greatest element that is < e, or null if no such element</li>
<li>E floor(E e) - Returns greatest element that is <= e, or null if no such element</li>
<li>E ceiling(E e) - Returns smallest element that is >= e, or null if no such element</li>
<li>E higher(E e) - Returns smallest element that is > e, or null if no such element</li>
</ul>

<h4>Java Queues</h4>
<p>An ArrayDeque is a “pure” double-ended queue. The main benefit of an ArrayDeque is that it is more efficient than a LinkedList.</p>
<ul>
<li>boolean add(E e) - Adds an element to the back of the queue and returns true or throws an exception</li>
<li>E element() - Returns next element or throws an exception if empty queue</li>
<li>boolean offer(E e) - Adds an element to the back of the queue and returns whether successful</li>
<li>E remove() - Removes and returns next element or throws an exception if empty queue</li>
void push(E e) - Adds an element to the front of the queue</li>
<li>E poll() - Removes and returns next element or returns null if empty queue</li>
<li>E peek() - Returns next element or returns null if empty queue</li>
<li>E pop() - Removes and returns next element or throws an exception if empty queue</li>
</ul>

<h4>Java Maps</h4>
<p>A HashMap stores the keys in a hash table. This means that it uses the hashCode() method
of the keys to retrieve their values more efficiently.</p>
<p>A TreeMap stores the keys in a sorted tree structure. The main benefit is that the keys are
always in sorted order. The tradeoff is that adding and checking if a key is present are both
O(log n).</p>
<p>Map methods</p>
<ul>
<li>void clear() - Removes all keys and values from the map.</li>
<li>boolean isEmpty() - Returns whether the map is empty.</li>
<li>int size() - Returns the number of entries (key/value pairs) in the map.</li>
<li>V get(Object key) - Returns the value mapped by key or null if none is mapped.</li>
<li>V put(K key, V value) - Adds or replaces key/value pair. Returns previous value or null.</li>
<li>V remove(Object key) - Removes and returns value mapped to key. Returns null if none.</li>
<li>boolean containsKey(Object key) - Returns whether key is in map.</li>
<li>boolean containsValue(Object) - Returns value is in map.</li>
<li>Set<K> keySet() - Returns set of all keys.</li>
<li>Collection<V> values() - Returns Collection of all values.</li>
</ul>