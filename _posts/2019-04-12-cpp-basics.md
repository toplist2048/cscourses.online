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

<h3>C++ Basic Types, Operators, and Expressions</h3>
<p>Everything has a type. Types tell us what our data mean, and what operation can be performed on the data. Some types are built-in in the languages, called primitive types.</p>

<h3>C++ Primitive Types</h3>
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