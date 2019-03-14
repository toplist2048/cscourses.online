---
ID: 759
post_title: Java Basics
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/java/java-basics/
published: true
post_date: 2019-03-14 17:00:38
---
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
    <h3>Java Source File Structure</h3>
    <p> In java, any real-world object is defined as a class (Object) in a Java
      source file (Object.java). The Java compiler (javac) compiles Object.java
      to bytecode (Object.class) and then JVM (Java Virtural Machine) (java) run
      Object.class directly.</p>
    <p>A Java source file can also define Java entities such as interface, enum,
      etc. </p>
    <h4>Java Comments</h4>
    <p>Comments make your code easier to read.</p>
    <p>Multi-line comments start with /* and end with */ and can span multiple
      lines .</p>
    <p>End-of-line comments start with // and end in the line they reside.</p>
    <p>Javadoc comments have special syntax that start with /** and end with */.
      These comments are processed by Javadoc to generate API documentation. </p>
    <h4>Java Classes</h4>
    <b>Java Class Definition</b>
    <pre lang="java">public final class Cat extends Animal implements Pet { }
</pre>
    <p>The definition of a class is made of the following parts:</p>
    <ul>
      <li>Access modifiers, public, optional</li>
      <li>Non-access modifiers, final, optional</li>
      <li>Keyword class and class name Cat</li>
      <li>keyword extends and base class name Animal if extending a base class</li>
      <li>keyword implements and all implemented interfaces, here is Pet, when
        implementing any interfaces</li>
      <li>Class body (fields, methods, constructors), included within a pair of
        curly braces {} </li>
    </ul>
    <b>Java variables</b>
    <p>A local variable is a variable defined within a method.Instance variables
      are used to store the state of an object (instance). Class variables
      (static variables) are shared by all the objects of a class.</p>
    <p>Local variables must be initialized before use. They do not have a
      default value. Instance and class variables do not require you to
      initialize them.</p>
    <p>Local variables has a scope from declaration to end of block. Instance
      variables has a scope from declaration until object garbage collected.
      Class variables has a scope from declaration until program ends.</p>
    <b>Java methods</b>
    <p>Instance methods can manipulate both instance variables and static
      variables.</p>
    <p>Class methods or static methods can manipulate the static variables.</p>
    <p>class constructors are used to create and initialize the objects of a
      class.</p>
    <pre lang="java">class Cat {
  String name;
  Cat(String name) { this.name = name; }
  void walk() {}
}</pre>
    <p>You can put several classes in one file. When you do so, at most one of
      the classes in the file is allowed to be public </p>
    <h4>Java Packages</h4>
    <b>Java package Statement</b>
    <p>A Java class can be explicitly defined in a named package; otherwise, it
      becomes part of a default package, which doesn’t have a name. </p>
    <p>A package statement is used to explicitly define which package a class is
      in. The package statement must be the first statement in the class
      definition.</p>
    <pre lang="java">package animal;
class Cat{ }
</pre> <b>Java import Statement</b>
    <p>To use a class/interface from another package, you must use its fully
      name, that is, packageName.subPackageName.ClassName. or you can use the
      import statement and then use the ClassName directly.</p>
    <pre>import aminal.Cat;</pre>
    <p>Classes in the same package are often imported together. You can use a
      shortcut to import all the classes in a package. Note a wildcard only
      matches class names</p>
    <pre>import aminal.*;</pre>
    <p>Some system packages, such as java.lang, are automaticlly imported.</p>
    <p>Sometimes you want to use Date from two different packages. When this
      happens, you can pick one to use in the import and use the other’s fully
      qualified class name.</p>
    <h4>Java Interface Definition</h4>
    <p>An interface specifies a contract for the classes to implement. The
      methods in an interface can define a default implementation. Interfaces
      can also define static methods.</p>
    <pre>interface Pet {
 public play();
}</pre>
    <h3>Java "Hello, World!"</h3>
    <p>JVM run an executable Java class from the main method. </p>
    <pre lang="java">public class Main {
  public static void main(String args[]) {
    System.out.println("Hello, World");
  }
}</pre>
    <p>The method must be public, be static, return a void value, be named as
      main, and accept String array as parameters. </p>
    <p>Now we can compile and run it.</p>
    <pre>$ javac Main.java 
$ java Main 
Hello, World!
$ 
</pre>
    <p>Another example which has class, sub-class and interface:</p>
    <p>The files are,</p>
    <pre>src
├── animal
│&nbsp;&nbsp; └── Cat.java
├── Animal.java
├── Main.java
└── Pet.java
</pre>
    <p>animal/Cat.java</p>
    <pre lang="java">package animal;
import base.*;
public class Cat extends Animal implements Pet{
  public Cat(String name) { super(name); }
  public void play() { System.out.println("Cat play!"); }
}
</pre>
    <p>Animal.java</p>
    <pre>package base;
public class Animal {
  String name;
  public Animal(String name) { this.name = name; }
  public String getName() { return this.name; }
  public void hello() { System.out.println("Hi, this is " + this.name); }
}</pre>
    <p>Main.java</p>
    <pre>import animal.Cat;

public class Main {
  public static void main(String args[]) {
    Cat cat = new Cat("Tom");
    cat.hello();
    cat.play();
  }
}
</pre>
    <p>Pet.java</p>
    <pre>package base;
public interface Pet {
  public void play();
}</pre>
    <p>Command to compile and run them</p>
    <pre>$ javac -d . -sourcepath src src/Animal.java  src/Pet.java src/Main.java src/animal/Cat.java 
$ java Main 
Hi, this is Tom
Cat play!
$</pre>
    <p>Java provides a garbage collector to automatically look for objects that
      aren’t needed anymore.</p>
    <p>An object is no longer reachable when one of two situations occurs: </p>
    <ul>
      <li>The object no longer has any references pointing to it.</li>
      <li> All references to the object have gone out of scope.</li>
    </ul>
    <p>Java allows objects to implement a method called finalize() that might
      get called. This method gets called if the garbage collector tries to
      collect the object. If the garbage collector doesn’t run, the method
      doesn’t get called. If the garbage collector fails to collect the object
      and tries to run it again later, the method doesn’t get called a second
      time.</p>
    <h3>Java Primitives</h3>
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
    <h3>Java References</h3>
    <p>Java reference is a pointer to a object located in memory. Reference
      types can be assigned null , which means they do not currently refer to an
      object.</p>
    <pre>String str = "Hello, World!";</pre>
    <h3>Java Identifiers</h3>
    <ul>
      <li>The name must begin with a letter or the symbol $ or _ </li>
      <li>Subsequent characters may also be numbers.</li>
      <li>You cannot use the same name as a Java reserved word.</li>
    </ul>
  </body>
</html>