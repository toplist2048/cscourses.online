---
ID: 763
post_title: Java Basics
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/java/java-basics/
published: true
post_date: 2019-03-14 18:30:46
---
    <h3>Java Data Types</h3>
    <p>Java has two kinds of data types: Java primitives and Java objects. Everything in Java is an Object except primitives.</p>

    <h4>Java Primitives</h4>
    <p>Java primitive types are built-in types.</p>
    <table>
      <thead>
        <tr><td>Keyword</td><td>Type</td><td>Literal</td></tr>
      </thead>
      <tbody>
        <tr><td>boolean</td><td>true or false</td><td>true</td></tr>
        <tr><td>byte</td><td>8-bit integral value</td><td>123</td>
        </tr><tr><td>short</td><td>16-bit integral value</td><td>123</td></tr>
        <tr><td>int</td><td>32-bit integral value</td><td>123</td></tr>
        <tr><td>long</td><td>64-bit integral value</td><td>123L</td></tr>
        <tr><td>float</td><td>32-bit floating-point value</td><td>123.45F</td></tr>
        <tr><td>double</td><td>64-bit floating-point value</td><td>123.456</td></tr>
        <tr><td>char</td><td>16-bit Unicode value</td><td>'a'</td></tr>
      </tbody>
    </table>
    <ul>
      <li>The float and double are used for floating-point (decimal) values.</li>
      <li>A float requires the letter f following the number so Java knows it is a float.</li>
      <li>The byte, short, int, and long are used for numbers without decimal points.</li>
      <li>A long requires the letter l following the number so Java knows it is a long.</li>
      <li>Each numeric type uses twice as many bits as the smaller similar type.
        For example, short uses twice as many bits as byte does.</li>
    </ul>
    <p>Special integer format</p>
    <ul>
      <li><b>octal:</b> (digits 0–7), which uses the number 0 as a prefix—for example,
        017</li>
      <li><b>hexadecimal:</b> (digits 0–9 and letters A–F), which uses the number 0
        followed by x or X as a prefix—for example, 0xFF</li>
      <li><b>binary:</b> (digits 0–1), which uses the number 0 followed by b or B as a
        prefix—for example, 0b10</li>
    </ul>

    <h4>Java Identifiers</h4>
    <ul>
      <li>The name must begin with a letter or the symbol $ or _. </li>
      <li>Subsequent characters may also be numbers.</li>
      <li>Java reserved words can not be used as identifier.</li>
    </ul>

    <h4>Java Strings, StringBuilders, and StringBuffer</h4>
    <p>In Java, there are two methods to create a String.</p>
    <pre>String name = "Java";
String name = new String("Java"); </pre>
    <p>Once a String object is created, it is not allowed to change. The string
      pool is the place where the JVM collects all these strings.</p>
    <p>String concatenates using +,</p>
    <pre>String Name = "Java" + "Script";   
Name = Name + Name; // old one garbage collected, new one re-assigned to Name reference; 
</pre>
    <p>Important String methods,</p>
    <ul>
      <li>charAt() - Return the character at a index. Throw exception if out of
        range.</li>
      <li>contains() - Check if a string contains some string.</li>
      <li>equals(), equalsIgnoreCase() - Check if two strings equal. Never use
        == to compare string objects, cause == check reference equal.</li>
      <li>indexOf() - Return the first index that matches the character. Return
        -1 is no match.</li>
      <li>length() - Return the string length.</li>
      <li>replace() - Replace part of the string.</li>
      <li>startsWith(), endsWith() - Check if string start / end with some
        string.</li>
      <li>subString() - Return part of the string.</li>
      <li>toLowerCase(), toUpperCase() - Return a lover case / upper case
        version.</li>
      <li>trim() - Remove whitespaces from begining and end of the string.</li>
    </ul>
    <p>It is common to chain multiple methods on the same string.</p>
    <pre>" Hello, World. ".trim().replace(".", "!").toLowerCase();
</pre>

    <p>String is immutable, so when there is lots of operations, use
      StringBuilder, which is mutable.</p>
    <pre>StringBuilder sb =  new StringBuilder("Java");</pre>
    <p>In StringBuilder, size is the number of characters currently in the
      sequence, and capacity is the number of characters the sequence can
      currently hold.</p>
    <p>Important StringBuilder methods include charAt(), indexOf(), length(),
      and subString().</p>
    <p>Since StringBuilder is mutable, it has methods such as append(), insert(), delete(),
      deleteCharAt(), reverse(), toString().</p>
    <p>The StringBuilder equals() only compare reference equal, since it is not
      overwritten.</p>
    <p>StringBuffer does the same thing as StringBuilder but more slowly because
      it is thread safe.</p>

    <h4>Java References</h4>
    <p>Java reference is a pointer to a object located in memory. Reference
      types can be assigned null, which means they do not currently refer to an
      object.</p>
    <pre>String str = "Hello, World!";</pre>

    <h4>Java Wrapper Class</h4>
    <table>
      <thead>
        <tr><td>Primitive Type</td><td>Wrapper Class</td><td>Constructing</td></tr>
      </thead>
      <tbody>
        <tr><td>boolean</td><td>Boolean</td><td>new Boolean(true)</td></tr>
        <tr><td>byte</td><td>Byte</td><td>new Byte((byte) 1)</td></tr>
        <tr><td>short</td><td>Short</td><td>new Short((short) 1)</td></tr>
        <tr><td>int</td><td>Integer</td><td>new Integer(1)</td></tr>
        <tr><td>long</td><td>Long</td><td>new Long(1L)</td></tr>
        <tr><td>float</td><td>Float</td><td>new Float(1.0F)</td></tr>
        <tr><td>double</td><td>Double</td><td>new Double(1.0)</td></tr>
        <tr><td>char</td><td>Character</td><td>new Character('1')</td></tr>
      </tbody>
    </table>
    <p>You can convert primitive value and wrapper class without cast. Java will
      convert it for you. This is called autoboxing. </p>
    <pre>Integer i = 1;
int j = i;</pre>

    <p>Converting from a String </p>
    <table>
      <thead><tr><td>Wrapper Class</td><td>Converting String to primitive</td>          <td>Constructing</td></tr>
      </thead>
      <tbody>
        <tr><td>Boolean</td><td>Boolean.parseBoolean("true");</td><td>Boolean.valueOf("TRUE");</td></tr>
        <tr><td>Byte</td><td>Byte.parseByte("1");</td><td>Byte.valueOf("1");</td></tr>
        <tr><td>Short</td><td>Short.parseShort("1");</td><td>Short.valueOf("1");</td></tr>
        <tr><td>Integer</td><td>Integer.parseInt("1");</td><td>Integer.valueOf("1");</td></tr>
        <tr><td>Long</td><td>Long.parseLong("1");</td><td>Long.valueOf("1");</td></tr>
        <tr><td>Float</td><td>Float.parseFloat("1");</td><td>Float.valueOf("1.1");</td></tr>
        <tr><td>Double</td><td>Double.parseDouble("1");</td><td>Double.valueOf("1.1");</td></tr>
        <tr><td>Character</td><td>N/A</td><td>N/A</td></tr>
      </tbody>
    </table>

    <h3>Java Operators</h3>
    <p>A Java operator applies to a set of variables, values, or literals and
      returns a result. Unless overridden with parentheses, Java operators
      follow order of operation. If two operators have the same level of
      precedence, then Java guarantees left-to-right evaluation.</p>
    <p>Order of operator precedence,</p>
    <table>
      <thead>
        <tr><td>Operator</td><td>Symbols and examples</td></tr>
      </thead>
      <tbody>
        <tr><td>Post-unary operators</td><td> expression++, expression--</td></tr>
        <tr><td>Pre-unary operators</td><td> ++expression, --expression</td></tr>
        <tr><td>Other unary operators</td><td> +, -, !</td></tr>
        <tr><td>Multiplication/Division/Modulus</td><td> *, /, %</td></tr>
        <tr><td>Addition/Subtraction</td><td> +, -</td></tr>
        <tr><td>Shift operators</td><td> &lt;&lt;, &gt;&gt;, &gt;&gt;&gt;</td></tr>
        <tr><td>Relational operators</td><td> &lt;, &gt;, &lt;=, &gt;=, instanceof</td></tr>
        <tr><td>Equal to/not equal to</td><td> ==, !=</td></tr>
        <tr><td>Logical operators</td><td> &amp;, ^, |</td></tr>
        <tr><td>Short-circuit logical operators</td><td> &amp;&amp;, ||</td></tr>
        <tr><td>Ternary operators boolean expression</td><td> ? expression1 : expression2</td></tr>
        <tr><td>Assignment operators</td><td> =, +=, -=, *=, /= %=, &amp;=, ^=, !=, &lt;&lt;=, &gt;&gt;= , &gt;&gt;&gt;=</td></tr>
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
      <li>Smaller data types, namely byte, short, and char, are first
        promoted to int even if neither of the operands is int. </li>
      <li>The result have the same data type as its promoted operands. </li>
    </ul>
    <p>Casting primitives is required any time you are going from a larger
      numerical data type to a smaller numerical data type, or converting from a
      floating-point number to an integral value</p>
    <pre>int i = (int)1.0</pre>
    <p><code>a instanceof b</code> is True if the reference that a points to is
      an instance of a class, subclass, or class that implements a particular
      interface, as named in b.</p>
    <p>The >> is arithmetic shift right, >>> is logical shift right. In an arithmetic shift, the sign bit is extended to preserve the signedness of the number. </p> 


    <h3>Java Arrays</h3>
    <p>An Java array is a piece of memory on the heap for a number of elements.</p>
    <h4>Java Creating Arrays</h4>
    <p>Ways to create arrays,</p>
    <pre>int[] numbers = new int[3];
int[] numbers = new int[] {11, 22, 33};
int[] numbers = {42, 55, 99};</pre>
    <p>The [] can before or after the name, and adding spaces is optional. This
      means that all four of these statements do the exact same thing.</p>
    <pre>int[] numbers;
int [] numbers;
int numbers[];
int numbers [];</pre>
    <p>Note when [] used in multiple declaration, the place of [] matters. In
      below example, b is a int[], whild d is a int.</p>
    <pre>int [] a, b;
int c[], d;
</pre>
    <p>When array is created for objects, the array does not allocate space for
      the objects. Instead, it allocates space for a reference to the objects.</p>
    <p>Array can be casted.</p>
    <pre>String[] s = {1, 2, 3}    
Object[] o = s 
String[] s2 = (String[]) o</pre>
    <h4>Java Array Functions</h4>
    <p>Some array functions defined in java.util.Arrays,</p>
    <ul>
      <li>Arrays.sort() - Sort an array.</li>
      <li>Arrays.binarySearch() - Search an array.</li>
    </ul>
    <h4>Java Multidimensional Arrays</h4>
    <pre>String [][] d2 = new String[3][2];</pre>
    <h3>Java ArrayList</h3>
    <p>An ArrayList is an ordered sequence that allows duplicates. ArrayList can
      change size at runtime as needed.</p>
    <pre>import java.util.ArrayList; // import ArrayList</pre>
    <p>There are different ways to create an ArrayList. ArrayList support
      generaic programming. If type is not specified, you can store any object
      in it.</p>
    <pre>ArrayList list1 = new ArrayList();
ArrayList list2 = new ArrayList(10);
ArrayList list3 = new ArrayList(list2);
ArrayList&lt;String&gt; list4 = new ArrayList&lt;String&gt;();
ArrayList&lt;String&gt; list5 = new ArrayList&lt;&gt;();
</pre>
    <p>ArrayList support below methods,</p>
    <ul>
      <li>add() - Insert a new value</li>
      <li>remove() - Remove the first matching value</li>
      <li>set() - Change one of the elements</li>
      <li>isEmpty() - Check if empty</li>
      <li>size() - Get size</li>
      <li>clear() - Discard all elements.</li>
      <li>contains() - Check if certain element is in.</li>
      <li>equals() - Check two lists have same elements in same order</li>
    </ul>
    <h3>Java Statements</h3>
    <b>Java if-else Statements</b>
    <pre>// Curly braces required for block of multiple statements, optional for single statement
if(booleanExpression 1) {   // Branch if booleanExpression 1 is True
  ;
} else if(booleanExpression 2) {   // Branch if booleanExpression 2 is True
  ;
} else { //otherwise;
}
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