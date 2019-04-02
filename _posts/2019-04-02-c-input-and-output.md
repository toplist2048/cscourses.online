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
<tr><td>s</td><td>character string (not quoted)</td><td>char *, pointing to an array of characters large enough for the string and a terminating , '\0' that will be added.</td></tr>
<tr><td>e, f, q</td><td>floating-point number with optional sign, optional decimal point and optional exponent</td><td>float *.</td></tr>
<tr><td>%</td><td>literal %</td><td>no assignment is made.</td></tr>
</tbody>
</table>
<pre>
double v;
scanf("%lf", &v);
</pre>
<h3>C File Access</h3>
<p>File has to be opened by the library function fopen. fopen takes an external name like x.c or y.c, does some housekeeping and negotiation with the operating system (details of which needn't concern us), and returns a pointer to be used in subsequent reads or writes of the file.</p>
<h3>C Error Handllng - Stderr and Exit</h3>
<p>Output written on stderr normally appears on the screen even if the standard output is redirected.</p>

<h3>C Line Input and Output</h3>
<pre>
char *fgets(char *line, int maxline, FILE *fp)
int fputs(char *line, FILE *fp)
</pre>

<h3>C Miscellaneous Functions</h3>
<b>C String Operations</b>
<ul>
<li>strcat(s,t) - concatenate t to end of s</li>
<li>strncat(s,t,n) - concatenate n characters of t to end of s</li>
<li>strcmp(s,t) - return negative, zero, or positive for s < t,s =::= t,or s > t</li>
<li>strncmp(s,t,n) - same as strcmp but only in first n characters</li>
<li>strcpy(s,t) - copy t to s</li>
<li>strncpy(s,t,n) - copy at most n characters of t to s</li>
<li>strlen(s) - return length of</li>
<li>st.bhr(s,c) - return pointer to first c in s, or NULL if not present</li>
<li>strrchr(s,c) - return pointer to last c in s, or NULL if not present</li>
</ul>

<b>C Character Class Testing and Conversion</b>
<ul>
<li>isalpha(c) - non-zero if c is alphabetic, 0 if not</li>
<li>isupper(c) - non-zero if c is upper case, 0 if not</li>
<li>islower(c) - non-zero if c is lower case, 0 if not</li>
<li>isdigit(c) - non-zero if c is digit, 0 if not</li>
<li>isalnum(c) - non-zero if isalpha(c)or isdigit(c),0 if not</li>
<li>isspace(c) - non-zero if c is blank, tab, newline, return, formfeed, vertical tab</li>
<li>toupper(c) - return c converted to upper case</li>
<li>tolower(c) - return c converted to lower case</li>
</ul>

<h3>C Ungetc</h3>
<p><code>int ungetc(int c, FILE *fp)</code> pushes the character c back onto file fp, and returns either c, or EOF for an error.</p>

<h3>C Command Execution</h3>
<p>The function <code>system(char *s)</code> executes the command contained in the character string s, then resumes execution of the current program</p>

<h3>C Storage Management</h3>
<p>The functions malloc and calloc obtain blocks of memory dynamically</p>
<pre>
void *malloc(size_t n)
void *calloc(size_t n, size_t size)
</pre>

<h3>C Mathematical Functions</h3>
<ul>
<li>sin(x) - sine of x, x in radians</li>
<li>cos(x) - cosine of x, x in radians</li>
<li>atan2(y,x) - arctangent of y Ix, in radians</li>
<li>exp(x) - exponential function e<sup>x</sup></li>
<li>log(x) - natural (base e) logarithm of x (x> 0)</li>
<li>log10(x) - common (base 10) logarithm of x (x> 0)</li>
<li>pow(x,y) - x<sup>y</sup></li>
<li>sqrt(x) - square root of x (x>=O)</li>
<li>fabs(x) - absolute value of x</li>
</ul>

<h3>C Random Number Generation</h3>
<p>The function rand() computes a sequence of pseudo-random integers in the range zero to RAND_MAX.</p>
<p>The function srand(unsigned) sets the seed for rand.</p>

<h2>C The UNIX System Interface</h2>
<p>Forget about UNIx; Take a look at <a href="https://cscourses.online/topics/Linux/">Linux</a>!</p>