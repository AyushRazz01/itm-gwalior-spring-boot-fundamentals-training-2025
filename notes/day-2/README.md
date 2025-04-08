# Spring Boot Fundamentals Training - ITM Gwalior

## **Duration**: 4 hours per day x 6 days (24 hours total)

### Day 2 : Spring Boot Fundamentals

#### Session 1 (2 hours) : Project setup, application properties, auto-configuration

* **Spring Boot Project Setup** (60 minutes)
	* [Spring Initializr (start.spring.io)](./README.md#spring-initializer-startspringio)
	* [Maven project structure](./README.md#maven-project-structure)
	* [POM configuration and dependencies](./README.md#pom-configuration-and-dependencies)
	* [application.properties/YAML configuration](./README.md#applicationpropertiesyaml-configuration)


* **Spring Boot Core Concepts** (60 mintues)
	* [@SpringBootApplication anatomy](./README.md#springbootapplication-anatomy)
	* [Component scanning](./README.md#component-scanning)
	* [Auto-configuration](./README.md#auto-configuration)
	* [Profiles for environment specific configuration](./README.md#profiles-for-environment-specific-configuration)

#### Session 2 (2 hours) : Dependency Injection, component scanning, bean lifecycle

* **Dependency Injection in Spring Boot** (90 minutes)
	* [Bean lifecycle](./README.md#bean-lifecycle)
	* [@Component, @Service, @Repository annotations](./README.md#component-service-repository-annotations)
	* [@Autowired and constructor injection](./README.md#autowired-and-constructor-injection)
	* [Scopes of Spring beans (Singleton vs Prototype)](./README.md#scopes-of-spring-beans-singleton-vs-prototype)
	* [Building a simple service layer](./README.md#building-a-simple-service-layer)


* [**Practical Exercise**](./README.md#practical-exercise) (30 minutes)
	* Create a Spring Boot application with multiple components
	* Configure beans with different injection methods
	* Test bean initialization and dependency injection


---

### Spring Initializer (start.spring.io)

[**Developing your First Spring Boot Application** (Spring Docs)](https://docs.spring.io/spring-boot/tutorial/first-application/index.html)

**Step 1: Install Java JDK (21 - LTS)**

If you have downloaded IntelliJ IDEA (Ultimate), it comes pre-installed with the latest version of the GA (Generally Available)
JDK, which right now is Java OpenJDK 24, but we need to install Java JDK 21 (LTS - Long Term Support). 

Press `ctrl + alt + shift + S` on Windows OR `cmd + ;` on a Mac to open the "Project Structure Window"

![img.png](assets/images/project-structure.png)

Make sure the **SDK:** is set to Java `21` (whichever flavor is available, OpenJDK/Amazon Coretto etc)

Make sure the **Language Level:** is set to `SDK default`.

click on `apply` and then click on `ok`.

### Maven project structure

### POM configuration and dependencies

### application.properties/YAML configuration

### @SpringBootApplication anatomy

### Component scanning

### Auto-configuration

### Profiles for environment specific configuration

### Bean lifecycle

### @Component, @Service, @Repository annotations

### @Autowired and constructor injection

### Scopes of Spring beans (Singleton vs Prototype)

### Building a simple service layer

---

## Practical Exercise