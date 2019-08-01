# Essential Java

Fundamental concepts (mostly Java-specific). We recommend learning / understanding all of these concepts before going through any of the **[Spring Boot](spring.md)** content.

If you're still new to development and need to learn core foundations / basic concepts, we recommend you go through the **[Java Tech College Handbook](https://github.com/excellaco/java-tech-college-handbook)**.

## Basic OOP

### Classes in Java

```java
// this is a basic java class
public class Employee {

}
```

A **class** is a user defined blueprint or prototype from which objects are created.  It represents the set of properties or methods that are common to all objects of one type. 

In general, class declarations can include these components, in order:

* **Modifiers** : A class can be public or has default access (see [Scope](#scope)).
* **Class name**: The name should begin with a initial letter (capitalized by convention).
* **Superclass**(if any): The name of the class’s parent (superclass), if any, preceded by the keyword `extends`. A class can only extend (subclass) one parent.
* **Interfaces**(if any): A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword `implements`. A class can implement more than one interface.
* **Body**: The class body surrounded by braces, { }.


```java
public class Employee extends Person implements Serializable {
  //everything inside the braces is part of the class body
}
```
In the example above, <br/>
Modifier: *public*<br/>Class Name: *Employee*<br/>Superclass: *Person*<br/>Interface: *Serializable*

**Learn more:**

* **[Classes and Objects in Java (GeeksForGeeks.org)](https://www.geeksforgeeks.org/classes-objects-java/)**
* **[Java Classes and Objects (W3Schools)](https://www.w3schools.com/java/java_classes.asp)**

**Deeper Dive:**

* Attributes: **[Java Class Attributes (W3Schools)](https://www.w3schools.com/java/java_class_attributes.asp)**
* Methods: **[Java Class Attributes (W3Schools)](https://www.w3schools.com/java/java_class_methods.asp)**
* Constructors: **[Java Constructors (W3Schools)](https://www.w3schools.com/java/java_constructors.asp)**


### Scope

You can define and restrict the scope of a class, constructor, variable, or method with an *access modifier*. There are four access modifiers in Java:

* public
* private
* protected
* default (no modifier included)

**Learn more:**

* **[Access Modifiers in Java](https://www.geeksforgeeks.org/access-modifiers-java/)**
* **[Java Modifiers (W3Schools)](https://www.w3schools.com/java/java_modifiers.asp)**

### Main OOP Concepts in Java

```java
// ENCAPSULATION
public class Employee extends Person {
  private String name;
  
  public String getName() {
  	return this.name;
  }
  
  public void setName(String name) {
  	this.name = name;
  }
}
```
**[Encapsulation](https://www.w3schools.com/java/java_encapsulation.asp)**: The practice of keeping fields within a class private, then providing access to them via public methods. It’s a protective barrier that keeps the data and code safe within the class itself. This way, we can re-use objects like code components or variables without allowing open access to the data system-wide.

```java
// INHERITANCE
public class Person {
	private String name;
	
	public String getName() {
  	return this.name;
  }
  
  public void setName(String name) {
  	this.name = name;
  }
}
public class Employee extends Person {
  private String title;
  
  public String getFullNameAndTitle() {
  // name is defined in parent class
  	return this.getName() + " " + this.title; 
  }
}
```
**[Inheritance](https://www.w3schools.com/java/java_inheritance.asp)**: Creating new classes that share some of the attributes of existing classes. This lets us build on previous work without reinventing the wheel.

```java
// COMPOSITION
public class Job { 
  private String role; 
  private long salary; 
  private int id; 

  public String getRole() { 
    return role; 
  }

  public void setRole(String role) { 
    this.role = role; 
  }

  public long getSalary() { 
    return salary; 
  }

  public void setSalary(long salary) { 
    this.salary = salary; 
  }

  public int getId() { 
    return id; 
  }

  public void setId(int id) { 
    this.id = id; 
  }
} 

public class Person { 
  // composition: has-a relationship 
  private Job job; 

  public Person(){ 
    this.job = new Job(); 
    job.setSalary(1000L); 
  }

  public long getSalary() { 
    return job.getSalary(); 
  } 
}
```
**[Composition](https://www.javatpoint.com/q/5101/what-is-composition-in-java?)**: Composition is the design technique to implement has-a relationship in classes. We can use java inheritance or Object composition for code reuse. 

```java
// POLYMORPHISM
public class Employee extends Person {
  public Device[] getDevices() {
    // get all devices owned by employee
  }
  
  public Device[] getDevices(String type) {
    // get all devices given a type.
    // e.g. get all tablets owned by this employee 
  }
}
```
**[Polymorphism](https://www.w3schools.com/java/java_polymorphism.asp)**: The practice of using the same word to mean different things in different contexts. One form of polymorphism in Java is method overloading. That’s when different meanings are implied by the code itself. The other form is method overriding. That’s when the different meanings are implied by the values of the supplied variables.

```java
// ABSTRACTION
public abstract class Person {
	// no implementation defined.
	// subclass MUST implement this method.
	public abstract void walk();
}
public class Employee extends Person {
	public void walk() {
	  // implementation of walk goes here.
	}
}
```

**[Abstraction](https://www.w3schools.com/java/java_abstract.asp)**: Using simple things to represent complexity. We all know how to turn the TV on, but we don’t need to know how it works in order to enjoy it. In Java, abstraction means simple things like objects, classes, and variables represent more complex underlying code and data. This is important because it lets avoid repeating the same work multiple times.

**Learn more: [OOP Concepts in Java](https://stackify.com/oops-concepts-in-java/)**


## Collections

A collection, as name implies, is group of objects. Java Collections framework is consist of the interfaces and classes which helps in working with different types of collections such as lists, sets, maps, stacks and queues etc.

![Collections Hierarchy](https://cdn2.howtodoinjava.com/wp-content/uploads/2018/11/Java-collections-interfaces.gif)

**Learn more: [Collections in Java](https://howtodoinjava.com/java-collections/)**

**Also see: [Data Structures](https://www.geeksforgeeks.org/data-structures/)**

## Generics

Java generics enable types (classes and interfaces) to be parameters when defining classes, interfaces and methods. Type parameters provide a way for you to re-use the same code with different inputs.

Collections are a great example of generics used in every day code.

```java
List list1 = new ArrayList(); // no type parameter
list1.add("abc");
String s1 = (String)list1.get(0); // cast required since type is not implied

List<String> list2 = new ArrayList<>(); // type parameter included
list2.add("abc");
String s2 = list2.get(0); // no need for a cast
```

Why use Generics?

* **Has stronger type checks at compile time.** A Java compiler applies strong type checking to generic code and issues errors if the code violates type safety. Fixing compile-time errors is easier than fixing runtime errors, which can be difficult to find.
* **Eliminates the need to cast.** Without generics, if you wanted to get the first element from an ArrayList of Strings, you would have to cast it.
* **Enables programmers to implement generic algorithms.** By using generics, programmers can implement generic algorithms that work on collections of different types, can be customized, and are type safe and easier to read.

**Learn more:**

* **[Generics in Java (GeeksForGeeks.org)](https://www.geeksforgeeks.org/generics-in-java/)**
* **[The Basics of Java Generics (Baeldung)](https://www.baeldung.com/java-generics)**
* **[Java Generics (TutorialsPoint)](https://www.tutorialspoint.com/java/java_generics)**

## Additional Resources

* **[Effective Java, 2nd Edition](https://www.oreilly.com/library/view/effective-java-2nd/9780137150021/)** is a cornerstone book on the *right way* to write Java.

