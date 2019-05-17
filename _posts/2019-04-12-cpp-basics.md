---
ID: 930
post_title: C++ Basics
author: admin
post_excerpt: ""
layout: post
permalink: https://cscourses.online/cpp/cpp-basics/
published: true
post_date: 2019-04-12 16:41:08
---
<h2> C++ Basics</h2>
<p>In this part, we will cover basic components in C++ language.</p>

<h3>C++ Types and Variables</h3>
<p>Everything has a type. Types tell us what our data mean, and what operation can be performed on the data. Some types are built-in in the languages, called primitive types.</p>

<h4>C++ Primitive Types</h4>
<p>Below are basic data types in C++:</p>
<ul>
<li>void, no value</li>
<li>bool, boolean</li>
<li>char, character, one byte</li>
<li>wchar_t, wilder character, two bytes</li>
<li>short, short integer, smaller size than int</li>
<li>int, integer, the natural size of integers on the host machine</li>
<li>long, long integer, bigger size than int</li>
<li>float, single-precision floating point, smaller size than double</li>
<li>double, double-precision floating point, the natural size of floating number on the host machine</li>
<li>long double, extended-precision floating point, bigger size than double</li>
</ul>
<p>C qualifiers can be applied to these basic types. short and long are actually qualifiers applied to integers. long also applied to double. The qualifier signed or unsigned may be applied to char or integer. unsigned numbers are always positive or zero, while signed numbers may be negative.</p>
<p>The size of the primitive types varies across machines. By size, we mean the number of bytes used to represent the type. The standard guarantees a minimum size for each of the primitive types, and compilers may use a larger size than is strictly required. We can use sizeof() to check the size of date types.</p>
<pre>cout &lt;&lt; "Size of void is " &lt;&lt; sizeof(void) &lt;&lt; endl; 
cout &lt;&lt; "Size of bool is " &lt;&lt; sizeof(bool) &lt;&lt; endl; 
cout &lt;&lt; "Size of char is " &lt;&lt; sizeof(char) &lt;&lt; endl; 
cout &lt;&lt; "Size of wchar_t is " &lt;&lt; sizeof(wchar_t) &lt;&lt; endl; 
cout &lt;&lt; "Size of short is " &lt;&lt; sizeof(short) &lt;&lt; endl; 
cout &lt;&lt; "Size of int is " &lt;&lt; sizeof(int) &lt;&lt; endl; 
cout &lt;&lt; "Size of long is " &lt;&lt; sizeof(long) &lt;&lt; endl; 
cout &lt;&lt; "Size of float is " &lt;&lt; sizeof(float) &lt;&lt; endl; 
cout &lt;&lt; "Size of double is " &lt;&lt; sizeof(double) &lt;&lt; endl; 
cout &lt;&lt; "Size of long double is " &lt;&lt; sizeof(long double) &lt;&lt; endl;</pre>

<p>The result is machine dependent,</p>
<pre>Size of void is 1 
Size of bool is 1 
Size of char is 1 
Size of wchar_t is 4 
Size of short is 2 
Size of int is 4 
Size of long is 8 
Size of float is 4 
Size of double is 8 
Size of long double is 16</pre>
<p>Notice the compiler warns about we apply sizeof on void type.</p>

<b>C++ Type Conversions</b>
<p>Below are type conversion rules,</p>
<ul>
<li>When we assign one of the none-bool arithmetic types to a bool object, the result is false if the value is 0 and true otherwise.</li>
<li>When we assign a bool to one of the other arithmetic types, the resulting value is 1 if the bool is true and 0 if the bool is false.</li>
<li>When we assign a floating-point value to an object of integral type, the value is truncated. The value that is stored is the part before the decimal point.</li>
<li>When we assign an integral value to an object of floating-point type, the fractional part is zero. Precision may be lost if the integer has more bits than the
floating-point object can accommodate.</li>
<li>If we assign an out-of-range value to an object of unsigned type, the result is the remainder of the value modulo the number of values the target type can
hold. For example, an 8-bit unsigned char can hold values from 0 through 255, inclusive. If we assign a value outside this range, the compiler assigns the
remainder of that value modulo 256. Therefore, assigning –1 to an 8-bit unsigned char gives that object the value 255. </li>
<li>If we assign an out-of-range value to an object of signed type, the result is undefined. The program might appear to work, it might crash, or it might
produce garbage values.</li>
</ul>

<b>C++ Literals</b>
<p>In C++, there are some prefix to specify the type of character and character string literals.</p>
<ul>
<li>Prefix u, Unicode 16 character, char16_t</li>
<li>Prefix U, Unicode 32 character, char32_t</li>
<li>Prefix L, wide character, wchar_t</li>
<li>Prefix u8, utf-8 (string literal only), char</li>
</ul>
<p>Also some suffix to specify the type of integer or floating-point literals.</p>
<ul>
<li>Suffix u or U, means unsigned</li>
<li>Suffix l or L, means long</li>
<li>Suffix ll or LL, means long long</li>
<li>Suffix f or F, means float</li>
<li>Suffix l or L, means long double</li>
</ul>

<b>C++ Escape Sequence</b>
<ul>
<li>newline, \n </li>
<li>horizontal tab, \t </li>
<li>alert (bell), \a</li>
<li>vertical tab, \v </li>
<li>backspace, \b </li>
<li>double quote, \"</li>
<li>backslash, \\ </li>
<li>question mark, \? </li>
<li>single quote, \'</li>
<li>carriage return, \r </li>
<li>formfeed, \f</li>
</ul>

<h4>Variables</h4>
<p>A variable definition consists of a type specifier, followed by a list of one or
more variable names separated by commas, and ends with a semicolon.</p>
<p>An variable can be initialized to a value when it is created. The
values can be expressions.  Initialization is not assignment. Initialization happens 
when a variable is created. Assignment replaces current value with a new one.</p>
<p>Using curly braces for initialization is called list initialization. 
When used with variables of built-in type, list initialization has one
important property: The compiler will not let us list initialize variables of built-in type if
the initializer might lead to the loss of information:</p>
<pre>int a = 0;
int b{0};</pre>
<p>A declaration makes a name known to the program. A file that wants to
use a name defined elsewhere includes a declaration for that name. A definition
creates the associated entity.</p>
<p>Identifiers in C++ can be composed of letters, digits, and the underscore character.
The language imposes no limit on name length. Identifiers must begin with either a
letter or an underscore. Identifiers are case-sensitive; upper- and lowercase letters are
distinct.</p>
<h4>C++ Compound Types</h4>
<b>C++ References</b>
<p>A reference defines an alternative name for an object. A reference type "refers to"
another type. A reference is not an object. Instead, a reference is just another name for an
already existing object.</p>
<pre>int ival = 1024;
int &refVal = ival;
</pre>
<b>C++ Pointers</b>
<p>A pointer is a compound type that “points to” another type. Like references, pointers
are used for indirect access to other objects. Unlike a reference, a pointer is an object
in its own right. Pointers can be assigned and copied; a single pointer can point to
several different objects over its lifetime. Unlike a reference, a pointer need not be
initialized at the time it is defined. </p>
<p>Pointers are often hard to understand. Uninitialized pointers are a common source of run-time errors.
Debugging problems due to pointer errors bedevil even experienced programmers</p>
<p>The value (i.e., the address) stored in a pointer can be in one of four states,</p>
<ul>
<li>It can point to an object.</li>
<li>It can point to the location just immediately past the end of an object.</li>
<li>It can be a null pointer, indicating that it is not bound to any object. 
A null pointer does not point to any object. Code can check whether a pointer is null
before attempting to use it.</li>
<li>It can be invalid; values other than the preceding three are invalid.</li>
</ul>
<p>We may dereference only a valid pointer that points to an object.</p>
<p>The type void* is a special pointer type that can hold the address of any object. Like
any other pointer, a void* pointer holds an address, but the type of the object at
that address is unknown.</p>

<h4>C++ const Qualifier</h4>
<p>We can make a variable unchangeable by defining the variable’s type as const</p>
<p>By default, const variables are local to a file. </p>
<p>A reference to const is a reference that refers to a const type.
A reference to const cannot be used to change the object to which the reference is bound.
A reference to const restricts only what we can do through that reference. 
Binding a reference to const to an object says nothing about
whether the underlying object itself is const. Because the underlying object might be
nonconst, it might be changed by other means:</p>
<p>A pointer to const may not be used to change the object to which the pointer points. 
We may store the address of a const object only in a pointer to const.</p>
<pre>
const int a = 1;
int *ptr = &a; // error: ptr is a plain pointer
const int *cptr = &a; // ok: cptr may point to a int that is const
*cptr = 2; // error: cannot assign to *cptr
</pre>
<p>A const pointer must be initialized, and once initialized, its value may
not be changed. We indicate that the pointer is const by putting the const after the
*. This placement indicates that it is the pointer, not the pointed-to type, that is
const.</p>
<p>A constant expression is an expression whose value cannot change and that can be
evaluated at compile time. A literal is a constant expression. A const object that is
initialized from a constant expression is also a constant expression.
We can ask the compiler to verify that a variable is a
constant expression by declaring the variable in a constexpr declaration. Variables
declared as constexpr are implicitly const and must be initialized by constant
expressions</p>

<h4>C++ Types</h4>
<p>A type alias is a name that is a synonym for another type. Type aliases let us
simplify complicated type definitions, making those types easier to use.</p>
<p>We can define a type alias in one of two ways. We use a typedef, or 
we can use alias declaration. An alias declaration starts with the keyword 
using followed by the alias name and an =.
</p>
<pre>
typedef int aname;
using aName = int;
</pre>
<p>we can let the compiler figure out the type for us by using the auto type specifier.</p>
<pre>auto b = 1;</pre>
<p>The decltype returns the type of its operand. The compiler analyzes the expression to determine its
type but does not evaluate the expression.</p>
<pre>
int a = 1;
int b = 2;
decltype(a+b) c = 3; // c has whatever type a+b has
auto x = foo();                           // more concise than 'decltype(foo()) x'
std::vector<decltype(foo())> v{ foo() };  // cannot use 'auto'</pre>

<h3>C++ Strings, Vectors, and Iterators</h3>
<p>A using declaration lets us use a name from a namespace without qualifying the
name with a namespace_name:: prefix. A using declaration has the form using namespace::name;</p>
<pre>using std:cin;</pre>

<h4>C++ Strings</h4>
<p>A string is a variable-length sequence of characters.</p>
<b>Ways to Initialize a C++ string</b>
<ul>
<li>string s1; - Default constructor; s1 is the empty string</li>
<li>string s2(s1); - Initialize s2 as a copy of s1</li>
<li>string s3("value"); - Initialize s3 as a copy of the string literal</li>
<li>string s4(n, 'c'); - Initialize s4 with n copies of the character 'c'</li>
</ul>
<p>Note for compatibility with C, character string literalsare not the same type as the standard library string type. </p>
<b>C++ string Operations</b>
<ul>
<li>cout << s; - Write string s into output stream cout, return cout</li>
<li>cin >> s; - Read whitespace-separated string from imput stream cin into s, return cin</li>
<li>getline(cin, s) - Read a line from input cin into s, return cin</li> 
<li>s.empty() - Returns true if s is empty; otherwise returns falses.</li>
<li>size() - Returns number of characters in s, returns type is string::size_type</li>
<li>s[n] - Returns the character at position n in s; positions start at 0.</li>
<li>s1 + s2 - Returns a string equal to the concatenation of s1 and s2</li>
<li>s1 = s2 - Replaces characters in s1 by a copy of s2</li>
<li>v1 == v2 - Returns true if v1 and v2 are equal; false otherwise</li>
<li>!=, <, <= ,>, and >= - Have their normal meanings</li>
</ul>

<b>C++ string Character Operations</b>
<p>Below are functions to process the individual characters of a string.</p>
<ul>
<li>isalnum(c) - true if c is a letter or a digit.</li>
<li>isalpha(c) - true if c is a letter.</li>
<li>iscntrl(c) - true if c is a control character.</li>
<li>isdigit(c) - true if c is a digit.</li>
<li>isgraph(c) - true if c is not a space but is printable.</li>
<li>islower(c) - true if c is a lowercase letter.</li>
<li>isprint(c) - true if c is a printable character.</li>
<li>ispunct(c) - true if c is a punctuation character.</li>
<li>isspace(c) - true if c is whitespace.</li>
<li>isupper(c) - true if c is an uppercase letter.</li>
<li>isxdigit(c) - true if c is a hexadecimal digit.</li>
<li>tolower(c) - If c is an uppercase letter, returns its lowercase equivalent; otherwise returns c unchanged.</li>
<li>toupper(c) - If c is a lowercase letter, returns its uppercase equivalent; otherwise returns c unchanged.</li>
</ul>

<h4>C++ Vectors</h4>
<p>A vector is a collection of objects, all of which have the same type. A vectoris a class template. </p>
<pre>
#include <vector>
using std::vector;</pre>
<b>Defining and Initializing C++ vectors</b>
<ul>
<li>vector<T> v1; - vector that holds objects of type T; Default constructor v1 is empty</li>
<li>vector<T> v2(v1); - v2 is a copy of v1</li>
<li>vector<T> v3(n, i); - v3 has n elements with value i</li>
<li>vector<T> v4(n); - v4 has n copies of a value-initialized object</li>
<li>vector<T> v5 {a, b, c}; - v5 has a value initializer list</li>
<li>vector<T> v6 = {a, b, c}; - v6 has a value initializer list</li>
</ul>
<p>Vectors grow dynamically at runtime.</p>

<b>C++ vectors Operations</b>
<ul>
<li>v.empty() - Returns true if v is empty; otherwise returns false</li>
<li>v.size() - Returns number of elements in v</li>
<li>v.push_back(t) - Adds element with value t to end of v</li>
<li>v[n] - Returns element at position n in v</li>
<li>v1 = v2 - Replaces elements in v1 by a copy of elements in v2</li>
<li>v1 == v2 - Returns TRue if v1 and v2 are equal</li>
<li>!=, <, <= ,>, and >= - Have their normal meanings</li>
</ul>

<h4>C++ Iterators</h4>
<p>The iterator returned by begin denotes the first element. The iterator returned by end is an iterator positioned “one past the end”. This iterator denotes a non existent element “off the end” of the container. If the container is empty, begin returns the same iterator as the one returned by end.</p>
<pre>
auto b = v.begin(), e = v.end();
</pre>
<b>C++ Iterator Operations</b>
<ul>
<li>*iter - Return a reference to the element denoted by the iterator iter.</li>
<li>iter->member， (*iter).memter - Return the element memeber</li>
<li>++iter, --iter - Iterator arithmetic</li>
<li>iter1 == iter2, iter1 != iter2 -  Iterator comparation</li>
</ul>