---
ID: 1003
post_title: C++ Generic and Containers
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/cpp/cpp-library/
published: true
post_date: 2019-04-26 13:25:19
---
<h2>C++ Library</h2>
<h3>C++ IO Library</h3>
<p>In iostream, we have,</p>
<ul>
<li>istream (input stream) type, which provides input operations</li>
<li>ostream (output stream) type, which provides output operations</li>
<li>cin, an istream object that reads the standard input</li>
<li>cout, an ostream object that writes to the standard output</li>
<li>cerr, an ostream object, typically used for program error messages, that writes to the standard error</li>
<li>The >> operator, which is used to read input from an istream object</li>
<li>The &lt;&lt; operator, which is used to write output to an ostream object</li>
<li>The getline function, which reads a line of input from a givenistream into a given string</li>
</ul>
<p>C++ also defined fstream for file and sstream for string buffer.</p>

<p>Objects of the IO types cannot be copied or assigned. Because the IO types can not be copied, functions that do IO typically pass and return the stream through references. Reading or writing an IO object changes its state, so the reference must not be const.</p>
<pre>
ofstream o1, o2;
o1 = o2;              // error: cannot assign stream objects
void print(ofstream); // error: can't initialize the ofstream parameter
o2 = print(o1);       // error: cannot copy stream objects
void print(std::ostream& c, string s) { c<<s; }
print(std::cout, "1");
</pre>



<h3>C++ Sequential Containers</h3>



<h3>C++ Generic Algorithms</h3>
<h3>C++ Associative Containers</h3>
<h3>C++ Dynamic Memory</h3>