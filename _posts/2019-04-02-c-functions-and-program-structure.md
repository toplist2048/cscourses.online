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
    <p>The static declaration can also be applied to internal variables. Internal static variables are local to a particular function just as automatic variables
are, but unlike automatics, they remain in existence rather than coming and going each time the function is activated. This means that internal static
variables provide private, permanent storage within a single function.</p>

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
<p>The #if line evaluates a constant integer expression (which may not include sizeof, casts, or enum constants). If the expression is non-zero, subsequent
lines until an #endif or #elif or #else are included. The expression defined(name) in a #if is 1 if the name has been defined, and 0 otherwise.</p>

    <h2>C Pointers and Arrays</h2>
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
    <p>There is one difference between an array name and a pointer.</p>
    <h3>C Address Arithmetic</h3>
    <p>Pointer arithmetic is consistent: if we are dealing with floats, and if p were a pointer to float, p++ would advance to the next float.</p>
    <h3>C Pointers to Functions</h3>
    <p>In C, a function itself is not a variable, but it is possible to define pointers to functions, which can be assigned, placed in arrays, passed to functions, returned by functions, and so on.</p>
    <h2>C Structures</h2>
    <h3>C Basics of Structures</h3>
    <p>A struct declaration defines a type. </p>
    <h3>C Typedef</h3>
    <p>C provides a facility called typedef for creating new data type names. For example, the declaration <code>typedef int Length;</code> makes the name Length a synonym for int.</p>
    <h3>C Unions</h3>
    <p>A union is a variable that may hold (at different times) objects of different types and sizes, with the compiler keeping track of size and alignment requirements. </p>
    <p>Unions provide a way to manipulate different kinds of data in a single area of storage, without embedding any machine-dependent information in the program.</p>
    <h3>C Bit-fields</h3>
    <p>A bit-field is a set of adjacent bits within a single implementation-defined storage unit that we will call a "word".</p>
    <pre>
struct {
 unsigned int is_keyword : 1;
 unsigned int is_extern : 1;
 unsigned int is_static : 1;
} flags;    
    </pre>