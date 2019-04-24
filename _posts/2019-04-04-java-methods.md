---
ID: 896
post_title: Java Methods
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/java/java-methods/
published: true
post_date: 2019-04-04 14:54:08
---
<h2>Java Methods</h2>

<h3>Java Method Design</h3>
<p>A typical Java method is declared below,</p>
<pre>
access_modifier optional_specifier return_type method_name(parameter_list) exception {
// method body
}
</pre>
<p>Note, access modifier, optional specifier, parameter_list, and exception are optional. The return type might be an
actual Java type. If there is no return type, the void keyword is used.</p>
<p>A method may use a vararg parameter (variable argument) as if it is an array.</p>
<pre>
public void count(int... nums) { }
</pre>

<b>Java Access Modifiers</b>
<ul>
<li>public - The method can be called from any class.</li>
<li>protected - The method can only be called from classes in the same package or sub-classes.</li>
<li>Default (Package Private Access) - The method can only be called from classes in the same 
package. This one is tricky because there is no keyword for default access. You simply omit
the access modifier.</li>
<li>private - The method can only be called from within the same class.</li>
</ul>

<p>The protected rules apply under two scenarios:</p>
<ul>
<li>A member is used without referring to a variable. In this case, we are taking advantage of inheritance and protected access is allowed.</li>
<li> A member is used through a variable. In this case, the rules for the reference type of the variable are what matter. If it is a subclass, protected access is allowed.
</ul>

<pre>
// in file a.java
package pa;
public class a {
  protected void m_a() { // protected access
  } 
}

// in file b.java
package pb;
import pa.A; // in different package
public class B extends A {
  public void swim() {
    m_a(); // access to superclass
  }
  public void helper_B() {
    B b = new B();
    b.m_a(); // access to superclass
  }
  public void helper_A() {
    A a = new A();
    a.m_a(); // DOES NOT COMPILE
  }
}
</pre>

<b>Access modifiers</b>
<table>
<thead>
<tr><td>
Can access</td><td>
If that member is private?</td><td>
If that member has default (package private) access?</td><td>
If that member is protected?</td><td>
If that member is public?</td><td>
</td></tr>
</thead>
<tbody>
<tr><td>Member in the same class</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr>
<tr><td>Member in another class in same package</td><td>No</td><td>Yes</td><td>Yes</td><td>Yes</td></tr>
<tr><td>Member in a super-class in a different package</td><td>No</td><td>No</td><td>Yes</td><td>Yes</td></tr>
<tr><td>Method/field in a nonsuperclass class in a different package</td><td>No</td><td>No</td><td>No</td><td>Yes</td></tr>
</tbody>
</table>

<b>Java Optional Specifiers</b>
<ul>
<li>static - Used for class methods.</li>
<li>abstract - Used when not providing a method body.</li>
<li>final - Used when a method is not allowed to be overridden by a subclass.</li>
<li>synchronized - multi-threading synchronized.</li>
<li>native - Used when interacting with code written in another language such as C++.</li>
<li>strictfp - Used for making floating-point calculations portable.</li>
</ul>

<h3>Java Static Methods and Fields</h3>
<p>Each class has a copy of the instance variables. There is only one copy of the code for the
instance methods. However, each call of an instance method (or any method) gets space on the stack for method parameters and local variables.</p>
<p>The same thing happens for static methods. There is one copy of the code. Parameters
and local variables go on the stack.</p>
</p>Only data gets its "own copy." There is no need to duplicate copies of the code itself.</p>

<p>static methods have two main purposes:</p>
<ul>
<li>For utility or helper methods that don’t require any object state. Since there is no need
to access instance variables, having static methods eliminates the need for the caller to
instantiate the object just to call the method.</li>
<li>For state that is shared by all instances of a class, like a counter. All instances must
share the same state. Methods that merely use that state should be static as well.</li>
</ul>

<p>Accessing a static member is easy. You just put the class name before the method or
variable and you are done.</p>
<p>A static member cannot call an instance member. This shouldn’t be a surprise since static doesn’t require any instances of the class to be around. A static method or instance method can call a static method because static methods don’t require an object to use. Only an instance method can call another instance method on the same class without using a reference variable, because instance methods do require an object. Similar logic applies for the instance and static variables.</p>

<b>Static vs. instance calls</b>
<table><thead>
<tr><td>Type</td><td>Calling</td><td>Legal?</td><td>How?</td></tr>
</thead>
<tbody>
<tr><td>Static method</td><td> Another static method or variable</td><td> Yes</td><td> Using the classname</td></tr>
<tr><td>Static method</td><td> An instance method or variable</td><td> No</td><td></td>&nbsp;</tr>
<tr><td>Instance method</td><td> A static method or variable</td><td> Yes</td><td> Using the classname or a reference variable</td></tr>
<tr><td>Instance method</td><td> Another instance method or variable</td><td> Yes</td><td> Using a reference variable</td></tr>
</tbody>
</table>

<b>Java Static Variables</b>
<p>Some static variables are meant to change as the program runs. 
Other static variables are meant to never change during the program. This type of variable
is known as a constant. It uses the final modifier to ensure the variable never changes.
static final constants use a different naming convention than other variables. They use
all uppercase letters with underscores between "words".</p>

<b>Java Static Initialization</b>
<p>Java instance initializers that looked like unnamed methods. Just code
inside braces. Static initializers look similar. They add the static keyword to specify they
should be run when the class is first used.
The static initializer runs when the class is first used. The statements in it run
and assign any static variables as needed.</p>
<pre>
static {
  // Init code here
}
</pre>
<p>Using static and instance initializers can make your code much harder to read.
Everything that could be done in an instance initializer could be done in a constructor
instead. The constructor approach is easier to read.
There is a common case to use a static initializer: when you need to initialize a
static field and the code to do so requires more than one line. This often occurs
when you want to initialize a collection like an ArrayList. When you do need to
use a static initializer, put all the static initialization in the same block. That way,
the order is obvious.</p>

<b>Java Static Imports</b>
<p>There is a special type of import called a static import. Regular
imports are for importing classes. Static imports are for importing static members of
classes.</p>
<pre>
import static java.util.Arrays.asList;
</pre>

<h3>Java Pass-by-Value</h3>
<p>Different languages handle parameters in different ways. Pass-by-value is used by many
languages, including Java.</p>
<p>The other approach is pass-by-reference. It is used by default in a few languages, such as
Perl.</p>

<h3>Java Overloading Methods</h3>
<p>Method overloading occurs when
there are different method signatures with the same name but different type parameters. 
Notice that the access modifier and exception list are irrelevant to overloading. If two methods differ only return type, they will not compile. If the only difference is that one is an instance method and one is a static method, it will not compile.</p>

<b>Order Java uses to choose the right overloaded method</b>
<table>
<thead>
<tr><td>Rule</td><td>Example of what will be chosen for f(1,2)</td></tr>
</thead>
<tbody>
<tr><td>Exact match by type</td><td>public String f(int i, int j) {}</td></tr>
<tr><td>Larger primitive type</td><td>public String f(long i, long j) {}</td></tr>
<tr><td>Autoboxed type</td><td>public String f(Integer i, Integer j) {}</td></tr>
<tr><td>Varargs</td><td>public String f(int... nums) {}</td></tr>
</tbody>
</table>

<h3>Java Constructors</h3>
<p>Every class in Java has a constructor whether you code one or not. If you don’t include any
constructors in the class, Java will create one for you without any parameters.</p>
<p>Java constructors can be overloaded. Overloaded constructors often call each other. One common technique is to have each
constructor add one parameter until getting to the constructor that does all the work.
This approach is called constructor chaining.</p>

<b>Java Order of Initialization</b>
<ul>
<li>If there is a superclass, initialize it first </li>
<li>Static variable declarations and static initializers in the order they appear in the file.</li>
<li>Instance variable declarations and instance initializers in the order they appear in the file.</li>
<li>The constructor.</li>
</ul>


<h3>Java Lambdas</h3>
<p>Functional programming uses lambda expressions to write code. A lambda expression
is a block of code that gets passed around. You can think of a lambda expression as an
anonymous method.</p>
<p>A java lambda has below parts, </p>
<ul>
<li>Specify parameter list</li>
<li>The arrow operator to separate the parameter and body</li>
<li>A body</li>
</ul> 
<pre>
print(() -> true); // 0 parameters
print(a -> a.startsWith("test")); // 1 parameter
print((String a) -> a.startsWith("test")); // 1 parameter
print((a, b) -> a.startsWith("test")); // 2 parameters
print((String a, String b) -> a.startsWith("test")); // 2 parameters
</pre>