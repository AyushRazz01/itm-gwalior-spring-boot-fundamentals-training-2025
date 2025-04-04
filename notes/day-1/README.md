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

### Inheritance and polymorphism in practice

### Interfaces and abstract classes

### Annotations in Java (built-in annotations and their purpose)

### Lambda expression and Functional Interfaces

### Stream API basics

### Optional class for null handling

### Method reference

### Spring Core concepts

### Dependency Injection (DI) and Inversion of Control (IoC)

### Spring vs Spring Boot

### Spring Boot advantages and features