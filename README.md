# Object Oriented Final Group Project, Comparing Java and Kotlin

### Written BY:
Jordan Liebman
(everyone don't forget to put your names)

# Comparison Criteria
* Language purpose/genesis
  * Why was the language created?
  * What problems was the language trying to address?
  * Is the language a reaction to a previous language or a replacement for another language?
* Unique features of the language
  * Does the language have any particularly unique features?
* Name spaces
  * How are name spaces implemented?
  * How are name spaces used?
* Types
  * What types does the language support?
  * Are both reference and value types supported?
  * Can new value types be created?
* Classes
  * Defining
  * Creating new instances
  * Constructing/initializing
  * Destructing/de-initializing
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
* Inheritance / extension
* Reflection
  * What reflection abilities are supported?
  * How is reflection used?
* Memory management
  * How is it handled?
  * How does it work?
  * Garbage collection?
  * Automatic reference counting?
* Comparisons of references and values
  * How are values compared? (i.e. comparing two strings)
* Null/nil references
  * Which does the language use? (null/nil/etc)
  * Does the language have features for handling null/nil references?
* Errors and exception handling
* Lambda expressions, closures, or functions as types

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
  * How is a singleton implemented?
  * Can it be made thread-safe?
  * Can the singleton instance be lazily instantiated?
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
Kotlin also supports functional programming.
## Multithreading
  * Threads or thread-like abilities
  * How is multitasking accomplished?
