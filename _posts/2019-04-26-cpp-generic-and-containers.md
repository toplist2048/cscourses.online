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
<p>A function template is a type-independent function that is used to generate a type-specific version at compile time. 
A template definition starts with the keyword template followed by a template parameter list. The template parameter list cannot be empty.</p>
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
<p>Except the template parameter list, the definition of a class template looks like
any other class. In the class, we can use the template parameters as types.</p>
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
<p>Template parameter can be a type parameter or a nontype parameter. If it is a type parameter, then we know
that the parameter represents a type. If it is a nontype parameter, we know it is a value.<p>
<pre>
template<typename T, int size>
</pre>
<p>The name of a template parameter can be used after it has been declared and until the end of the template definition.</p>
<p>A name used as a template parameter may not be reused within the template. The name of a template parameter can be used only once within
the same template parameter list.</p>
<p>We can declare a template without defining it.</p>
<pre>
template <class T> int compare(const T&, const T&) ;
</pre>
<p>Each template type parameter must be preceded either by the keyword class or typename ;
each nontype parameter must be preceded by a type name. The keyword typename was added to C++ as part of Standard C++, so
older programs are more likely to use the keyword class exclusively</p>
<p>We can tell the compiler to treat a member as a type by prefixing uses of the member name with the keyword typename .</p>
<pre>
tempalte <class T> 
void fun(T & t) {
  typename t::size_type *p;
}
</pre>




<h3>C++ Sequential Containers</h3>



<h3>C++ Generic Algorithms</h3>
<h3>C++ Associative Containers</h3>
<h3>C++ Dynamic Memory</h3>