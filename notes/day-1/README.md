# Spring Boot Fundamentals Training - ITM Gwalior

## **Duration**: 4 hours per day x 6 days (24 hours total)

### Day 1 : Introduction & Java Refresher

#### Session 1 (2 hours) : Welcome, environment setup, OOP concepts review

* **Welcome & Overview** (30 minutes)
  * Training objectives and schedule  

    > By the end of this training program, _YOU_ will be able to:
    > * Understand core Spring Boot concepts and its advantages over traditional Spring framework.
    > * Design and implement RESTful APIs following industry best practices.
    > * Work with data persistence using Spring Data JPA and Hibernate.
    > * Implement proper exception handling and API documentation.
    > * Apply the MVC architectural pattern in Spring Boot applications.
    > * Develop and test a complete Spring Boot application from scratch.

  * Pre-requisite knowledge assessment
  * Setting up the development environment (JDK, IntelliJ IDEA, Git)


* **Java Refresher: OOP Concepts** (90 minutes)
  * [Classes and Objects review](./README.md#classes-and-objects-review)
  * [Inheritance and polymorphism in practice](./README.md#inheritance-and-polymorphism-in-practice)
  * [Interfaces and abstract classes](./README.md#interfaces-and-abstract-classes)
  * [Annotations in Java (built-in annotations and their purpose)](./README.md#annotations-in-java-built-in-annotations-and-their-purpose)

#### Session 2 (2 hours) : Modern Java features, Introduction to Spring Framework

* **Java Refresher: Modern Java Features** (60 minutes)
    * [Lambda expressions and Functional Interfaces](./README.md#lambda-expression-and-functional-interfaces)
    * [Stream API basics](./README.md#stream-api-basics)
    * [Optional class for null handling](./README.md#optional-class-for-null-handling)
    * [Method references](./README.md#method-reference)


* **Introduction to Spring Framework** (60 minutes)
    * [Spring Core concepts](./README.md#spring-core-concepts)
    * [Dependency Injection and Inversion of Control](./README.md#dependency-injection-di-and-inversion-of-control-ioc)
    * [Spring vs Spring Boot](./README.md#spring-vs-spring-boot)
    * [Spring Boot advantages and features](./README.md#spring-boot-advantages-and-features)


---

### Classes and Objects review

**What is a class?**

A class describes an object in terms of its
  - data (variables/fields)
  - operations (functions/methods)

Any concept you wish to implement in a Java program must be _encapsulated_ within a class!

A student class example

```java
public class Student {
	int rollNumber;
	String name;
	double marks;
	
	// ...
}
```
In this `Student` class there are 3 fields (data points)
- roll number of the student called `rollNumber`, which is of the `int` (integer) type.
- name of the student called `name`, which is of the `String` type.
- marks of the student called `marks`, which is of the `double` type.

This means, we are telling out Java program about a new object type - `Student`, and
we are saying every student should have a 
- roll number,
- name,
- and marks.

**POJO: Plain-Old Java Object**

A complete POJO implementation of the same Student class would look like this

```java
import java.util.Objects;

public class Student {
	private final int rollNumber;
	private final String name;
	private double marks;

	public Student() {
		this.rollNumber = 0;
		this.name = "";
	}

	public Student(int rollNumber, String name, double marks) {
		this.rollNumber = rollNumber;
		this.name = name;
		this.marks = marks;
	}

	public int getRollNumber() {
		return rollNumber;
	}

	public String getName() {
		return name;
	}

	public double getMarks() {
		return marks;
	}

	public void setMarks(double marks) {
		this.marks = marks;
	}

	@Override
	public boolean equals(Object o) {
		if (o == null || getClass() != o.getClass()) return false;

		Student student = (Student) o;
		return rollNumber == student.rollNumber 
				&& Double.compare(marks, student.marks) == 0 
				&& Objects.equals(name, student.name);
	}

	@Override
	public int hashCode() {
		int result = rollNumber;
		result = 31 * result + Objects.hashCode(name);
		result = 31 * result + Double.hashCode(marks);
		return result;
	}

	@Override
	public String toString() {
		return "Student{" +
				"rollNumber=" + rollNumber +
				", name='" + name + '\'' +
				", marks=" + marks +
				'}';
	}
}
```

Don't be afraid of the code. This is simply the same class we have seen earlier with some extra instructions
for the Java program. This complete "POJO" (Plain-Old Java Object) implementation can be created for any class!
The general requirements to create a POJO class are
1. The class should be public.
2. The fields should be private.
3. There should be a no-args constructor in the class.
4. There should be public getter and setter methods.
5. **There should be NO business logic in the class.**
6. **Optional:** Parameterized Constructor.
7. **Optional:** Override the `toString()` method.
8. **Optional:** Override the `equals()` and the `hashCode()` methods.

**What is an object?**

An _object_ in Java is a real-world entity, created from a class, that exists in memory when the Java program is running!

For example, before creating an actual house, an architect designs the house on a blueprint. IN this scenario, the blueprint
is the _class_ and the actual house is the _object_.

Code Example - 

```java
public class Main {
    public static void main(String[] args) {
        Student chatur = new Student();
    }
}
```

In this example, we have created a new `Student` object, and we are referring to the object with the name `chatur`.

After the creation of the object is completed successfully, you can read and write the values of the data fields of the object
i.e. `rollNumber`, `name`, and `marks` as defined in the `Student` class. 

Also, you can _make_ the `chatur` object do something by calling the `Student` methods defined in the class.

### Inheritance and polymorphism in practice

**Inheritance**

**Polymorphism**

### Interfaces and abstract classes

**Abstract Class**

**Interface**

### Annotations in Java (built-in annotations and their purpose)

**@Override**

### Lambda expression and Functional Interfaces

**Functional Interfaces**

**Lambda Expressions**

### Stream API basics

### Optional class for null handling

### Method reference

### Spring Core concepts

### Dependency Injection (DI) and Inversion of Control (IoC)

### Spring vs Spring Boot

### Spring Boot advantages and features

---

## Practice Exercises

1. Create an `abstract` superclass named `Fruit`, and a concrete subclass named `Apple`. The superclass (`Fruit`) should 
belong to a package called `food` and the subclass (`Apple`) can belong to the default package. Make the superclass `public`
and give the subclass **default** access.
   - Create the superclass as follows
   ```java
        package food;
     
        public abstract class Fruit {
            // data 
            // operations
            // write the complete POJO implementation
        }
     ```
   - Create the subclass as follows
   ```java
        import food.Fruit;
        class Apple extends Fruit {
            // data
            // operations
            // write the complete POJO implementation
        }  
   ```
   - Create a `Main` class, and create the `main()` method inside it. Create objects of both the classes.  

2. You are given an interface as follows
   ```java
        public interface Vehicle {
            public int getYear();
            public String getModelName;
            public String getCompanyName;
        }    
   ```
   Write a class called `Ferrari` that implement the interface. Write the complete POJO implementation for the `Ferrari`
   class. Create a `Main` class, and create the `main()` method inside it. Create object of the `Ferrari` class inside it.

3. Create a class called `Bird` and define an instance method called `fly()` inside it. Define some instance fields for the `Bird`
class such as `name`, `height`, `weight` etc. Define a _static_ field for the `Bird` class called `birdCount`. 
Create a `Main` class, and create the `main()` method inside it. Create a static variable inside the `main()` method of the `Bird` type.
Initialize the variable with a valid `Bird` object and print the values of the instance and _static_ fields. Write some logic
in the `Bird` class to increment the `birdCount` variable every time a new `Bird` class object is created. Create an array of `Bird`s (`Bird[]`)
4. Try the Stream API practice questions given [here](https://github.com/dbc2201/StreamPracticeQuestions)
5. Write a program that counts duplicate characters from a given string.
    ```java
    /**
     * Counts duplicate characters in a given string and returns only those 
     * that appear more than the specified threshold.
     *
     * @param input the string to analyze for duplicate characters
     * @param threshold minimum number of occurrences to be considered duplicate
     * @return a Map with each duplicate character as key and its count as value
     * @throws NullPointerException if the input string is null
     * @throws IllegalArgumentException if threshold is less than 1
     */
    public Map<Character, Integer> countDuplicateCharacters(String input, int threshold) 
            throws NullPointerException, IllegalArgumentException {
        // TODO: Implement the duplicate counting logic
        return new HashMap<>(); // Placeholder return
    }
    ```
6. Write a program that reverses the letters of a word.
    ```java
    /**
     * Reverses the letters of each word in the input text while preserving word order.
     * For example: "Hello World" becomes "olleH dlroW"
     *
     * @param text The input text to process
     * @return A new string with each word's letters reversed
     * @throws IllegalArgumentException if the input text is null or empty
     */
    public String reverseLettersInWords(String text) throws IllegalArgumentException {
        // TODO: Implement the letter reversal logic
        return null;
    }
    ```
7. Write a program that counts the occurrences of a certain character in a given string.
    ```java
    /**
     * Counts the number of occurrences of a specific character in the given string.
     *
     * @param inputString the string to search in
     * @param targetChar the character to search for
     * @return the number of occurrences of the target character in the input string
     * @throws NullPointerException if the input string is null
     */
    public static int countCharacterOccurrences(String inputString, char targetChar) throws NullPointerException {
        // TODO: Implement the character counting logic
        return 0;
    }
    ```
8. Write a program that removes all white spaces from the given string.
    ```java
    /**
     * Removes all white spaces from the input string.
     * 
     * @param input the string from which to remove white spaces
     * @return a new string with all white spaces removed
     * @throws NullPointerException if the input string is null
     */
    public static String removeWhiteSpaces(String input) throws NullPointerException {
        // TODO: Implement the white space removing logic
        return null;
    }
    ```
--- 
##### Special Problem Statement
Design a robust product classification hierarchy for an inventory system where:

Products must be classified as exactly one of the following: Electronics, Clothing, or Food.
Each main category must restrict which specific product types can extend/implement it:

Electronics should only allow Smartphone, Laptop, and SmartWatch implementations
Clothing should only allow TShirt, Jeans, and Jacket implementations
Food should only allow Fruit, Vegetable, and PreparedMeal implementations


It should be impossible for developers to create new product types outside these predefined categories.
The system must enforce strong compile-time type checking to prevent unauthorized extensions of the hierarchy.

Requirements

Create a type hierarchy that enforces these strict classification rules
Implement the required classes/interfaces with appropriate attributes
Demonstrate your solution with a test program that:

Creates instances of valid product types
Shows how the system prevents creation of invalid product types
Processes different products appropriately based on their classification.