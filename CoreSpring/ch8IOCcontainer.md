# IOC container:

`The Spring framework is a powerful framework for building Java applications. It can be considered a collection of sub-frameworks, also referred to as layers, such as Spring AOP, Spring ORM, Spring Web Flow, and Spring Web MVC. We can use any of these modules separately while constructing a Web application. The modules may also be grouped to provide better functionalities in a web application.`

## Spring Container

The core component of the spring framework is the Inversion of Control (IOC) container, which is responsible for managing the lifecycle of objects called beans and their dependencies. Spring provides two types of containers:

BeanFactory Container
This is the basic container that provides support for dependency injection.
In this, beans are instantiated only when explicitly requested.
It is lightweight and suitable for resource-constrained environments.
ApplicationContext Container
This is an advanced container built on top of the BeanFactory.
It includes all the features of BeanFactory and adds extra functionalities such as internationalization, event propagation, and integration with other Spring modules.
In this, beans are created and configured at startup.
