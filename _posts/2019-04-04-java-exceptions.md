---
ID: 906
post_title: Java Exceptions
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/java/java-exceptions/
published: true
post_date: 2019-04-04 17:18:15
---
<h2>Java Exceptions</h2>
<p>An Java exception is the way to handle coding error or unexpected conditions when the program runs. </p>
<p>The java.lang.Throwable is the superclass for all java.lang.Exception and java.lang.Error. The java.lang.Exception is the superclass of java.lang.RuntimeException.</p>
<li>Error means something went wrong that your program should not attempt to recover from it.</li>
<li>A runtime exception, RuntimeException, tend to be unexpected but not necessarily fatal. Runtime exceptions are also known as unchecked exceptions. </li>
<li>A checked exception includes Exception and all subclasses that do not extend
RuntimeException. For checked exceptions, Java requires the code to either handle them or declare them in the method signature.</li>
<pre>
void fall() throws Exception {
  throw new Exception();
}
</pre>
<p>Notice the difference of throw and throws. throw tells Java that you want to
throw an Exception. throws simply declares that the method might throw an Exception. It
also might not.</p>
<p>In the past, developers used checked exceptions more often than they do now. 
Then developers started writing code where a chain of methods kept
declaring the same exception and nobody actually handled it. Now libraries started
using runtime exceptions for issues a programmer might reasonably be expected to
recover from. </p>
<b>Java Types of exceptions</b>
<table>
<thead>
<tr><td>Type</td><td>How to recognize</td><td>Okay for program to catch?</td><td>Is program required to handle or declare?</td></tr>
</thead>
<tbody>
<tr><td>Runtime exception</td><td>Subclass of RuntimeException</td><td>Yes</td><td>No</td></tr>
<tr><td>Checked exception</td><td>Subclass of Exception but not subclass of RuntimeException</td><td>Yes</td><td>Yes</td></tr>
<tr><td>Error</td><td>Subclass of Error</td><td>No</td><td>No</td></tr>
</tbody>
</table>

<b>Java try Statement</b>
<pre>
try { // The curly braces are required even if there is only one statement inside the code blocks. 
  // The try block is also referred to as protected code.
  // If an exception is thrown in a try statement, the catch clauses attempt to catch it.
} catch ( exception_type identifier ) { // The identifier refers to the caught exception object.
  //exception handler
} finally {
  //finally block //The finally block always executes, whether or not an exception occurs in the try block.
}
</pre>
<p>If an exception is thrown in a try statement, the catch clauses attempt to catch it.</p>
<p>The finally block always executes, whether or not an exception occurs in the try block.
If an exception is thrown, the finally block is run after the catch block. 
If no exception is thrown, the finally block is run after the try block completes.
There is one exception to “the finally block always runs after the catch block” rule:
Java defines a method that you call as System.exit(0);. The integer parameter is the
error code that gets returned.</p>

<h3>Java Common Exception Types</h3>
<b>Runtime Exceptions</b>
<p>Runtime exceptions extend RuntimeException. They don’t have to be handled or declared.
They can be thrown by the programmer or by the JVM. Common runtime exceptions include:</p>
<ul>
<li>ArithmeticException - Thrown by the JVM when code attempts to divide by zero</li>
<li>ArrayIndexOutOfBoundsException - Thrown by the JVM when code uses an illegal index to access an array</li>
<li>ClassCastException - Thrown by the JVM when an attempt is made to cast an exception to a subclass of which it is not an instance</li>
<li>IllegalArgumentException - Thrown by the programmer to indicate that a method has been passed an illegal or inappropriate argument</li>
<li>NullPointerException - Thrown by the JVM when there is a null reference where an object is required</li>
<li>NumberFormatException - Thrown by the programmer when an attempt is made to convert a string to a numeric type but the string doesn’t have an appropriate format</li>
</ul>

<b>Checked Exceptions</b>
<p>Checked exceptions are subclass of Exception but not RuntimeException. They
must be handled or declared. They can be thrown by the programmer or by the JVM.</p>
<ul>
<li>FileNotFoundException - Thrown programmatically when code tries to reference a file that does not exist</li>
<li>IOException - Thrown programmatically when there’s a problem reading or writing a file</li>
</ul>

<b>Errors</b>
<p>Errors extend the Error class. They are thrown by the JVM and should not be handled or declared.</p>
<ul>
<li>ExceptionInInitializerError - Thrown by the JVM when a static initializer throws an exception and doesn’t handle it</li>
<li>StackOverflowError - Thrown by the JVM when a method calls itself too many times (this is called infinite recursion because the method typically calls itself without end)</li>
<li>NoClassDefFoundError - Thrown by the JVM when a class that the code uses is available at compile time but not runtime</li>
</ul>
<p>When you’re calling a method that throws an checked exception, the exception
must be handled or declared.</p>
<p>A subclass is allowed to declare fewer exceptions than the superclass or interface. This is legal because callers are already handling them.</p>

<b>Java Printing an Exception</b>
<p>You can let Java print it out, print just the mes-sage, or print where the stack trace comes from.</p>
<pre>
try {
  hop();
} catch (Exception e) {
  System.out.println(e);
  System.out.println(e.getMessage());
  e.printStackTrace();
}
</pre>