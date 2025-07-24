# Spring Boot tutorial

1. this is a java framework to run java applications .
2. main use: it simplifies configuration and setup process.
3. `Spring boot is a module of the Spring framework' .
4. Spring framework --> then SpringBoot.

# Spring : lightweight , open source, also called a framework of frameworks.

1. Spring Framework

“A comprehensive and versatile platform for enterprise Java development.”

    •	Think of it as the skeleton or foundation for building Java apps.
    •	It provides all the tools and features to build large-scale, high-performance apps.
    •	It’s modular—you use only what you need (like plug-and-play 🔌).

🧠 Example: Need to connect to a database? Use Spring Data. Want to build APIs? Use Spring MVC. You’re in control.

# Spring Basics.

## Keywords

- Spring Java framework for building apps
- IoC Framework manages object creation
- DI Inject dependencies instead of manually creating them
- Spring MVC Build APIs / web apps
- Spring Boot Spring but easier, faster
- Spring Security Protect routes and handle login
- Spring Data Easy database operations
- Spring Cloud Tools for microservices
- Microservices Small, independent services working together

## features.

1. Full scale application development
2. it has features like
3. Inversion of control: framework controls the flow , `we don't need to create and manage objects`.
4. Dependency Injection : `this injects the dependencies our class needs `
5. Spring MVC : `“Model-View-Controller for building web applications.”` > for web development.
6. spring security : auth and autorization
7. spring data , spring cloud for microservices

## Why to use Spring?

- When it comes to size and transparency, Spring is a featherweight. Spring framework's basic version is about 2MB in size. The Spring Framework's core capabilities can be used to create any Java program

## what are modules in spring :

1. think of them as a subprojects or toolkits inside the spring framework.
2. each part in spring contains it's own modules inbuilt .
3. each solves a specific problems.

## applications

- pojo based : plain old java object
- POJO = Plain Old Java Object : a java class with private variables and public getters , setters .

1. why is this used ?
1. Spring is designed to be non-invasive, meaning it lets you write normal Java classes (POJOs) and still manage them through features like:
   • Dependency Injection (DI)
   • AOP (Aspect-Oriented Programming)
   • ORM (with JPA/Hibernate)
   \*\* So instead of forcing you to extend framework-specific classes like in other frameworks…

🔁 Spring lets you build apps using POJOs that you annotate, and Spring wires them up behind the scenes. \*\*

---

2. Modular : modular approach .
3. integration with the existing framework: use of existing frameworks to use .
4. Testability : Because Spring manages all the setup, and your logic lives in clean little Java classes (POJOs), you can test easily without worrying about real databases, APIs, or other junk.
