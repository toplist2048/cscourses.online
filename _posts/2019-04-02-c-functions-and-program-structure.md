---
ID: 870
post_title: C Functions and Program Strructure
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/c/c-functions-and-program-structure/
published: true
post_date: 2019-04-02 12:49:54
---
<h2>C Functions and Program Structure</h2>
<h3>C Basics of Functions</h3>
<p>Function definition,</p>
<pre>return-type function-name(argument declarations){
  declarations and statements
}</pre>
<p>The returh statement is the mechanism for returning a value from the called function to its caller. Any expressioncan follow return:</p>
<pre>return expression;</pre>
<h3>C External Variables</h3>
<p>External variables are defined outside of any function, and are thus available to many functions.</p>
<h3>C Scope Rules</h3>
<p>The scope of a name is the part of the program within which the name can be used. </p>
<p>For an automatic variable declared at the beginning of a function, the scope is the function in which the name is declared. Local variables of the same name in different functions are unrelated. The same is true of the parameters of the function, which are in effect local variables. </p>
<p>The scope of an external variable or a function lasts from the point at which it is declared to the end of the file being compiled. It is important to distinguish between the declaration of an external variable and its definition. A declaration announces the properties of a variable (primarily its type); a definition also causes storage to be set aside. </p>
<h3>C Header Files</h3>
<p>The definitions and declarations shared among files are placed in a header file. To use it, use <code>#include "headfile.h"</code>.</p>
<h3>C Static Variables</h3>
<p>The static declaration, applied to an external variable or function, limits the scope of that object to the rest of the source file being compiled.</p>
<p>The static declaration can also be applied to internal variables. Internal static variables are local to a particular function just as automatic variables are, but unlike automatics, they remain in existence rather than coming and going each time the function is activated. This means that internal static variables provide private, permanent storage within a single function.</p>

<h3>C Register Variables</h3>
<p>A register declaration advises the compiler that the variable will be heavily used. The idea is that register variables are to be placed in machine registers, which may result in smaller and faster programs. But compilers are free to ignore the advice.</p>
<h3>C Block Structure</h3>
<p>Variables declared in block structure hide any identically named variables in outer blocks, and remain in existence until the matching right brace. As a matter of style, it's best to avoid variable names that conceal names in an outer scope; the potential for confusion and error is too great.</p>

<h3>C Initialization</h3>
<p>External and static variables are guaranteed to be initialized to zero; automatic and register variables have undefined initial values.</p>

<h3>C Recursion</h3>
<p>C functions may be used recursively; that is, a function may call itself either directly or indirectly.</p>
<h3>C Preprocessor</h3>
<p>The two most frequently used preprocessor features are #include, to include the contents of a file during compilation, and #define, to replace a token by an arbitrary sequence of characters.</p>
<pre>
#include «filename»
#define name replacement text
</pre>
<p>The #if line evaluates a constant integer expression (which may not include sizeof, casts, or enum constants). If the expression is non-zero, subsequent lines until an #endif or #elif or #else are included. The expression defined(name) in a #if is 1 if the name has been defined, and 0 otherwise.</p>

<h2 id="PaA">C Pointers and Arrays</h2>
<p>A pointer is a variable that contains the address of a variable. Pointers and arrays are closely related.</p>

<h3>C Pointers and Addresses</h3>
<p>The unary operator &amp; gives the address of an object.</p>
<p>The unary operator * is the indirection or dereferencing operator; when applied to a pointer, it accesses the object the pointer points to.</p>
<pre>int x = 1, y = 2, z[10];
int *ip;  //ip is a pointer to int 
ip = &amp;x; // ip now points to x 
y = *ip; // y is now 1 
*ip = 0; // x is now 0 
ip = &amp;z[O]; // ip now points to z[O] </pre>

<h3>C Pointers and Function Arguments</h3>
<p>Since C passes arguments to functions by value, there is no direct way for the called function to alter a variable in the calling function. The right way is to pass pointers to the variable to be changed.</p>
<pre>
void swap(int *px, int *py) {
  int temp;
  temp = *px;
  *px = *py;
  *py = temp;
}
swap (&a,&b);
</pre>
<h3>C Pointers and Arrays</h3>
<p>In evaluating a[i], C converts it to *(a+i) immediately; the two forms are equivalent. Applying the operator & to both parts of this equivalence, it follows that &a[i] arid a+i are also identical: a+i is the address of the i-th element beyond a. As the other side of this coin, if pa is a pointer, expressions may use it with a subscript; pa[i] is identical to *(pa+i). In short, an array-and-index expression is equivalent to one written as a pointer and offset.</p>

<h3>C Address Arithmetic</h3>
<p>Pointer arithmetic is consistent: if we are dealing with floats, and if p were a pointer to float, p++ would advance to the next float.</p>

<h3>C Character Pointers and Functions</h3>
<p>There is an important difference between these definitions,</p>
<pre>char amessage[] = "now is the time"; // an array 
char *pmessage = "now is the time"; // a pointer
<p>amessaqe is an array, just big enough to hold the sequence of characters and '\0' that initializes it. Individual characters within the array may be changed but amessaqe will always refer to the same storage. On the other hand, pmessaqe is a pointer, initialized to point to a string constant; the pointer may subsequently be modified to point elsewhere, but the result is undefined if you try to modify the string contents.</p>

    <h3>C Pointer Arrays; Pointers to Pointers</h3>
<pre>char *lineptr[MAXLINES]; // pointers to text lines 
</pre>

<h3>C Multi-dimensional Arrays</h3>
<p>In C, a two-dimensional array is really a one-dimensional array, each of whose elements is an array. </p>
<pre>daytab[i][j]; // [row][col] </pre>

<h3>C Initialization of Pointer Arrays</h3>
<pre>char *name[] = {
"Illegal month",
"January", "February", "March",
"April", "May", "June",
"July", "August", "September",
"October", "November", "December" };</pre>

<h3>C Pointers vs. Multi-dimensional Arrays</h3>
<p>The important advantage of the pointer array is that the rows of the array may be of different lengths. </p>

<h3>C Command-line Arguments</h3>
<p>In environments that support C, there is a way to pass command-line arguments or parameters to a program when it begins executing. When main is called, it is called with two arguments. The first (conventionally called argc, for argument count) is the number of command-line arguments the program was invoked with; the second (argv, for argument vector) is a pointer to an array of character strings that contain the arguments, one per string.</p>

<h3>C Pointers to Functions</h3>
<p>In C, a function itself is not a variable, but it is possible to define pointers to functions, which can be assigned, placed in arrays, passed to functions, returned by functions, and so on.</p>
<pre>
void qsort(void *v[], int left, int right, int (*comp)(void *, void *));
</pre>
<h3>C Complicated Declarations</h3>
<pre>
int *f(); // f: function returning pointer to int 
int (*pf)(); // pf: pointer to function returning int 
</pre>

<h2 id="S">C Structures</h2>
<p>A structure is a collection of one or more variables, possibly of different types, grouped together under a single name for convenient handling.</p>
<h3>C Basics of Structures</h3>
<p>A struct declaration defines a type. </p>
<pre>struct { ...} x, y;
struct point {
int X;
int y;
};
struct point pt;
</pre>
<p>A member of a particular structure is referred to in an expression by a construction of the form <code>structure-name.member</code>.</p>

<h3>C Structures and Functions</h3>
<p>The only legal operations on a structure are copying it or assigning to it as a unit, taking its address with &, and accessing its members. Copy and assignment include passing arguments to functions and returning values from functions as well. Structures may not be compared. A structure may be initialized by a list of constant member values; an automatic structure may also be initialized by an assignment.</p>
<p>Pointers to structures are so frequently used that an alternative notation is provided as a shorthand. If p is a pointer to a structure, then <code>p->member-of-structure</code> refers to the particular member.</p>

<h3>C Arrays of Structure</h3>
<p>The structure declaration</p>
<pre>
struct key {
char *word;
int count;
} keytab[NKEYS];
</pre>
<p>declares a structure type key, defines an array keytab of structures of this type, and sets aside storage for them. Each element of the array is a structure.</p>

<h3>C Pointer to Structure</h3>
<p>If p is a pointer to a structure, arithmetic on p takes into account the size of the structure, so p+ + increments p by the correct amount to get the next element of the array of structures.</p>

<h3>C Self-referential Structures</h3>
<p>This recursive declaration of a node might look chancy, but it's correct.</p>
<pre>
struct tnode { // the tree node
  char *word; // points to the text
  int eount; // number of occurrences 
  struct tnode *left;  // left child 
  struct tnode *right; // right child 
};
</pre>

<h3>C Table Lookup</h3>
<p>The for loop in lookup is the standard idiom for walking along a linked list: </p>
<pre>
for (ptr = head; ptr 1= NULL; ptr = ptr->next)
  ...
</pre>

<h3>C Typedef</h3>
<p>C provides a facility called typedef for creating new data type names. For example, the declaration <code>typedef int Length;</code> makes the name Length a synonym for int. For example, the declaration <code>typedef int Length;</code> makes the name Length a synonym for int.</p>

<h3>C Unions</h3>
<p>A union is a variable that may hold (at different times) objects of different types and sizes, with the compiler keeping track of size and alignment requirements. </p>
<pre>
union u_tag {
  int ivaI;
  float fval;
  char *sval;
} u;
</pre>
<p>Unions provide a way to manipulate different kinds of data in a single area of storage, without embedding any machine-dependent information in the program.</p>
<p>Syntactically, members of a union are accessed as <code>union-name.member</code> or <code>union-pointer->member</code></p>

<h3>C Bit-fields</h3>
<p>A bit-field is a set of adjacent bits within a single implementation-defined storage unit that we will call a "word".</p>
<pre>
struct {
 unsigned int is_keyword : 1;
 unsigned int is_extern : 1;
 unsigned int is_static : 1;
} flags;    
</pre>
<p>Individual fields are referenced in the same way as other structure members.</p>