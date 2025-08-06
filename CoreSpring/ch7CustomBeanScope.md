# Custom Bean Scope in Spring

In Spring, Objects are managed by the Spring IOC(Inversion of Control) container, and their lifecycle is determined by the scope. Spring provides two standard scopes, which are listed below:

Singleton Scope: One instance of the bean is created per Spring IOC Container. This is the default scope.
Prototype Scope: A new instance of the bean is created every time it is requested.

## learning recommended prerequisite:

Bean Scopes refer to the lifecycle of a Bean, which means when the object of a Bean is instantiated, how long it lives, and how many objects are created for that Bean throughout its lifetime. Basically, it controls the instance creation of the bean, and it is managed by the Spring container.
The Spring framework provides five scopes for a bean. We can use three of them only in the context of a web-aware Spring ApplicationContext, and the rest of the two are available for both an IoC container and a Spring-MVC container. The following are the different scopes provided for a bean:

1. Singleton: Only one instance will be created for a single bean definition per Spring IoC container, and the same object will be shared for each request made for that bean.
2. Prototype: A new instance will be created for a single bean definition every time a request is made for that bean.
3. Request: A new instance will be created for a single bean definition every time an HTTP request is made for that bean. But only valid in the context of a web-aware Spring ApplicationContext.
4. Session: Scopes a single bean definition to the lifecycle of an HTTP Session. But only valid in the context of a web-aware Spring ApplicationContext.
5. Global-Session: Scopes a single bean definition to the lifecycle of a global HTTP Session. It is also only valid in the context of a web-aware Spring ApplicationContext.

---
