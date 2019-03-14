---
ID: 763
post_title: >
  Java Data Types, Operators and
  Statements
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/java/java-data-types-operators-and-statements/
published: true
post_date: 2019-03-14 18:30:46
---
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
    <h3>Java Data Types</h3>
    <h4>Java Primitives</h4>
    <p>Java primitive types are built-in types.</p>
    <table>
      <thead>
        <tr>
          <td> Keyword </td>
          <td> Type </td>
          <td> Literal </td>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>boolean</td>
          <td> true or false </td>
          <td>true</td>
        </tr>
        <tr>
          <td>byte</td>
          <td style="height: 19px;"> 8-bit integral value</td>
          <td> 123</td>
        </tr>
        <tr>
          <td>int</td>
          <td> 32-bit integral value</td>
          <td> 123</td>
        </tr>
        <tr>
          <td>long</td>
          <td> 64-bit integral value </td>
          <td style="height: 19px;">123L</td>
        </tr>
        <tr>
          <td> float</td>
          <td> 32-bit floating-point value </td>
          <td>123.45F</td>
        </tr>
        <tr>
          <td>double</td>
          <td> 64-bit floating-point value </td>
          <td>123.456</td>
        </tr>
        <tr>
          <td>char</td>
          <td> 16-bit Unicode value </td>
          <td>'a'</td>
        </tr>
      </tbody>
    </table>
    <ul>
      <li>float and double are used for floating-point (decimal) values.</li>
      <li>A float requires the letter f following the number so Java knows it is
        a float.</li>
      <li>byte, short, int, and long are used for numbers without decimal
        points.</li>
      <li>A long requires the letter l following the number so Java knows it is
        a long.</li>
      <li>Each numeric type uses twice as many bits as the smaller similar type.
        For example, short uses twice as many bits as byte does.</li>
    </ul>
    <p>Speical integer format</p>
    <ul>
      <li>octal (digits 0–7), which uses the number 0 as a prefix—for example,
        017</li>
      <li>hexadecimal (digits 0–9 and letters A–F), which uses the number 0
        followed by x or X as a prefix—for example, 0xFF</li>
      <li>binary (digits 0–1), which uses the number 0 followed by b or B as a
        prefix—for example, 0b10</li>
    </ul>
    <h4>Java References</h4>
    <p>Java reference is a pointer to a object located in memory. Reference
      types can be assigned null , which means they do not currently refer to an
      object.</p>
    <pre>String str = "Hello, World!";</pre>
    <h4>Java Identifiers</h4>
    <ul>
      <li>The name must begin with a letter or the symbol $ or _ </li>
      <li>Subsequent characters may also be numbers.</li>
      <li>You cannot use the same name as a Java reserved word.</li>
    </ul>    
    <h3>Java Operators</h3>
    <p>A Java operator applies to a set of variables, values, or literals and
      returns a result. Unless overridden with parentheses, Java operators
      follow order of operation. If two operators have the same level of
      precedence, then Java guarantees left-to-right evaluation.</p>
    <p>Order of operator precedence,</p>
    <table>
      <thead>
        <tr>
          <td>Operator</td>
          <td>Symbols and examples</td>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Post-unary operators</td>
          <td> expression++, expression--</td>
        </tr>
        <tr>
          <td>Pre-unary operators</td>
          <td> ++expression, --expression</td>
        </tr>
        <tr>
          <td>Other unary operators</td>
          <td> +, -, !</td>
        </tr>
        <tr>
          <td>Multiplication/Division/Modulus</td>
          <td> *, /, %</td>
        </tr>
        <tr>
          <td>Addition/Subtraction</td>
          <td> +, -</td>
        </tr>
        <tr>
          <td>Shift operators</td>
          <td> &lt;&lt;, &gt;&gt;, &gt;&gt;&gt;</td>
        </tr>
        <tr>
          <td>Relational operators</td>
          <td> &lt;, &gt;, &lt;=, &gt;=, instanceof</td>
        </tr>
        <tr>
          <td>Equal to/not equal to</td>
          <td> ==, !=</td>
        </tr>
        <tr>
          <td>Logical operators</td>
          <td> &amp;, ^, |</td>
        </tr>
        <tr>
          <td>Short-circuit logical operators</td>
          <td> &amp;&amp;, ||</td>
        </tr>
        <tr>
          <td>Ternary operators boolean expression</td>
          <td> ? expression1 : expression2</td>
        </tr>
        <tr>
          <td>Assignment operators</td>
          <td> =, +=, -=, *=, /= %=, &amp;=, ^=, !=, &lt;&lt;=, &gt;&gt;= ,
            &gt;&gt;&gt;=</td>
        </tr>
      </tbody>
    </table>
    <p>The modulus operation is not limited to positive integer values and may
      also be applied to negative integers and floating-point integers.</p>
    <p> Numeric promotion rules when using arithmatic operators, </p>
    <ul>
      <li>If two values have different data types, Java will automatically
        promote one of the values to the larger of the two data types.</li>
      <li>If one of the values is integral and the other is floating-point, Java
        will automatically promote the integral value to the floating-point
        value’s data type. </li>
      <li>Smaller data types, namely byte , short , and char , are first
        promoted to int even if neither of the operands is int . </li>
      <li>The result have the same data type as its promoted operands. </li>
    </ul>
    <p>Casting primitives is required any time you are going from a larger
      numerical data type to a smaller numerical data type, or converting from a
      fl oating-point number to an integral value</p>
    <pre>int i = (int)1.0</pre>
    <p><code>a instanceof b</code> is True if the reference that a points to is
      an instance of a class, subclass, or class that implements a particular
      interface, as named in b</p>
    <h3>Java Statements</h3>
    <b>Java if-else Statements</b>
    <pre>// Curly braces required for block of multiple statements, optional for single statement
if(booleanExpression 1) {   // Branch if booleanExpression 1 is True
  ;<br>} else if(booleanExpression 2) {   // Branch if booleanExpression 2 is True
  ;<br>} else { //otherwise<br>  ;<br>}
 </pre>
    <b>Java Ternary Operators</b>
    <pre>booleanExpression ? expression 1 : expression 2</pre>
    <p>If booleanExpression is True, then the result is expression 1, otherwise
      expression 2.</p>
    <b>Java Switch Statements</b>
    <pre>switch(variableToTest) { // curly brace is required
  case constantExpression 1 :
    ;// Branch for case 1 ;
    break;
  case constantExpression 2 :
    ;// Branch for case 2 ;
    break; Optional break
  default:
    ;// Branch for default
}</pre>
    <p>A switch statement has a target variable that is not evaluated until
      runtime. Data types of the target varialbe include the following: int and
      Integer, byte and Byte, short and Short, char and Character, int and
      Integer, String, and enum values.</p>
    <p>There is no requirement that the case or default statements be in a
      particular order.</p>
    <b>Java while Statements</b>
    <pre>// Curly braces required for block of multiple statements, optional for single statement
while(booleanExpression) {
  ;// Body
}    
</pre> <b>Java do-while Statements</b>
    <pre>// Curly braces required for block of multiple statements, optional for single statement
do {
  // Body
} while (booleanExpression); //Semicolon (required)    
</pre> <b>Java for Statements</b>
    <pre>// Curly braces required for block of multiple statements, optional for single statement
for(initialization; booleanExpression; updateStatement) {
  ; // Body
}</pre>
    <p>The steps is, </p>
    <ol>
      <li>Initialization statement executes</li>
      <li>If booleanExpression is true continue, else exit loop</li>
      <li>Body executes</li>
      <li>Execute updateStatements</li>
      <li>Return to Step 2</li>
    </ol>
    <b>Java for-each Statements</b>
    <pre>for(datatype instance : collection) {
  ;// Body
}</pre>
    <p>The collection must be a Java array or an object whose class implements
      java.lang.Iterable , which includes most of the Java Collections
      framework. The type of the instance must matches the type of a member of
      the collection.</p>
    <b>Java break Statements</b>
    <pre>optionalLabel: while(booleanExpression) {
  ; //  Body code
  break optionalLabel;<br>  ; // Body code<br>}</pre>
    <p>Here optionalLabel is a label. A label is an optional pointer to the head
      of a statement that allows the application flow to jump to it or to
      break&nbsp; it. Without a label parameter, the break statement will
      terminate the nearest inner loop it is in.</p>
    <b>Java Continue Statements</b>
    <pre>optionalLabel: while(booleanExpression) {
  ; //  Body code
  continue optionalLabel;<br>  ; // Body code<br>}</pre>
    <p>Without a label parameter, the continue statement will continue the
      nearest inner loop it is in.</p>
  </body>
</html>