# Spring Boot

This section will help you understand all the core pieces of a Spring Boot application. We recommend going through / understanding **[Essential Java](java.md)** concepts before learning the following topics.

### What is Spring Boot?

Spring Boot is a Java-based framework used to create a microservice. It is considered to be the de-facto standard for building Java-based web services.

**Learn more:**

* **[Spring Boot Introduction](https://www.tutorialspoint.com/spring_boot/spring_boot_introduction)**
* **[Spring Boot Quick Start](https://www.tutorialspoint.com/spring_boot/spring_boot_quick_start.htm)**

### Gradle

Gradle is a [Groovy](https://groovy-lang.org)-based build management system designed specifically for building Java-based projects. It is typically used for managing dependencies and creating tasks. (for JavaScript devs, Gradle is equivalent to npm in most regards).

**Learn more:**

* **[Introduction to Gradle](https://www.baeldung.com/gradle)**
* **[Building Spring Boot 2 Applications with Gradle](https://guides.gradle.org/building-spring-boot-2-projects-with-gradle/)**
* **[Gradle Build Tool for Beginners](https://www.udemy.com/gradle-build-tool-learn-from-scratch/)** (Paid Udemy Course)

### Beans

A bean is an object that is instantiated, assembled, and managed by Spring. 

Beans are defined using one of the `@Component` annotations on a class. These include `@Controller`, `@Service`, and `@Repository`. Beans can be also be defined at a method level by adding `@Bean` on a method in a class with an `@Configuration` annotation.

When Spring starts, it runs a [component scan](https://www.baeldung.com/spring-component-scanning), creating instances of each component. When you define a dependency in one of your files, Spring will inject the "running instance" of a bean into the class.

**Learn more:**

* **[What is a Spring Bean](https://www.baeldung.com/spring-bean)**
* **[Spring Component Scanning](https://www.baeldung.com/spring-component-scanning)**
* **[A quick intro to Dependency Injection](https://www.freecodecamp.org/news/a-quick-intro-to-dependency-injection-what-it-is-and-when-to-use-it-7578c84fa88f/)**

### Code Structure

Because of [component scanning](https://www.baeldung.com/spring-component-scanning), your application will still run no matter how you structure your code. There are many ways to structure your code and the link below is a great example of how a Spring Boot project should be structured.

See: **[Projects Structure and Best Practices](https://medium.com/the-resonant-web/spring-boot-2-0-project-structure-and-best-practices-part-2-7137bdcba7d3)**


### Bean Validation 

*Bean Validation is not a Spring-specific concept, but it is much easier to understand from the scope of a Spring Boot application.*

See: **[Validation in Spring Boot](https://www.baeldung.com/spring-boot-bean-validation)**

### Serialization

See: **[Introduction to Java Serialization](https://www.baeldung.com/java-serialization)**

### Unit Testing

The primary testing framework for a Spring Boot application is JUnit.

See: **[Testing in Spring Boot (JUnit)](https://www.baeldung.com/spring-boot-testing)**

### Migrations

Database migrations allow developers to continuously remodel database schemas. A change in a table, column, etc of a database can be managed by version control. If any changes in a migration break your application, it is very easy to rollback to the previous version.

There are two main libraries that most developers use to create and run migrations: **Flyway** and **Liquibase**.

**[Database Migrations with Flyway](https://www.baeldung.com/database-migrations-with-flyway)**

**[Use Liquibase to Safely Evolve Your Database Schema](https://www.baeldung.com/liquibase-refactor-schema-of-java-app)**

### Additional Resources

* **[Spring Framework Master Class](https://www.udemy.com/spring-tutorial-for-beginners/)** (covers Spring Boot, Spring JDBC, Spring AOP, Hibernate, JUnit, and Mockito)