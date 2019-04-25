---
ID: 901
post_title: Java Classes
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/java/java-classes/
published: true
post_date: 2019-04-04 17:14:17
---
<h2>Java Classes</h2>

<h3>Java Class Inheritance</h3>
<p>Java supports single inheritance, by which a class may inherit from only one direct parent class. 
To truly understand single inheritance, it may helpful to contrast it with multiple inheritance,
by which a class may have multiple direct parents.</p>
<p>Java also supports multiple levels of inheritance, by which one class may extend
another class, which in turn extends another class.</p>
<p>In Java, all classes inherit from a single class, java.lang.Object. Furthermore, java.lang.Object is the only class that doesn’t have any
parent classes. The compiler automatically inserts code into any class you write that doesn’t extend a specific class.</p>

<b>Constructor Definition Rules:</b>
<ul>
<li>The first statement of every constructor is a call to another constructor within the class
using this(), or a call to a constructor in the direct parent class using super().</li>
<li>The super() call may not be used after the first statement of the constructor.</li>
<li>If no super() call is declared in a constructor, Java will insert a no-argument super()
as the first statement of the constructor.</li>
<li>If the parent doesn’t have a no-argument constructor and the child doesn’t define any
constructors, the compiler will throw an error and try to insert a default no-argument
constructor into the child class.</li>
<li>If the parent doesn’t have a no-argument constructor, the compiler requires an explicit
call to a parent constructor in each child constructor.</li>
</ul>

<p>The super() and super are quite different but may be used in the same methods on the exam. The first,
super(), is a statement that explicitly calls a parent constructor and may only be used in
the first line of a constructor of a child class. The second, super, is a keyword used to reference
a member defined in a parent class and may be used throughout the child class.</p>

<p>you may want to define a new version of an existing method in a child class that makes use of the definition in the parent class. In this case, you can override a method by declaring
a new method with the signature and return type as the method in the parent class.</p>
<p>The compiler performs the following checks when you override a non-private method:</p>
<ul>
<li>The method in the child class must have the same signature as the method in the parent
class.</li>
<li>The method in the child class must be at least as accessible or more accessible than the
method in the parent class.</li>
<li>The method in the child class may not throw a checked exception that is new or
broader than the class of any exception thrown in the parent class method.</li>
<li>If the method returns a value, it must be the same or a subclass of the method in the
parent class, known as covariant return types.</li>
</ul>
<p>The @Override annotation is used to express that you intend for this
method to override one in a superclass or implement one from an interface. It is a great idea to get in the habit of using @Override in order to avoid accidentally overloading a method.</p>

<p>When @Override is used, the method is doing one of three things:</p>
<ul>
<li>Implementing a method from an interface</li>
<li>Overriding a superclass method of a class</li>
<li>Overriding a method declared in Object, such as hashCode, equals, or toString</li>
</ul>

<b>Java Overloading vs. Overriding</b>
<p>Overloading a method and overriding a method are similar in that they both involve
redefining a method using the same name. They differ in that an overloaded method will
use a different signature than an overridden method. This distinction allows overloaded
methods a great deal more freedom in syntax than an overridden method would have.</p>

<b>Java Redeclaring private Methods</b>
<p>Java permits you to redeclare a new method in the child class with the same or modified
signature as the private method in the parent class. This method in the child class is a separate
and independent method, unrelated to the parent version’s method, so none of the rules for
overriding methods are invoked.</p>

<b>Java Hiding Static Methods</b>
<p>A hidden method occurs when a child class defi nes a static method with the same name
and signature as a static method defi ned in a parent class.</p>
<b>The five rules for hiding a method</b>
<ul>
<li>The method in the child class must have the same signature as the method in the parent
class.</li>
<li>The method in the child class must be at least as accessible or more accessible than the
method in the parent class.</li>
<li>The method in the child class may not throw a checked exception that is new or
broader than the class of any exception thrown in the parent class method.</li>
<li>If the method returns a value, it must be the same or a subclass of the method in the
parent class, known as covariant return types.</li>
<li>The method defined in the child class must be marked as static if it is marked as
static in the parent class (method hiding). Likewise, the method must not be marked
as static in the child class if it is not marked as static in the parent class (method
overriding).</li>
</ul>

<p>Hiding static methods is fraught
with pitfalls and potential problems and as a practice should be avoided.</p>

<b>Overriding vs. Hiding Methods</b>
<p>There was a distinction between
overriding and hiding methods. Unlike overriding a method, in which a child method
replaces the parent method in calls defined in both the parent and child, hidden methods
only replace parent methods in the calls defined in the child class.</p>

<p>Java final methods cannot be overridden. 
Although marking methods as final prevents them from being overridden, it does have
advantages in practice. For example, you’d mark a method as final when you’re defining
a parent class and want to guarantee certain behavior of a method in the parent class,
regardless of which child is invoking the method</p>

<b>Java Inheriting Variables</b>
<p>The rules for variables with the same name in the parent and child classes are a lot simpler, because Java
doesn’t allow variables to be overridden but instead hidden. 
Although Java allows you to hide a variable defined in a parent class with one defined in
a child class, it is considered an extremely poor coding practice.</p>

<h3>Java Abstract Classes</h3>
<b>Abstract Class Definition Rules:</b>
<ul>
<li>Abstract classes cannot be instantiated directly.</li>
<li>Abstract classes may be defined with any number, including zero, of abstract and nonabstract
methods.</li>
<li>Abstract classes may not be marked as private or final.</li>
<li>An abstract class that extends another abstract class inherits all of its abstract methods
as its own abstract methods.</li>
<li>The first concrete class that extends an abstract class must provide an implementation
for all of the inherited abstract methods.</li>
</ul>

<b>Abstract Method Definition Rules:</b>
<ul>
<li>Abstract methods may only be defined in abstract classes.</li>
<li>Abstract methods may not be declared private or final.</li>
<li>Abstract methods must not provide a method body/implementation in the abstract
class for which is it declared.</li>
<li>Implementing an abstract method in a subclass follows the same rules for overriding a
method. For example, the name and signature must be the same, and the visibility of
the method in the subclass must be at least as accessible as the method in the parent
class.</li>
</ul>

<h3>Java Interfaces</h3>
<p>Although Java doesn’t allow multiple inheritance, it does allow classes to implement any
number of interfaces. An interface is an abstract data type that defines a list of abstract
public methods that any class implementing the interface must provide. An interface can
also include a list of constant variables and default methods.</p>
<p>Define an interface,</p>
<pre>
public abstract interface CanFly {
  public static final int Wings = 2;
  public abstract void fly();
}
</pre>
<b>Java Rules define an interface,</b>
<ul>
<li>Interfaces cannot be instantiated directly.</li>
<li>An interface is not required to have any methods.</li>
<li>An interface may not be marked as final.</li>
<li>All top-level interfaces are assumed to have public or default access, and they must
include the abstract modifier in their definition. Therefore, marking an interface as
private, protected, or final will trigger a compiler error, since this is incompatible
with these assumptions.</li>
<li>All non-default methods in an interface are assumed to have the modifiers abstract
and public in their definition. Therefore, marking a method as private, protected,
or final will trigger compiler errors as these are incompatible with the abstract and
public keywords.</li>
</ul>
<p>Adding the assumed keywords to an interface is a matter of personal
preference, although it is considered good coding practice to do so. Code
with the assumed keywords written out tends to be easier and clearer to
read.</p>

<b>Java Inheriting an Interface</b>
<p>There are two inheritance rules you should keep in mind when extending an interface:</p>
<ul>
<li>An interface that extends another interface, as well as an abstract class that
implements an interface, inherits all of the abstract methods as its own abstract
methods.</li>
<li>The first concrete class that implements an interface, or extends an abstract class
that implements an interface, must provide an implementation for all of the inherited
abstract methods.</li>
</ul>

<p>Inplementing an inerface,</p>
<pre>
public class Bird implements CanFly {
  public void fly() {
    // Yes, you can!
  }
}
</pre>

<b>Interface variables rules:</b>
<ul>
<li>Interface variables are assumed to be public, static, and final. Therefore, marking
a variable as private or protected will trigger a compiler error, as will marking any
variable as abstract.</li>
<li>The value of an interface variable must be set when it is declared since it is marked as
final.</li>
</ul>

<b>Java Default Interface Methods</b>
<p>A default method is a method defined within an
interface with the default keyword in which a method body is provided. Contrast default
methods with “regular” methods in an interface, which are assumed to be abstract and
may not have a method body.</p>

<b>The following are the default interface method rules:</b>
<ul>
<li>A default method may only be declared within an interface and not within a class or
abstract class.</li>
<li>A default method must be marked with the default keyword. If a method is marked as
default, it must provide a method body.</li>
<li>A default method is not assumed to be static, final, or abstract, as it may be used
or overridden by a class that implements the interface.</li>
<li>Like all methods in an interface, a default method is assumed to be public and will not
compile if marked as private or protected.</li>
</ul>
<p>If a class implements two interfaces that have default methods with the same name and
signature, the compiler will throw an error. There is an exception to this rule, though: if
the subclass overrides the duplicate default methods, the code will compile without
issue—the ambiguity about which version of the method to call has been removed.</p>

<b>Java Static Interface Methods</b>
<p>Here are the static interface method rules:</p>
<ul>
<li>Like all methods in an interface, a static method is assumed to be public and will not
compile if marked as private or protected.</li>
<li>To reference the static method, a reference to the name of the interface must be used.</li>
</ul>

<h3>Java Polymophism</h3>
<p>Java supports polymorphism, the property of an object to take on many different forms.</p>

<b>Java Object vs. Reference</b>
<p>In Java, all objects are accessed by reference, so as a developer you never have direct access
to the object itself. Conceptually, though, you should consider the object as the entity that
exists in memory, allocated by the Java runtime environment. Regardless of the type of the
reference you have for the object in memory, the object itself doesn’t change.</p>
<pre>
Object monkey = new Monkey();
</pre>
<p>We can summarize this principle with the following two rules:</p>
<ul>
<li>The type of the object determines which properties exist within the object in memory.</li>
<li>The type of the reference to the object determines which methods and variables are
accessible to the Java program.</li>
</ul>

<b>Java Casting Objects</b>
<p>Here are some basic rules to keep in mind when casting variables:</p>
<ul>
<li>Casting an object from a subclass to a superclass doesn’t require an explicit cast.</li>
<li>Casting an object from a superclass to a subclass requires an explicit cast.</li>
<li>The compiler will not allow casts to unrelated types.</li>
<li>Even when the code compiles without issue, an exception may be thrown at runtime if
the object being cast is not actually an instance of that class.</li>
</ul>
<p>The instanceof operator can be used to check whether an object belongs to a
particular class and to prevent ClassCastExceptions at runtime</p>

<b>Java Virtual Methods</b>
<p>A virtual method is a method in which the specific implementation is not determined until runtime.
In fact, all non-final, nonstatic,
and non-private Java methods are considered virtual methods, since any of them can
be overridden at runtime.</p>
<p>The nature of the polymorphism is that an object can take on many different forms.
By combining polymorphism with method overriding, objects may be interpreted in vastly different ways at runtime, 
especially in methods defined in the superclasses of the objects.</p>

<b>Java Polymorphic Parameters</b>
<p>One of the most useful applications of polymorphism is the ability to pass instances of
a subclass or interface to a method.</p>
<p>If you’re defining a method that will be accessible outside the current class, either to
subclasses of the current class or publicly to objects outside the current class, it is considered
good coding practice to use the superclass or interface type of input parameters
whenever possible.</p>

<b>Java Polymorphism and Method Overriding</b>
<p>We know that a subclass cannot declare an overridden method with a new or broader
exception than in the superclass, since the method may be accessed using a reference to
the superclass. For example, if an instance of the subclass is passed to a method using a
superclass reference, then the enclosing method would not know about any new checked
exceptions that exist on methods for this object, potentially leading to compiled code with 
“unchecked” checked exceptions. Therefore, the Java compiler disallows overriding methods
with new or broader exceptions. </p>
<p>For the same reason, Java disallows a method from being overridden by a less accessible version of the method.
Also, overridden methods must use covariant return types. </p>


<h3>Java Coding equals, hashCode, and toString</h3>
<p>All classes in Java inherit from java.lang.Object, so three of methods in Object are common to override, toString(), equals(), and hashCode(). 
<b>Java toString()</b>
<p>Java automatically calls the toString() method if you try to print out an object.</p>
<pre>
import org.apache.commons.lang.builder.ToStringBuilder;
import org.apache.commons.lang.builder.ToStringStyle;

public class ToStringBuilderTest {
  private int testNum = 123;
  private String testString = "hamburger";
  public static void main(String[] args) {
    Test test = new Test();
    String result = ToStringBuilder.reflectionToString(test, ToStringStyle.MULTI_LINE_STYLE);
    System.out.println(result);
  }
}
</pre>

<b>Java equals()</b>
<p>Java uses == to compare primitives and for checking if two variables refer
to the same object. String does have an equals() method. It checks that the values are the same. StringBuilder uses the implementation of equals() provided by Object, which simply
checks if the two objects being referred to are the same.</p>
<pre>
class Complex {   
    private double re, im; 
    public Complex(double re, double im) { 
        this.re = re; 
        this.im = im; 
    } 
    // Overriding equals() to compare two Complex objects 
    @Override
    public boolean equals(Object o) { 
        if (o == this) { return true; } 
        if (!(o instanceof Complex)) { return false; }           
        Complex c = (Complex) o; 
        return Double.compare(re, c.re) == 0
                && Double.compare(im, c.im) == 0; 
    } 
} 
</pre>
<p>The equals() method implements an equivalence relation on non‐null object references:</p>
<ul>
<li>It is reflexive: For any non‐null reference value x, x.equals(x) should return true.</li>
<li>It is symmetric: For any non‐null reference values x and y, x.equals(y) should return
true if and only if y.equals(x) returns true.</li>
<li>It is transitive: For any non‐null reference values x, y, and z, if x.equals(y) returns
true and y.equals(z) returns true, then x.equals(z) should return true.</li>
<li>It is consistent: For any non‐null reference values x and y, multiple invocations of
x.equals(y) consistently return true or consistently return false, provided no
information used in equals comparisons on the objects is modified.</li>
<li>For any non‐null reference value x, x.equals(null) should return false.</li>
</ul>

<b>Java hashCode()</b>
<p>The hash code is used when storing the object as a key in a map.</p>
<p>The hash code contract:</p>
<ul>
<li>Within the same program, the result of hashCode() must not change. </li>
<li>If equals() returns true when called with two objects, calling hashCode() on each of
those objects must return the same result. </li>
<li>If equals() returns false when called with two objects, calling hashCode() on each of
those objects does not have to return a different result. This means hashCode() results
do not need to be unique when called on unequal objects.</li>
</ul>

<h3>Java Enums</h3>
<p>An enum is a type of class that mainly contains static members. To create an enum, use the enum keyword instead of the class keyword. Then list all of the valid types for that enum.</p>
<pre>
public enum Season {
  WINTER, SPRING, SUMMER, FALL
}
Season s = Season.WINTER;
for(Season season: Season.values()) {
  System.out.println(season.name() + " " + season.ordinal());
}
</pre>
<p>You can’t compare an int and enum value directly.</p>
<p>You can’t extend an enum.</p>

<h3>Java Nested Classes</h3>
<p>A nested class is a class that is defined within another class. A nested class that is not
static is called an inner class. There are four of types of nested classes:</p>
<ul>
<li>A member inner class is a class defined at the same level as instance variables. It is not
static. Often, this is just referred to as an inner class without explicitly saying the type.</li>
<li>A local inner class is defined within a method.</li>
<li>An anonymous inner class is a special case of a local inner class that does not have a
name.</li>
<li>A static nested class is a static class that is defined at the same level as static
variables.</li>
</ul>

<b>Java Member Inner Classes</b>
<p>Member inner classes have the following properties:</p>
<ul>
<li>Can be declared public, private, or protected or use default access</li>
<li>Can extend any class and implement interfaces</li>
<li>Can be abstract or final</li>
<li>Cannot declare static fields or methods</li>
<li>Can access members of the outer class including private members</li>
</ul>
<pre>
public class Outer {
  private String hi= "Hi";
  protected class Inner {
    public void say() {
      System.out.println(hi);
    }
  }
  public static void main(String[] args) {
    Inner inner= new Outer().new Inner();
    inner.say();
  }
}
</pre>
<p>Compiling the Outer.java class creates two class files: Outer.class and Outer$Inner.class. </p>
<p>Inner classes can have the same variable names as outer classes. There is a special way of
calling this to say which class you want to access.</p>
<pre>
public class A {
  private int x = 1;
  class B {
    private int x = 2;
    class C {
      private int x = 3;
      public void allTheX() {
        System.out.println(x);         //3
        System.out.println(this.x);    //3
        System.out.println(B.this.x);  //2
        System.out.println(A.this.x);  //1
      }
    }
  }
  public static void main(String[] args) {
    A.B.C c = new A().new B().new C();
    c.allTheX();
  }
}
</pre>

<b>Java Private Interfaces</b>
<p>All methods in an interface are public. A class that implements the interface must define that method as public. The interface itself does not have to be public. An inner
interface can be private. This means that the interface can only be referred to within the
current outer class.</p>
<pre>
public class C {
  private interface I {
    public void f();
  }
  class B implements I {
    public void f() { }
  } 
}
</pre>

<b>Java Local Inner Classes</b>
<p>A local inner class is a nested class defined within a method. A local
inner class declaration does not exist until the method is invoked, and it goes out of scope
when the method returns. This means that you can create instances only from within the
method.</p>
<p>Local inner classes have the following properties:</p>
<ul>
<li>They do not have an access specifier.</li>
<li>They cannot be declared static and cannot declare static fields or methods.</li>
<li>They have access to all fields and methods of the enclosing class.</li>
<li>They do not have access to local variables of a method unless those variables are final
or effectively final. More on this shortly.</li>
</ul>
<pre>
class Outer {
  public void f() {
    class Inner {
      void fin() {
        System.out.println("fin");
      }
    }
    Inner i = new Inner();
    i.fin();
  }
  public static void main(String args[]) {
    Outer o = new Outer();
    o.f();
  }
}
</pre>

<b>Java Anonymous Inner Classes</b>
<p>An anonymous inner class is a local inner class that does not have a name. It is declared
and instantiated all in one statement using the new keyword. Anonymous inner classes are
required to extend an existing class or implement an existing interface.</p>
<pre>
public class O{
  abstract class I{
    abstract void f();
  }
  public void fo() {
    I i= new I() {
      void f() { }
    };
  }
  public static void main(String args[]) {
    O o = new O();
    o.fo();
  }
}
</pre>

<b>Java Static Nested Classes</b>
<p>A static nested class is a static class defined at the member level. It can be instantiated without an object of the enclosing class, so it can’t access the instance variables without an explicit object of the enclosing class.</p>
<pre>
public class O {
  static class I {
    private int val = 1;
  }
  public static void main(String[] args) {
    I i = new I();
    System.out.println(i.val);
  } 
}
</pre>