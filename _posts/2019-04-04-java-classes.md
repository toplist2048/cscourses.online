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

<h3>Java Class Inheritance<h3>
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

<p>you may want to define a new version of an existing method in a child class that makes use of the
definition in the parent class. In this case, you can override a method by declaring
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

<h3>Java Abstract Classes<h3>
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
<li>Abstract methods may only be defined in abstract classes.<li>
<li>Abstract methods may not be declared private or final.<li>
<li>Abstract methods must not provide a method body/implementation in the abstract
class for which is it declared.<li>
<li>Implementing an abstract method in a subclass follows the same rules for overriding a
method. For example, the name and signature must be the same, and the visibility of
the method in the subclass must be at least as accessible as the method in the parent
class.<li>
</ul>

<h3>Java Interfaces<h3>
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

<h3>Java Polymophism<h3>
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