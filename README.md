# FinalGroupProject
* Pick two object-oriented languages.
* Form a team to work on the comparison.
  * You can be a team of 1.
  * Teams greater than 4 are usually not a good idea.
* Using the comparison criteria provided, compare the two languages
* through documentation and code examples.
* The documentation is to be written in markdown.
* The documentation and code examples are to be in a
* GitHub public repository that the team uses.
* The home page is to be the README.md for the repository.
* Other mark down pages can be linked using relative links in markdown files.
  * Relative links in markdown files (Links to an external site.)Links to an external site..
* The README.md is to include near the top:
  * The two languages being compared.
  * The names of the members of the team.
* The URL for the GitHub repository for your team is to be submitted via an assignment on Canvas.
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
* Properties
  * Getters and setters…write your own or built in?
  * Backing variables?
  * Computed properties?
* Interfaces / protocols
  * What does the language support?
  * What abilities does it have?
  * How is it used?
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
