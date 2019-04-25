---
ID: 998
post_title: C++ Classes
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/cpp/cpp-classes/
published: true
post_date: 2019-04-25 19:19:02
---
<h2>C++ Classes</h2>
<p>The ideas behind classes are data abstraction and encapsulation.
Data abstraction separates interface and implementation. The interface consists of
the operations that users can execute. The implementation includes data members, the bodies of the functions. Encapsulation enforces the separation of a class’ interface and implementation. Users can use the interface but have no access to the implementation.</p>
<h3>C++ Class Constructors</h3>
<p>Class constructors control object initialization. Classes control default initialization by defining the default constructor. The default constructor takes no arguments. The compiler generates a default constructor automatically only if a class declares no constructors.</p>
<b>C++ Class Constructor Initializer List</b>
<p>A constructor initializer list specifies initial values for one or more data members of the object being created. The constructor initializer is a list of member names, each of
which is followed by that member’s initial value in parentheses (or inside curly
braces). Multiple member initializations are separated by commas.</p>
<pre>
Person(const std::string &name, const unsigned age): name(name), age(age)) { }
</pre>
<b>C++ Class Copy, Assignment, and Destruction</b>
<p>In C++, the compiler will synthesize the copy, assignment, and destruction operations
for us. It is important to understand that for some classes the default versions do not
behave appropriately. In particular, the synthesized versions are unlikely to work
correctly for classes that allocate resources that reside outside the class objects
themselves.</p>
<b>C++ Access Control</b>
<ul>
<li>Public - Members defined after a public specifier are accessible to all parts of the
program. The public members define the interface to the class.</li>
<li>Private - Members defined after a private specifier are accessible to the member
functions of the class but are not accessible to code that uses the class. The
private sections encapsulate the implementation.</li>
<li>
</ul>
<p>The only difference between struct and class is the default access level. If we use the struct keyword, the members defined before the first access specifier are public; if we use class, then the members are private.</p>

<b>C++ Friends</b>
<p>A class can allow another class or function to access its nonpublic members by
making that class or function a friend. A class makes a function its friend by including
a declaration for that function preceded by the keyword friend:</p>

<b>C++ inline Functions</b>
<p>Member functions defined inside the class are automatically inline. We can explicitly declare a member function as inline as part of its declaration inside the class body. Alternatively, we can specify inline on the function definition that appears outside the class body.</p>

<b>C++ mutable Data Members</b>
<p>It sometimes (but not very often) happens that a class has a data member that we
want to be able to modify, even inside a const member function. We indicate such
members by including the mutable keyword in their declaration.</p>

<b>C++ Functions That Return *this</b>
<p>Functions that return a reference are lvalues, which means that they return the object itself, not a copy of the object.</p>
<p>A const member function that returns *this as a reference should have a return type that is a reference to const.</p>