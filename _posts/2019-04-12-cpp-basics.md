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
<pre>decltype(f()) ret = x; // ret has whatever type f returns</pre>