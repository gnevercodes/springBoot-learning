# core concepts in spring.

## Dependency injection :

- dependency injection is a design pattern used in software development to implement inversion of control
- this allow's it's class to receive dependencies from another `source` rather than creating them with the `same class`.
- This reduces the main class dependencies with other classes.

### Types of dependency injection :

- Constructor injection : he dependent object is provided to the class via its constructor. The dependencies are passed when an instance of the class is created.
- setter injection : n setter injection, the dependent object is provided to the class via a setter method after the class is instantiated. This allows you to change the dependencies dynamically.
- field injection : spring directly injects you with a dependency into a class field using the annotation `@Autowired` right above the field. (not recommended, breaks encapsulation.)

## Inversion of Control:

- design principle used in the OOP

---

```java
public class car{ // ! without inversion control .
    private Engine engine;
    public car(){
        engine = new Engine() ; // * here we are directly controlling the creating of engine inside the car class : This is called as "tight Coupling" , car heavily depends on engine;

    }
    public void start(){
        engine.run():
    }
}
```

```java
public class Car { // ! loose coupling .
    @Autowired
    private Engine engine;

    public void start() {
        engine.run();
    }
}
```

---

- here spring does take care of :
- Now Spring is in control of:  
  • When and how Engine is created
  • Injecting Engine into Car

- 🎯 Why Is It Called “Inversion”?

Because control is inverted:
• Old Way → Your code controls object creation.
• IoC Way → Framework controls object creation, your code just gets the ready-to-use object.

### types of inversion control :

- What is an IOC container: it's like a factory or a warehouse.
- IOC container knows how to create and manage objects .
- handles their dependencies.
- gives us only when needed.

-- Spring , this ware house has two types :

- BeanFactory - minimal version
- ApplicationContext - pro level version.

### BeanFactory : A basic lightweight container that creates beans only when asked. `LazyLoading`.

```java
Resource resource = new ClassPathResource("beans.xml");
BeanFactory factory = new XmlBeanFactory(resource);

MyBean obj = (MyBean) factory.getBean("myBean");
```

🧠 Downside of BeanFactory:

It doesn’t give you:
• Event handling 📢  
• AOP support 🌀 (used for adding logging, security, etc.)  
• Internationalization 🌍  
• Or much flexibility for enterprise-level stuff

### applicationcontext:

ApplicationContext (the real MVP)

✅ What it is:
• A super-powered version of BeanFactory  
 • Eager loads beans → Creates them when the container starts, not when you ask  
 • Supports all the cool Spring features

💥 Extra Features:  
 • 🔁 Dependency Injection  
 • 🔊 Event handling (like listeners)  
 • 🌍 Internationalization  
 • 🧠 AOP (logging, transactions, etc.)  
 • 💾 Access to file resources  
 • 🧩 Integration with other frameworks (JPA, Hibernate, etc.)

---

# SpringAnnotation:

- annotations are metadata used by spring framework to define
  - configuration
  - dependencies.
  - behaviour  
    directly into our java code.
- some common types of annotations :
  1. @component : marks a class as a spring bean , allws spring to easily detect and manage it during class scan.
  2. @autowired: automatically injects dependencies into class , used on fields , constructors, methods.
  3. @Bean : define a spring bean explicitly.
  4. @Configuration: indicates that a class contains bean definitions and acts as a source

# Spring Annotations Cheat Sheet

| Annotation                 | Description                                                                       | Usage Example                                             |
| -------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------- |
| `@Component`               | Marks a class as a Spring-managed component.                                      | `@Component public class MyService {}`                    |
| `@Controller`              | Specialization of `@Component` for web controllers (Spring MVC).                  | `@Controller public class MyController {}`                |
| `@Service`                 | Indicates a service layer component.                                              | `@Service public class MyService {}`                      |
| `@Repository`              | Indicates a DAO component (data access layer). Adds exception translation.        | `@Repository public class MyRepo {}`                      |
| `@Autowired`               | Automatically injects the required dependency by type.                            | `@Autowired private MyService service;`                   |
| `@Qualifier`               | Used with `@Autowired` to resolve ambiguity when multiple beans match.            | `@Qualifier("myBean")`                                    |
| `@Value`                   | Injects a property or value from properties file or environment.                  | `@Value("${db.url}") private String url;`                 |
| `@Bean`                    | Declares a bean inside a `@Configuration` class.                                  | `@Bean public MyBean bean() {}`                           |
| `@Configuration`           | Indicates that a class has `@Bean` definitions; used for Java-based config.       | `@Configuration public class AppConfig {}`                |
| `@Primary`                 | Marks a bean as the primary candidate for autowiring when multiple beans.         | `@Primary @Bean public Engine defaultEngine()`            |
| `@Scope`                   | Defines the scope of a bean (`singleton`, `prototype`, etc).                      | `@Scope("prototype")`                                     |
| `@PostConstruct`           | Method runs **after** dependency injection is done.                               | `@PostConstruct public void init()`                       |
| `@PreDestroy`              | Method runs **before** bean is destroyed.                                         | `@PreDestroy public void destroy()`                       |
| `@RequestMapping`          | Maps web requests to a method or controller.                                      | `@RequestMapping("/home")`                                |
| `@GetMapping`              | Shortcut for `@RequestMapping(method = GET)`.                                     | `@GetMapping("/users")`                                   |
| `@PostMapping`             | Shortcut for `@RequestMapping(method = POST)`.                                    | `@PostMapping("/add")`                                    |
| `@PathVariable`            | Binds URI template variable to method param.                                      | `@GetMapping("/user/{id}")`                               |
| `@RequestParam`            | Binds a query parameter to a method param.                                        | `@RequestParam String name`                               |
| `@RestController`          | Combines `@Controller` + `@ResponseBody` for REST APIs.                           | `@RestController public class Api {}`                     |
| `@ResponseBody`            | Indicates return value should be written to HTTP response body.                   | `@ResponseBody public String hello()`                     |
| `@RequestBody`             | Binds HTTP request body to method param.                                          | `@PostMapping("/") public void save(@RequestBody User u)` |
| `@ComponentScan`           | Tells Spring where to search for components.                                      | `@ComponentScan("com.example.service")`                   |
| `@EnableAutoConfiguration` | Tells Spring Boot to guess and configure beans.                                   | `@SpringBootApplication` includes this                    |
| `@SpringBootApplication`   | Combination of `@Configuration`, `@EnableAutoConfiguration`, and `@ComponentScan` | `@SpringBootApplication`                                  |

---

## Spring Architecture

```text
+----------------------------------------------------------+
|                  Spring Application                      |
+----------------------------------------------------------+
|     Spring AOP     |    Spring ORM    |   Spring Web     |
+----------------------------------------------------------+
|        Spring Context (ApplicationContext)               |
+----------------------------------------------------------+
|          Spring Core Container (Beans, Core, EL, Context)|
+----------------------------------------------------------+
|                    Java SE / EE APIs                     |
+----------------------------------------------------------+
```

- Expression Language (SpEL) : SPRING EXPRESSION LANGUAGE>
  ` Allows querying and manipulating objects at runtime (like ${} and #{} expressions).`

- conclusion on architectural principles followed by spring .
  `Overall, the Spring framework architecture is based on the principles of modularity, separation of concerns, and flexibility, providing developers with a powerful set of tools to build robust, scalable, and maintainable enterprise applications. The framework's modular architecture allows developers to select only the necessary modules for their specific needs, reducing unnecessary overhead and complexity in the application. Additionally, the Spring framework's flexible configuration model allows developers to configure the application using various approaches, such as XML-based configuration, Java-based configuration, and annotation-based configuration.`
