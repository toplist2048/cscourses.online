---
ID: 751
post_title: JavaScript
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/topics/javascript/
published: true
post_date: 2019-03-13 17:27:14
---
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
    <h2>JavaScript Introduction</h2>
    <p>JavaScript and ECMAScript are two names of the same language. </p>
    <p>JavaScript is easy to learn but hard to master. JavaScript is
      ridiculously liberal in what it allows. The idea is to make it easier for
      beginners, but acturally it makes finding problems harder because the
      system will not point them out.</p>
    <h2>JavaScript Basics</h2>
    <h3>JavaScript Values, Types, and Operators</h3>
    <h4>JavaScript Numbers</h4>
    <p>JavaScript has a number type. JavaScript uses 64 bits to store a number
      value.</p>
    <pre lang="javascript">9
9.1</pre>
    <p>Arithmetic operations including +, -, *, / and %. </p>
    <p>There are three special number values in JavaScript. Infinity and
      -Infinity represent the positive and negative infinities. Infinity - 1 is
      still Infinity , and so on. NaN stands for “not a number”, even though it
      is a value of the number type.</p>
    <h4>JavaScript Strings</h4>
    <p>JavaScript strings are used to represent text content. They are marked by
      single quotes, double quotes, or backticks.</p>
    <pre lang="javascript">`JavaScript`
"Python"
'Lisp'</pre>
    <p>There are two special values, written null and undefined, that are used
      to denote the absence of a meaningful value.</p>
    <p>JavaScript support character escape such as \n, \\, \`.</p>
    <p>JavaScript string concatenation.</p>
    <pre>"a" + 'b'</pre>
    <p>JavaScript backtick-quoted strings support template literals</p>
    <pre>let v = "World!"
`Hello, ${v}`</pre>
    <h4>JavaScript Boolean</h4>
    <p>JavaScript has a Boolean type, which has just two values, true and false</p>
    <h4>JavaScript Operators</h4>
    <p>JavaScript typeof is a operator</p>
    <p>Comparison operators such as &lt;, &gt;, &lt;=, &gt;=, ==, and !=</p>
    <p>Logical operators such as &amp;&amp; and ||</p>
    <p>Ternary operator (?&nbsp; : )</p>
    <p>To negate a number - </p>
    <p>To negate logically ! </p>
    <h4>JavaScript Type Conversion</h4>
    <p>JavaScript tends to quietly convert a value to the type it needs, using a
      set of rules that often aren’t what you want, for example, <code>"5" + 1</code>,
      the result is "51" since 1 is converted to "1", while <code>"5" - 1</code>,
      the result is 4 since "5" is converted to 5. Another example is <code>null
        == undefined</code> evaluates to true, <code>null == 0</code> evaluates
      to false.</p>
    <p>When you do not want any type conversions to happen, there are two
      additional operators: === and !== .The first tests whether a value is
      precisely equal to the other, and the second tests whether it is not
      precisely equal.</p>
    <pre></pre>
    <h3>JavaScript Program Structure</h3>
    <h4>JavaScript Variables</h4>
    <p>The keyword let defines a variable. It is followed by the name of the
      variable and an = operator and an expression. The keyword var also defines
      a variable, but its outdated cause it has a scope issue. The keyword const
      defines a constant variable.</p>
    <p>Bindings declared with let and const are local to the block that they are
      declared in. The old-style variables, created with the var keyword, are
      visible throughout the whole function or throughout the global scope, if
      they are not in a function.</p>
    <pre lang="javascript">let a = 1; 
var a = 1; 
const b = 1;</pre>
    <h4>JavaScript Control Flow</h4>
    <p>JavaScript has usual conditional if statement and loops statement such as
      for, do, while and switch.</p>
    <h3>JavaScript Arrays</h3>
    <p>JavaScript array type is used to store sequences of values. It is written
      as a list of values between square brackets, separated by commas.</p>
    <pre>let a = [1, 3, 5, 7];</pre>
    <h3>JavaScript Objects</h3>
    <p>The type object has values which are collections of properties. One way
      to create an object is by using braces as an expression. Inside the
      braces, there is a list of properties separated by commas. Each property
      has a name followed by a colon and a value. </p>
    <pre>let o = {
  name : "numbers",
  value : [1, 2, 3]
}</pre>
    <h2>JavaScript Functions</h2>
    <h3>JavaScript Function Declaration</h3>
    <p>A function is created with an expression that starts with the keyword
      function. Functions have a set of parameters and a body.</p>
    <p>When the function keyword is used at the beginning of a statement, it is
      a function declaration. </p>
    <pre lang="javascript">function inc(x) {
&nbsp; return x + 1;
}</pre>
    <p>Function declarations are not part of the regular top-to-bottom flow of
      control. They are moved to the top of their scope and can be used by all
      the code in that scope. This is sometimes useful because it offers the
      freedom to order code in a way that seems meaningful, without worrying
      about having to define all functions before they are used.</p>
    <h3>JavaScript Function Definition</h3>
    <p>A function definition is a regular binding where the value of the binding
      is a function.</p>
    <pre lang="javascript">const inc = function(x) {
  return x + 1;
};</pre>
    <p>A function value can do all the things that other values can do — you can
      use it in expressions, not just call it. It is possible to store a
      function value in a new binding, pass it as an argument to a function, and
      so on. Similarly, a binding that holds a function is still just a regular
      binding and can be assigned a new value.</p>
    <h3>JavaScript Arrow Functions</h3>
    <p>Instead of the function keyword, it uses an arrow ( =&gt; ).</p>
    <pre lang="javascript">const inc = (x) =&gt; {
 return x + 1;
};
// More concisely
const int = x =&gt; x + 1;
</pre>
    <h3>JavaScript Closure</h3>
    <p>A function that references bindings from local scopes around it is called
      a closure.</p>
    <pre lang="javascript">function inc(n) {
  let local = n;
  return () =&gt; local + 1;
}
</pre>
    <h3>JavaScript Recursion</h3>
    <p>A function that calls itself is called recursive. JavaScript supports
      Resursion.</p>
    <h3>JavaScript Higher-Order Functions</h3>
    <p>Functions that operate on other functions, either by taking them as
      arguments or by returning them, are called higher-order functions.</p>
    <pre lang="JavaScript">function greaterThan(n) {
  return m =&gt; m &gt; n;
}
let greaterThan10 = greaterThan(10);    
    </pre>
    <h2>JavaScript OOP</h2>
    <h3>JavaScript Object Methods</h3>
    <p>In JavaScript, methods are properties that hold function values.</p>
    <pre lang="JavaScript">  let o = {}
  o.inc = function(x) {
    return x + 1; 
  }
</pre>
    <h3>JavaScript Object Prototypes</h3>
    <p>Most objects have a prototype. A prototype is another object that is used
      as a fallback source of properties. When an object gets a request for a
      property that it does not have, its prototype will be searched for the
      property, then the prototype’s prototype, and so on.</p>
    <p>The entity behind almost all objects is Object.prototype .</p>
    <pre lang="javascript">Object.getPrototypeOf({}) == Object.prototype</pre>
    <h3>JavaScript Classes</h3>
    <p>JavaScript classes are constructor functions with a prototype property.</p>
    <pre>class O {
  constructor(v) {
  this.v = v;
  }
  int() {
    this.v += 1;
    return this.v;
  }
}
let o = new O(1);
</pre>
    <h3>JavaScript Inheritance</h3>
    <p>JavaScript’s prototype system makes it possible to create a new class,
      much like the old class, but with new definitions for some of its
      properties.</p>
    <h2>JavaScript Error Handling</h2>
    <p>JavaScript can be made a little stricter by enabling strict mode. This is
      done by putting the string "use strict" at the top of a file or a function
      body.</p>
    <p>There are a number of different conventions for annotating JavaScript
      programs with types.</p>
    <p>Exceptions are a mechanism that makes it possible for code that runs into
      a problem to raise (or throw) an exception.</p>
    <pre lang="javascript">throw new Error("Invalid Parameters!");</pre>
    <h2>JavaScript Regular Expression</h2>
    <p>Regular expressions are a way to describe patterns in string data. They
      form a small, separate language that is part of JavaScript</p>
    <p>A regular expression is a type of object. It can be either constructed
      with the RegExp constructor or written as a literal value by enclosing a
      pattern in forward slash ( / ) characters.</p>
    <pre lang="javascript">let re1 = new RegExp("abc");
let re2 = /abc/;   
re1.test("abcd")
</pre>
    <ul>
      <li>\d means the same thing as [0-9] .</li>
      <li>\d Any digit character</li>
      <li>\w An alphanumeric character (“word character”)</li>
      <li>\s Any whitespace character (space, tab, newline, and similar)</li>
      <li>\D A character that is not a digit</li>
      <li>\W A nonalphanumeric character</li>
      <li>\S A nonwhitespace character</li>
      <li>. Any character except for newline</li>
    </ul>
    <p>Plus sign ( + ) after something indicates that the element may be
      repeated more than once.</p>
    <p>The star ( * ) has a similar meaning but also allows the pattern to match
      zero times.</p>
  </body>
</html>