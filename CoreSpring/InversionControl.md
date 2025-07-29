# Spring core :

## Inversion Control : IoC stands for Inversion of Control : It's a container.

- this creates objects (beans) and configures them , injects dependencies and manages beans lifecycles.
- This uses `Dependency Injection` in order to manage application components.
- it retrieves object configuration from xml files , annotations or pojo's .
- Here spring IoC container can control the object lifecycle and dependency management.

## Spring IoC container :

- there are two types
  1. BeanFactory : basic version , support for DI , Bean LifeCycle Management.
  2. ApplicationContext : support for extra features like internilization and event progogation.

### Key Features of IoC Container

The key features of IoC Container are listed below

1. Dependency Injection: Automatically injects dependencies into our classes.
2. Lifecycle Management: Manages the lifecycle of beans, including instantiation, initialization, and deletion.
3. Configuration Flexibility: Supports both XML-based and annotation-based configurations.
4. Loose Coupling: Promotes loose coupling by decoupling the implementation of objects from their usage.

### bean defination : we going as a plain old xml based approach :

`In the beans.xml file, we have created beans. So inside the id, we have to pass the unique id and inside the class, we have to pass the Class name for which you want to create the bean. Later on, inside the main method, we can tweek it out that will be described in the upcoming program.`

- Bean Definition: In Spring, the objects that form the backbone of your application and that are managed by the Spring IoC container are called beans. A bean is an object that is instantiated, assembled, and otherwise managed by a Spring IoC container.

### approach i did a xml based approach and now i am doing a autoconfig approach in the modern spring.

- used `@configuration` class to define the beans, it's like <u style="color:red" >`treat this class like xml file but in java`. </u>
  <br>

### topics understood in lecture :

1.  Spring IOC
2.  IOC Container.
3.  Loose Coupling importance via Interface example.
4.  Creating Beans using traditional XML method using pom class and `ClassPathXmlApplicationContext()`.
5.  getting those from application context container using `applicationContext.getBean()`.
6.  USing java based configuration : via `AppConfig` , `@Bean`.
    1. In this we use `AnnotationConfigAppApplicationContext()` ,`context.getBean()`.

7.  annotations
8.  Learnt `@Configuration` , `@Bean` , `ComponentScan(basepackages=)`, `Component`, `Primary`, `Qualifier`,`explicit bean names`.
9.  how to resolve `NoUniqueBeanException`.
