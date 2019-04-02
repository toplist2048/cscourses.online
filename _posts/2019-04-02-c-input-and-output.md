---
ID: 881
post_title: C Input and Output
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/c/c-input-and-output/
published: true
post_date: 2019-04-02 15:06:46
---
<h2>C Input and Output</h2>
<h3>C Standard Input and Output</h3>
<p>The simplest input mechanism is to read one character at a time from the standard input, normally the keyboard, with getchar: <code>int getchar(void)</code>.</p>
<p>The function <code>int putchar(int)</code> is used for output: putchar (c) puts the character c on the standard output, which is by default the screen.</p>
<p>Each source file that refers to an input/output library function must contain the line <code>#include <stdio.h></code>.</p>

<h3>C Formatted Output- Printf</h3>
<p>The output function printf translates internal values to characters,</p>
<pre>int printf (char *format, arg c , arg2, ... )</pre>

<p>The format string contains two types of objects: ordinary characters, which are copied to the output stream, and conversion specifications, each of which causes conversion and printing of the next successive argument to printf. Each conversion specification begins with a % and ends with a conversion character. Between the % and the conversion character there may be, in order:</p>
<ul>
<li>A minus sign, which specifies left adjustment of the converted argument.</li>
<li>A number that specifies the minimum field width. The converted argument will be printed in a field at least this wide. If necessary it will be padded on the left (or right, if left adjustment is called for) to make up the field width.</li>
<li>A period, which separates the field width from the precision.</li>
<li>A number, the precision, that specifies the maximum number of characters to be printed from a string, or the number of digits after the decimal point of a floating point value, or the minimum number of digits for an integer.</li>
<li>An h if the integer is to be printed as a short,or I (letter ell) if as a long.</li>
</ul>
<p>Basic Print Conversions</p>
<table>
<thead>
<tr><td>Character</td><td>Argument Type</td><td>Printed As</td></tr>
</thead>
<tbody>
<tr><td>d,i</td><td>int</td><td>decimal number.</td></tr>
<tr><td>o</td><td>int</td><td>unsigned octal number (without a leading zero).</td></tr>
<tr><td>x, X</td><td>int</td><td>unsigned hexadecimal number (without a leading Ox or OX),using abcdef or ABCDEF for 10, ..., 15.</td></tr>
<tr><td>u</td><td>int</td><td>unsigned decimal number.</td></tr>
<tr><td>c</td><td>int</td><td>single character.</td></tr>
<tr><td>s</td><td>char *</td><td>print characters from the string until a '\0' or the number of characters given by the precision.</td></tr>
<tr><td>f</td><td>double</td><td>[-1m.dddddd, where the number of d's is given by the precision (default 6).</td></tr>
<tr><td>e,E</td><td>double</td><td>[-1m.dddddde±xx or [-1m.ddddddE±XX, where the number of d's is given by the precision (default 6).</td></tr>
<tr><td>g,G</td><td>double</td><td>use %e or %E if the exponent is less than -4 or greater than or equal to the precision; otherwise use %f. Trailing zeros and a trailing decimal point are not printed.</td></tr>
<tr><td>p</td><td>void *</td><td>pointer (implementation-dependent representation).</td></tr>
<tr><td>%</td><td>no argument is converted</td><td>print a %.</td></tr>
</tbody>
</table>

<h3>C Variable-length Argument Lists</h3>
<p>The declaration ... means that the number and types of these arguments may vary, <code>int minprintf(char *fmt, ...)</code></p>
<p>The type va_list is used to declare a variable that will refer to each argument in turn; in minprintf, this variable is called ap, for "argument pointer."
The macro va_start initializes ap to point to the first unnamed argument. It must be called once before ap is used. There must be at least one named argument;
the final named argument is used by va_start to get started. Each call of va_arq returns one argument and steps ap to the next; va_arq uses a type name to determine what type to return and how big a step to take. Finally, va_end does whatever cleanup is necessary. It must be called before the function returns.</p>
<pre>
void minprintf(char *fmt, ...) {
  va_list ap; // points to each unnamed arg in turn
  char *p, *sval;
  int ivaI;
  double dval;

  va_start(ap, fmt) // make ap point to 1st unnamed arg
  for (p = fmt; *p; p++) {
    ...
    ivaI = va_arg(ap, int);
    ...
    dval = va_arg(ap, double);
    ...
  }
  va_end(ap) ; // clean up when done
}
</pre>

<h3>C Formatted Input-Scanf</h3>
<p>The scanf reads characters from the standard input, interprets them according to the specification in format, and stores the results through the remaining arguments.</pre>
<pre>int sscanf (char *strinq, char *£ormat, arg), arg2, ... )</pre>
<p>The format string may contain:</p>
<ul>
<li>Blanks or tabs, which are ignored.</li>
<li>Ordinary characters (not %), which are expected to match the next non-white space character of the input stream.</li>
<li>Conversion specifications, consisting of the character '" an optional assignment suppression character *, an optional number specifying a maximum field width, an optional h, 1, or L indicating the width of the target, and a conversion character.</li>
</ul>
<p>Basic Scanf Conversions</p>
<table>
<thead>
<tr><td>Character</td><td>Input Data</td><td>Argument Type</td></tr>
</thead>
<tbody>
<tr><td>d</td><td>decimal integer</td><td>int *.</td></tr>
<tr><td>i</td><td>integer</td><td>int *. The integer may be in octal (leading 0) or hexadecimal (leading Ox or OX).</td></tr>
<tr><td>o</td><td>octal integer (with or without leading zero)</td><td>int *.</td></tr>
<tr><td>u</td><td>unsigned decimal integer</td><td>unsigned int *.</td></tr>
<tr><td>x</td><td>hexadecimal integer (with or without leading Ox or OX)</td><td>int *.</td></tr>
<tr><td>c</td><td>characters</td><td>char *. The next input characters (default 1) are placed at the indicated spot. The normal skip over white space is suppressed; to read the next non-white space character, use %1s.</td></tr>
<tr><td>s</td><td>character string (not quoted)</td><td>char *, pointing to an array of characters large enough for the string and a terminating , \0' that will be added.</td></tr>
<tr><td>e, f, q</td><td>floating-point number with optional sign, optional decimal point and optional exponent</td><td>float *.</td></tr>
<tr><td>%</td><td>literal %</td><td>no assignment is made.</td></tr>
</tbody>
</table>