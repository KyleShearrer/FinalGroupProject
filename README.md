# Object Oriented Final Group Project, Comparing Java and Kotlin

### Written BY:
* Andy Ziber
* Jordan Wieberg
* Kyle Shearrer
* Jordan Liebman

# Comparison Criteria
## Language purpose/genesis
  ### Why was the language created?
  #### Java
  The language was created to be used on a variety of day-to-day products. There were 5 principles in the creation of Java.
  1. It must be "Simple, object-oriented, and familiar"
  2. It must be "robust and secure"
  3. It must be "archituecture-nuetral and portable"
  4. it must execute with "high performance"
  5. it must be "interpreted threaded, and dynamic"
  #### Kotlin
  Kotlin was created to basically replace java. The creators realzied that java had run its corse and there are obvious problems with Java that need to be fixed.
  ### What problems was the language trying to address?
  #### Java
  The problem java was trying to fix was to have greater uniformity and simplicity within the language unlike C/C++. They wanted to make a language where is was extremely reliable language and could work on any machine. They slogan they had while making Java was "Write Once, Run Anywhere"
   #### Kotlin
   The problems that the language was trying to fix was that Java was from a different time and need a fresh update to bring into the modern age. The main goal was to update and condense java and make it more user friendly.
  ### Is the language a reaction to a previous language or a replacement for another language?
  #### Java
  Java was a reaction to C/C++ and also a attempted replacement of them. Java wanted to provide a simple and more uniformed experience then C/C++.
  #### Kotlin
  Kotlin was a replacement for java. Kotlin still uses parts of Java and even in your Kotlin code you can use Java code in it.
## Unique features of the language
  ### Does the language have any particularly unique features?
  #### Java
  The most unique feature of java is how it is able to run on about anything. It is extremely reliable and portable. It is platform independent so java has the ability to run the same program on many different systems with no hiccups. Even a toaster could probably run a java program.
  #### Kotlin
  The most unique feature of Kotlin is that Kotlin and Java code can be intertwined in the same program. In you Kotlin program you can add java code in the middle and the program will work just fine.

## Name spaces
  ### How are name spaces implemented?
  #### Java
  Name spaces are implemented in java in the use of packagaes. Packagaes are a named collection of classes and subclasses. They are like folders on a computer
  #### Kotlin
  Name spaces are used in the form of packages, like java. They act like a folder and contain files inside of them. They contian classes and sublacsses.
  ### How are name spaces used?
  #### Java
  ```java
  //in the Draggable.java file
  package movie;
  public interface Scenes {
      . . .
  }

  //in the Graphic.java file
  package movies;
  public abstract class Graphic {
      . . .
  }

  //in the Act.java file
  package movies;
  public class Act extends Graphic
      implements Scenes {
      . . .
  }
  ```
  #### Kotlin
  ```Kotlin
  package food.bar
  fun hotdog(){}
  class Buns{}
  ```
## Types
  ### What types does the language support?
  Both java and kotlin have the same basic primative types . As in bytes, char, short, int, long, float, double, boolean, void. When delcaring types in kotlin you do not need to delcare a data type because it is not a strongly worded langauge and the language itself will be able to determine what the variable type needs to be.
  ### Are both reference and value types supported?
  #### Java
  Java supports both refernce and value types. The basic primative types are value types but objects like strings are reference tpyes.
  ```Java
  public class Dogs{
  //call by value
  int age = 1;
  //call by reference
  String name = "Nelson";
  }
  ```
  #### Kotlin
  Kotlin also supports both reference and value types.
  ```Kotlin
  class Dogs{
  val firstName: String = "Chess"
  val fistName1 = "Chess"
  
  val age: Int = 2
  val age1 = 2
  }
  ```
  
  ### Can new value types be created?
  No new value types can not be created.
## Classes
  ### Defining
  #### Java
  ```Java
  public class Dog{
  }
  ```
   #### Kotlin
    ```kotlin
    class Money {
    }
    ```
  ## Creating new instances
  #### Java
  ``` Java
  Dog hotDog = new Dog();
  ```
  #### Kotlin
  ``` Kotlin
  val money = Money()
  val customer = Customer("Billy Bob Thornton")
  ``` 
  ## Constructing/initializing
  #### Java
  ``` Java
  Dog hotDog = new Dog()
  Constructing/initializing
  public class Dog{
  }
  Dog(string breed){
  }
  Pet(string breed, string name, int age){
  }
  }
  ```
  Constructors are called when they are given the correct arguments
  ``` Java
  Dog paul = new Dog();
  Dog paully = new Dog("paul");
  Dog Randy = new Dog('Chow Chow', 'Randy', 13);
  ```
  #### Kotlin
  Each class has one primary constructors and then secondary constructors
``` Kotlin
class Person constructor(firstName: String) {
}
```
Primary Constructors can not contain any code in it. The keyword init can be used to of initialization to implement code
``` Kotlin
class InitOrderDemo(name: String) {
    val firstProperty = "First property: $name".also(::println)

    init {
        println("First initializer block that prints ${name}")
    }
}
```
If the class already has a primary constructor then it can have a secondary constructor
```Kotlin
class Person {
    constructor(parent: Person) {
        parent.children.add(this)
    }
}
```
  ## Destructing/de-initializing
  Both Java and Kotlin have a form of a garbage collector that destroys objects when they are no longer in use.
## Instance reference name in data type (class)
#### Java
The most common use of the “this” keyword is when referencing object’s fields in a constructor. If you have the parameters of your constructor with the same names and types as the object’s fields, the “this” keyword is used to refer to the object’s fields.  “This” can also be used to call another constructor inside another constructor in the same class.  The constructors have to have similar parameters. 
```java
public class ThisJava {
    private int first;
    private int second;
    private int third;
    private int fourth;
    
    public ThisJava(int first, int second) {
        this.first = first;
        this.second = second;
    }
    
    public ThisJava(int first, int second, int third, int fourth) {
        this(first, second);
        this.third = third;
        this.fourth = fourth;
    }
}
```
#### Kotlin
The “this” keyword is used similarly in Kotlin.  Since Kotlin has primary constructors built when naming the class, the “this” keyword is used with secondary constructors.   “This” can also be used to refer to the current object/property of the class.
```kotlin
class ThisKotlin(t: Int) {
    var k = this@ThisKotlin
    
    var number1 = BigDecimal(1)
    var number2 = 2.bd

    private val Int.bd: BigDecimal
        get() = BigDecimal(this)
}
class Noun {
    var person: String

    constructor(person: String) {
        this.person = person
    }
}
```
## Properties
#### Java
When trying to reach or change properties in your object, you the programmer have to write the code for getters and setters.  Since Java has you code your own getter and setters, backing fields are not needed, and computer properties are basically just the getter methods.
```java
public class PropertiesJava {
    private String property;
    
    public String getProperty() {
        return property;
    }
    
    public void setProperty(String property) {
        this.property = property;
    }
}
```
#### Kotlin
When trying to reach or change properties in your object, Kotlin automatically has getters and setters built in when building a class.  But you can build your own custom getters and setters to do what you want specifically.  A computed property (fullname), a field that doesn’t store a value but can make a custom getter to grant property access, can be used in Kotlin.  You simply make a new field and create your getter in the next line underneath it.  Backing fields (property) are used when you want to write out the code for basic getters and setters.  You use backing fields by using the keyword “field”.
```kotlin
class PropertiesKotlin (var firstname: String, var lastname: String)  {

    val fullname : String
        get() = "$firstname $lastname"

    var property = ""
        get() = field
        set(value) {field = value}
}
```
## Interfaces / Protocols
#### Java
Java allows interfaces to be implemented with classes.  Interfaces in Java allows a group of empty methods to be implemented with one or more classes.  The methods in the interface are not allowed to have any code in them.  Fields are also not allowed in Java interfaces.  To implement an interface, you write the keyword “implements” along with the name of said interface after declaring the name of the class.  Once an interface is implemented, Java forces you to define all the methods of the interface into the class along with the “@Override” annotation before each method.  The interface and all its methods must be declared public in Java.
```java
public interface InterfaceJava {
    public void method();
    
    public int method2(int field);
}
public class JavaClass implements InterfaceJava {
    @Override
    public void method() {
        
    }
    
    @Override
    public int method2(int field) {
        return field + 1;
    } 
}
```
#### Kotlin
Interfaces in Kotlin work similarly as with Java, but with a few differences.  Kotlin allows properties and methods with code already inside of it to also be implemented in interfaces.  When implementing an interface with a class, you write a colon and the name of the interface after declaring the name of the class.  Kotlin also forces users to define all methods and properties of the interface into the class.  You also need to use an override annotation before each method and property, but that’s just the word “override” before each member. When defining a filled method with code in a class, you can use the interface’s code by using the “super” keyword or writing your own code.
``` kotlin
interface InterfaceKotlin {
    val property: String

    fun doSomething(prop: Int): Int {
        return prop + 1
    }

    fun doNothing()
}
class ClassKotlin : InterfaceKotlin {
    override val property: String = "property"

    override fun doSomething(prop: Int): Int {
        if (prop == 0) return super.doSomething(prop)
        else return prop + 2
    }

    override fun doNothing() {
        println("I will not do something!")
    }
}
```
## Inheritance / extension
#### Java
Java allows classes to extend their fields and methods to other classes.  Constructors cannot be inherited but the constructor of the superclass can be called in the subclass.  You do use inheritance by writing “extends” and the name of the class that has the methods you would like to use.  To use to the superclass’ members, you have to use the “super” keyword.  If you want the purpose of a method to change, you use the “@Override” annotation and write the new code in the method.  Private members of the superclass cannot be inherited to the subclass.  You can also add as many more fields and methods as you’d like in the subclass.  Java does not support extension methods.
``` java
public class ExtendJava extends Class {
    public int field2;
    
    public ExtendJava(int field) {
        super(field);
    }
    
    @Override
    public void method(int field) {
        field = super.method2(super.field);
    }   
}
class Class {
    public int field;
    private int field2;
    
    Class(int field) {
        this.field = field;
    }
    
    public void method(int field) {
        
    }
    
    public int method2(int field) {
        return field + 1;
    }
}
```
#### Kotlin
Kotlin’s inheritance works similarly with Java’s.  To show a subclass is inheriting from a superclass, the superclass is listed with the name of the subclass along with a “:”.  To rewrite a superclass method in the subclass, you simply add the “override” keyword similarly to Java.  If you want a method or field to be inherited by the subclass, you must add the “open” keyword with the class name and field or method you want to use.  If you don’t want a field or method to be inherited, use the “final” keyword.  The “super” keyword works similarly with Java’s super.  Inner classes in the subclass can also access members of the superclass by using the “super” keyword along with a label of the subclass.  Kotlin does support extension functions and extension properties.  Extensions allow programmers to extend from a class without having to inherit from the actual class.  You can create extensions for classes that are already in Kotlin as well (ex. ArrayList).  To create an extension function from a class, you code a function with the class name along with the function name.  Then you write whatever you want your function to do.  Writing an extension property is similar to an extension function, except with a getter instead of code inside of a function.
``` kotlin
class ExtendKotlin(): Class() {
    override var field: Int = 2;

    override fun method(): Int {
        return super.method2(super.field + 3)
    }

    inner class Extend {
        fun method3() {
            super@ExtendKotlin.field = 8;
        }
    }

}
open class Class() {
    open var field: Int = 0
    final var field2: String = ""

    open fun method(): Int {
        return 0
    }

    final fun method2(field: Int): Int {
        return field + 1
    }

    val ArrayList<Int>.middle: Int
        get() = size%2
}
fun main(args: Array<String>) {
    fun Class.newMethod() {
        println("I'm an extension")
    }

    val newClass = Class()
    newClass.newMethod()

    fun ArrayList<Int>.increment(i1: Int, i2: Int, i3: Int) {
        this[i1].inc()
        this[i2].inc()
        this[i3].inc()
    }
    val array = arrayListOf(55, 56, 53)
    array.increment(0, 1, 2)
}
```
## Reflection
#### Java
Reflection is an API used to give programmers information about a class to which an object is from including fields, constructors, and methods. Reflection can also allow access to members of a class to be used similarly with inheritance and even private members of a class can be used.  To use reflection you simply create an instance of a class and use the getClass() method to gain access to many other get methods that gives you information about the class.  To be able to use the methods from the class, you must first declare a method and have it equal to the class’s declared method with its parameters including the name of the method and its parameters.  Then use the invoke method.  And if you want access to private members of the class, you first have to set its accessibility to true. 
``` java
import java.lang.reflect.Method;
import java.lang.reflect.Field;

public class ReflectJava {
    private String name;

    public ReflectJava()  {
        name = "Bob"; 
    }
 
    public void method()  {
        System.out.println("My name is " + name);
    }
 
    public void method2(int n)  {
        System.out.println(n + " + 1 = " + (n+1));
    }

    private void method3() {
        System.out.println("Private method has been called");
    }
    public String getName() {
        return this.name;
    }
    public void setName(String name) {
        this.name = name;
    }
}
class Main {
    public static void main(String args[]) throws Exception {
        ReflectJava reflect = new ReflectJava();
        
        System.out.println("The class's package name is " + reflect.getClass().getPackage());
    
        System.out.println("The class's name is " + reflect.getClass().getSimpleName());
        
        System.out.println("The class's name is " + reflect.getClass().getCanonicalName());
        
        System.out.println("The class's constructor name is " + reflect.getClass().getConstructor().getName());
        
        System.out.println("The class's field is " + reflect.getClass().getDeclaredField("name"));
        
        System.out.println("The class's public methods are");
        Method[] methods = reflect.getClass().getMethods();
        for(Method method:methods) {
            System.out.println("\t" + method.getName());
        }
        
        Method method = reflect.getClass().getDeclaredMethod("method");
        Field field = reflect.getClass().getDeclaredField("name");
        field.setAccessible(true);
        field.set(reflect, "Shirley");
        method.invoke(reflect);
        
        Method method2 = reflect.getClass().getDeclaredMethod("method2", int.class);
        method2.invoke(reflect, 7);
        
        Method method3 = reflect.getClass().getDeclaredMethod("method3");
        method3.setAccessible(true);
        method3.invoke(reflect);
    }
}
```
#### Kotlin
Kotlin’s reflection can work almost the exact same as Java if you use the javaClass function reference which allows access to all of the same methods used for reflection in Java.  But Kotlin’s way of reflection is using the “::” operator.  The “::” operator is used for creating a reference to a class’s function/class/variable.  You can also use the operator to reference functions, compose to functions together, and reference properties.
``` kotlin
import kotlin.reflect.full.declaredMemberFunctions
import kotlin.reflect.full.declaredMemberProperties

class ReflectKotlin(val name: String, val num: Int) {
    fun method() {
        System.out.println("My name is " + name)
    }

    fun method2(num: Int) {
        println("$num + 1 = ${num+1}")

    }

    private fun method3() {
        println("Private method has been called")
    }
}
fun main(args: Array<String>) {
    val reflect = ReflectKotlin("Bob", 10)

    println("Class Name: ${reflect.javaClass.simpleName}")

    reflect.javaClass.declaredFields.forEach {
        println("Type:${it.type} Name:${it.name}")
    }
    reflect.javaClass.declaredMethods.forEach {
        println("Name:${it.name} Return Type:${it.returnType}")
    }

    val method = reflect.javaClass.getDeclaredMethod("method")
    val field = reflect.javaClass.getDeclaredField("name")
    field.setAccessible(true)
    field.set(reflect, "Shirley")
    method.invoke(reflect)

    val method2 = reflect.javaClass.getDeclaredMethod("method2", Int::class.javaPrimitiveType)
    method2.invoke(reflect, 99)

    val method3 = reflect.javaClass.getDeclaredMethod("method3")
    method3.setAccessible(true)
    method3.invoke(reflect)

    val c = ReflectKotlin::class
    for (func in c.declaredMemberFunctions) {
        println(func.name)
    }
    for (vari in c.declaredMemberProperties) {
        println(vari.name)
    }
    val d = ReflectKotlin::num

    fun isEven(x: Int) = x % 2 == 0
    val nums = arrayListOf(10, 11, 12, 13, 14)
    println(nums.filter(::isEven))

    println(::num.get())
    println(::num.name)
}
val num = 99
```
## Memory management
### How is it handled?
#### Java
In java, all objects reside in an area, or space, called the heap. The Java Virtual Machine creates this at startup and can dynamically increase or decrease it as needed. 
The heap is sometimes divided into two spaces, the nursery and the old space. The nursery holds new objects, the old space older ones.
#### Kotlin
Kotlin makes use of the JVM, same as Java does, using the heap and garbage collecting. 
	

### How does it work?
#### Java
During object creation, java decides if an object is small or large. What exactly is considered a large object varies, but it is usually between 2 and 128kb
#### Kotlin
Kotlin creates and stores its objects similarly to java as they both run on the JVM
### Garbage collection?
#### Java
Java has, and is often quite known for, its garbage collection. When the heap becomes full the garbage collector kicks in and attempts to clear out objects that are no longer being used, in order to free up space for more. 
When the heap is divided into nursery and old space, they have separate amounts of storage. When the nursery fills up, a special garbage collector called the young collection activates and promotes any objects in the nursery that have lived long enough to the old space. Once the old space is full, a garbage collector called old collection frees up space. 
This is very useful as many objects are short lived and keeping them in the nursery allows for them to be freed faster, as well as easier to find when needed. 
#### Kotlin
Kotlin is run on the JVM and will be identical to Java, depending on the settings of your JVM runtime. 
### Automatic reference counting?
#### Java
Java does not have Automatic reference counting, instead making use of the nursery and old space as described above. 
#### Kotlin
Kotlin/Native makes use of automatic reference counting as well as a cycle counter when used without a VM, but regular Kotlin does not, as it is Java based
## Comparisons of references and values
### How are values compared? (i.e. comparing two strings)
#### Java
You can compare values in two different ways, the value, or the memory address. 
Java compares these with the “==” operator and “.equals()” method.

	== is used for reference comparison, or address comparison
	.equals() is used for content comparison.
#### Kotlin
Kotlin uses == and equals() interchangeably to compare values or structural equality 
Kotlin uses === for referential equality, to compare if two objects have the same memory address or not. 
	
## Null/nil references
### Which does the language use? (null/nil/etc)
Both Kotlin and Java use “null” to indicate null/nil. 

### Does the language have features for handling null/nil references?
#### Java
Java handles Null poorly, the null pointer exception is the bane of many programmer’s existence. Java 8 introduces an optional feature to java in the form of the class java.util.Optional, which helps to solve some of those issues. Optionals may or may not have a return type, which prevents them from having null pointer issues. 
#### Kotlin
Kotlin takes great steps to avoid issues with null pointer exceptions, to the point where there are only a few things that cause them in the language.
	* Explicitly calling them via throw NullPointerException()
	* The !! or “not null assertion operator”
	* Java interoperation, or times when Java messes with Kotlin via external code or other trickery.  
## Errors and exception handling
#### Java
Java handles exceptions and errors through “try catch” blocks

    try {
    
    } catch (try {   ExceptionType name) {
    
    } catch (ExceptionType name) {
    
    }
(code example from https://goo.gl/gMHMBr)

Each catch block is an exception handler that is handled based on its ExceptionType argument. The Catch block contains code that implements if the exception is called. 

#### Kotlin
Kotlin makes use of an almost identical process to java for exception and error handling, with some minor syntax changes. 

    try {
        // some code
    }
    catch (e: SomeException) {
        // handler
    }
    finally {
        // optional finally block
    } 
(code example from https://goo.gl/Ei6C4f)

## Lambda expressions, closures, or functions as types
#### Java
Java 8 allows for Lambda expressions allow you to treat functionality as method argument, or code as data. A Lambda function can be created without belonging to any class. 
Java uses these lambda expressions instead of closures, as they are similar.

This is the general syntax that Lambda's follows

	(argument-list) -> {body}

In practice, this can turn a function like this 

	interface Drawable{  
		public void draw();  
	}  
	public class LambdaExpressionExample {  
		public static void main(String[] args) {  
			int width=10;  

			//without lambda, Drawable implementation using anonymous class  
			Drawable d=new Drawable(){  
				public void draw(){System.out.println("Drawing "+width);}  
			};  
			d.draw();  
		}  
	}  

Into something like this

	interface Sayable{  
		public String say();  
	}  
	public class LambdaExpressionExample3{  
	public static void main(String[] args) {  
		Sayable s=()->{  
			return "I have nothing to say.";  
		};  
		System.out.println(s.say());  
	}  
	}  

(Code examples from https://goo.gl/b7tGv7)

#### Kotlin
Kotlin as well, allows for Lambda expressions in the same way java does, with one addition. Kotlin can take a Lambda expression and a Inline function together and performant custom control structures


[comment]: # (Jordan)

## Implementation of listeners and event handlers
A basic implementation of a handler (onClick function) and a listener (onClickListener) in Kotlin is much shorter than in Java as shown below.

#### Java
```java

public interface OnClickListener{
  void onClick(View v);
}

button.setOnClickListener(new OnClickListener(){
  @Override
  public void onClick(View v){
    doSomething();
  }
});
```
#### Kotlin
```kotlin
button.setOnClickListener(object : OnClickListener{
  override fun onClick(view: View){
    doSomething()
  }
})
```
Notice that in Kotlin it is very similar to Java, we create an object of interface OnClickListener and define a method that overrides onClick. However in Kotlin it can be even less code if we choose to use Kotlin's ability to substitute a function that recieves an interface with a lambda
#### Kotlin with lambda

```kotlin
fun setOnClickListener(listener: (View) -> Unit)

button.setOnClickListener({ view -> doSomething() })
```
[Reference]: # (https://medium.com/@dbottillo/kotlin-by-examples-methods-and-lambdas-25aef7544365)

## Singleton  
In Kotlin, singletons are used as a replacement for static members and fields, as they do not exist in Kotlin. A singleton is created by declaring an object. An object doesn't have any constructor like a class does but has an init block that allows initialization of code if needed.
  #### Kotlin
``` kotlin
object SomeSingleton {
    init {
        println("init complete")
    }
}
```
The object will be instantiated and its init blocks will be executed lazily upon first access, in a thread-safe way. Kotlin objects actually rely on a Java static initialization block. The above Kotlin object will be compiled to the following equivalent Java code:
#### Java
``` java
public final class SomeSingleton {
   public static final SomeSingleton INSTANCE;

   private SomeSingleton() {
      INSTANCE = (SomeSingleton)this;
      System.out.println("init complete");
   }

   static {
      new SomeSingleton();
   }
}
```
This is thread-safe, and allows lazy initialization. By simply using an object declaration in Kotlin, you are guaranteed to get a safe and efficient singleton implementation.
## Procedural programming
  Kotlin supports procedural programming. In Kotlin you may start coding a function without encapsulating it, which Java does not allow. The following is the classic "hello world" program first in a Java class and then In Kotlin using procedural programming.
  #### Java

  ```java
  public class HelloWorld {

    public static void main(String[] args) {
        System.out.println("Hello, World");
    }

}
```
  
#### Kotlin

  ```kotlin
  fun main(args : Array<String>) {
    println("Hello, world!")
}
```
  
## Functional programming
Kotlin allows for Functional Programming. Whereas in Java even after the introduction of lambdas, the Java language remains an imperative one. It doesn't allow you to write code as pure functions, has statements changing the state of the program used more than expressions independent of state, and favors mutability over immutability. In Java the word Final is used to make an object immutable. This takes much longer to write than its equivalent in Kotlin, val instead of var which would declare a variable. 
#### Java
``` Java
Final String person = "John";
```
#### Kotlin
``` Kotlin
val person = "John"
```
Below is a simple example of the use of expressions vs statements in the two languages.
#### Java

``` Java
String name = "Anonymous";
if(person.name){
name = person.name;
}
```
The above Java code is written as an expression followed by another statement inside of an if statement. In Kotlin we could write this code in a Functional style with one expression.
#### Kotlin

``` Kotlin
val name = if(person.name){
person.name}
else "Anonymous"
```
The above Kotlin code accomplishes the same thing but in the Functional paradigm by favoring expressions over statements.
## Multithreading
In Java you can achieve multithreading by Implementing the Runnable interface or by extending the Thread class.
#### Java
``` java
// Threading by implementing Runnable interface
class OurThread implements Runnable{  
	public void run(){  
		System.out.println("thread is running...");  
	}  
	public static void main(String args[]){  
		OurThread m1=new OurThread();  
		Thread t1 =new Thread(m1);  
		t1.start(); 
    }
}
// Threading by extending the Thread class
class OurExtendedThread extends Thread{  
	public void run(){  
		System.out.println("thread is running...");  
	}  
	public static void main(String args[]){  
		OurExtendedThread t1=new OurExtendedThread();  
		t1.start();  
 	}  
} 
```
#### Kotlin
In Kotlin multithreading is achieved in a similar way to Java, because you can use Java classes in Kotlin. everything you need to know about the standard library function thread in kotlin is here.
``` kotlin
fun thread(
    start: Boolean = true, 
    isDaemon: Boolean = false, 
    contextClassLoader: ClassLoader? = null, 
    name: String? = null, 
    priority: Int = -1, 
    block: () -> Unit
): Thread (source)
```
and an example of its use follows
``` kotlin
// Threading by extending the Thread class
object : Thread() {  
    override fun run() {
       println("test")
    }
}.start()
//Threading by implementing the Runnable interface

Thread(Runnable {
    Thread.sleep(1000)
    println("test")
})

```
