---
ID: 1003
post_title: C++ Generic and Containers
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/cpp/cpp-generic-and-containers/
published: true
post_date: 2019-04-26 13:25:19
---
<h2>C++ Generic and Containers</h2>
<p>Generic programming writes code independent of type. </p>

<h3>C++ Templates</h3>
<p>Templates are the base of generic programming.</p>

<h4>C++ Template Definitions</h4>
<b>C++ Function Templates</b>
<p>A function template is a type-independent function that is used to generate a type-specific version at compile time. A template definition starts with the keyword template followed by a template parameter list. The template parameter list cannot be empty.</p>
<pre>
template &lt;typename T>
int compare(const T &a, const T &b) {
  if (a < b) return -1;
  if (a > b) return 1;
  return 0;
};
compare(1, 2);
compare(1.1, 2.2);
</pre>
<p>A function template can be declared inline. The specifier is placed following the template parameter list.</p>

<b>C++ Class Templates</b>
<p>In class template, we can use the template parameters as types.</p>
<pre>
template <typename T>
class Value {
  T val;
public:  
  int compare(const T &a) {
    if (val < a) return -1;
    if (val > a) return 1;
    return 0;
  }
};
Value&lt;int> v;
v.compare(1);
</pre>

<b>C++ Template Parameters</b>
<p>Template parameter can be a type parameter or a non-type parameter.<p>
<pre>
template<typename T, int size>
</pre>
<p>For scope, the name of a template parameter can be used after it has been declared and until the end of the template declaration or definition.</p>
<p>A name used as a template parameter may not be reused within the template. The name of a template parameter can be used only once within the same template parameter list.</p>
<p>We can declare a template without defining it.</p>
<pre>
template <class T> int compare(const T&, const T&) ;
</pre>
<p>Each template type parameter must be preceded either by the keyword class or typename;
each non-type parameter must be preceded by a type name. The keyword typename was added to C++ as part of Standard C++, so older programs are more likely to use the keyword class.</p>
<p>We can tell the compiler to treat a member as a type by prefixing uses of the member name with the keyword typename .</p>
<pre>
tempalte <class T> 
void fun(T & t) {
  typename t::size_type *p;
}
</pre>

<h4>C++ Template Instantiation</h4>
<p>The process of determining the types and values of the template arguments from the type of the function arguments is called template argument deduction. Each instantiation of a class template constitutes an independent
class type.</p>
<p>A template type parameter may be used more than one function parameter. In
such cases, it must generate the same template argument type for each function argument.</p>

<h4>C++ Template Compilation</h4>
<p>When the compiler sees a template definition, it does not generate code immediately. The compiler
produces type-specific instances only when it sees a use of the template.</p>

<h3>C++ Sequential Containers</h3>
<b>Sequential Containers</b>
<ul>
<li>vector - Supports fast random access</li>
<li>list - Supports fast insertion/deletion</li>
<li>deque - Double-ended queue</li>
</ul>

<b>Sequential Container Adaptors</b>
<ul>
<li>stack Last in/First out stack</li>
<li>queue First in/First out queue</li>
<li>priority_queue Priority-managed queue</li>
</ul>

<b>Operations that add elements to a sequential container</b>
<ul>
<li>c.push_back(t) - Adds element with value t to the end of c. Returns void.</li>
<li>c.push_front(t) - Adds element with value t to front of c. Returns void. Valid only for list or deque.</li>
<li>c.insert(p,t) - Inserts element with value t before the element referred to by iterator p. Returns an iterator referring to the element that was added.</li>
<li>c.insert(p,n,t) - Inserts n elements with value t before the element referred to by iterator p. Returns void .</li>
<li>c.insert(p,b,e) - Inserts elements in the range denoted by iterators b and e before the element referred to by iterator p. Returns void.</li>
</ul>

<b>Sequential Container Size Operations</b>
<ul>
<li>c.size() - Returns the number of elements in c. Return type is c::size_type.</li>
<li>c.max_size() - Returns maximum number of elements c can contain. Return type is c::size_type.</li>
<li>c.empty() - Returns a bool that indicates whether size is 0 or not.</li>
<li>c.resize(n) - Resize c so that it has n elements. If N < c.size(), the excess elements are discarded. If new elements must be added, they are value initialized. </li>
<li>c.resize(n,t) - Resize c to have n elements. Any elements added have value t.</li>
</ul>

<b>Operations to Access Elements in a Sequential Container</b>
<ul>
<li>c.back() - Returns a reference to the last element in c. Undefined if c is empty.</li>
<li>c.front() - Returns a reference to the first element in c. Undefined if c is empty.</li>
<li>c[n] - Returns a reference to the element indexed by n. Undefined if n <0 or n >= c.size(). Valid only for vector and deque .</li>
<li>c.at(n) - Returns a reference to the element indexed by n. If index is out of range, throws out_of_range exception. Valid only for vector and deque.</li>
</ul>

<b>Operations to Remove Elements from a Sequential Container</b>
<ul>
<li>c.erase(p) - Removes element referred to by the iterator p. Returns an iterator referring to the element after the one deleted, or an off-the-end iterator if p referred to the last element. Undefined if p is an off-the-end iterator.</li>
<li>c.erase(b,e) - Removes the range of elements denoted by the iterators b and e. Returns an iterator referring after the last one in the range that was deleted, or an off-the-end iterator if e is itself an off-the-end iterator.</li>
<li>c.clear() Removes all the elements in c. Returns void. </li>
<li>c.pop_back() Removes the last element in c. Returns void . Undefined if c is empty.</li>
<li>c.pop_front() Removes the first element in c. Returns void . Undefined if c is empty. Valid only for list or deque.</li>
</ul>

<b>Sequential Container Assignment Operations</b>
<ul>
<li>c1 = c2 - Deletes elements in c1 and copies elements from c2 into c1 . c1 and c2 must be the same type.</li>
<li>c1.swap(c2) - Swaps contents: After the call c1 has elements that were in c2 , and c2 has elements that were in c1 . c1 and c2 must be the same type. Execution time usually much faster than copying elements from c2 to c1.</li>
<li>c.assign(b,e) - Replaces the elements in c by those in the range denoted by iterators b and e . The iterators b and e must not refer to elements in c.</li>
<li>c.assign(n,t) - Replaces the elements in c by n elements with value t.</li>
</ul>

<b>Operations Supported by the Stack Container Adaptor</b>
<ul>
<li>s.empty() - Returns TRue if the stack is empty; false otherwise.</li>
<li>s.size() - Returns a count of the number of elements on the stack.</li>
<li>s.pop() - Removes, but does not return, the top element from the stack.</li>
<li>s.top() - Returns, but does not remove, the top element on the stack.</li>
<li>s.push(item) - Places a new top element on the stack.</li>
</ul>

<b>Operations Supported by Queues and Priority Queues</b>
<ul>
<li>q.empty() Returns TRue if the queue is empty; false otherwise.</li>
<li>q.size() Returns a count of the number of elements on the queue.</li>
<li>q.pop() Removes, but does not return, the front element from the queue.</li>
<li>q.front() Returns, but does not remove, the front element on the queue. This operation can be applied only to a queue .</li>
<li>q.back() Returns, but does not remove, the back element on the queue. This operation can be applied only to a queue.</li>
<li>q.top() Returns, but does not remove, the highest-priority element. This operation can be applied only to a priority_queue.</li>
<li>q.push(item) Places a new element at the end of the queue or at its appropriate position based on priority in a priority_queue.</li>
</ul>


<h3>C++ Associative Containers</h3>
<h3>C++ Generic Algorithms</h3>