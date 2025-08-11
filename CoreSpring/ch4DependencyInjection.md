# Dependency Injection :

1. Main functionality.
2. responsible for injecting dependencies.
3. in order to keep java classes independent of each other and the container frees them from object creation and maintenance.
4. > These classes, managed by Spring, must adhere to the standard definition of Java-Bean. Dependency Injection in Spring also ensures loose coupling between the classes.

`Loose coupling between classes can be possible by defining interfaces for common functionality and the injector will instantiate the objects of required implementation. The task of instantiating objects is done by the container according to the configurations specified by the developer.`

## Spring - Difference Between Inversion of Control and Dependency Injection

- IOC : `It is a design principle where the control of object creation and lifecycle is managed by a framework or container rather than by the developer. Spring IOC Container is responsible for creating, configuring, and managing the lifecycle of objects called beans.`
- di : ` It is a design pattern and a part of IOC container. It allows objects to be injected with their dependencies rather than creating those dependencies themselves`

> hello
