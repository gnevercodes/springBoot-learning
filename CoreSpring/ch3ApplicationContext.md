# application constant.

---

## intro

- ApplicationContext belongs to Spring Framework.
- `Spring IOC container is responsible for instantiating and wiring , configuring and managing the entire life cycle of beans or objects.`
- `BeanFactory` and `Application context` represent the `Spring IOC containers`.

| Bean factory                    | top interface |
| ------------------------------- | ------------- |
| ----------implements ---------- |
| -------Application Context ---- |

- application context is the superset of beanfactory and provides all the features provided by the bean factory.

## application context features.

1. basic to enterprise specific functionalities.
2. publishing events to registered listeneres.
3. methods for accessing application components.
4. internilization.
5. loading in a generic fashion.

## implementation classes.

1. annotationConfigapplicationcontext container.
2. annotationconfigwebapplicationcontext.
3. xmlwebapplicationcontext.
4. filesystemxmlapplicationcontext.
5. classpathXMLapplicationcontet.

### 1: annotation:

> AnnotationConfigApplicationContext class was introduced in Spring 3.0. It accepts classes annotated with @Configuration, @Component, and JSR-330 compliant classes. The constructor of AnnotationConfigApplicationContext accepts one or more classes.

### 2 : annotation support for web.

> AnnotationConfigWebApplicationContext class was introduced in Spring 3.0. It is similar to AnnotationConfigApplicationContext for a web environment. It accepts classes annotated with @Configuration, @Component, and JSR-330 compliant classes. These classes can be registered via register() method or passing base packages to scan() method. This class may be used when we configure ContextLoaderListener servlet listener or a DispatcherServlet in a web.xml.

### 3 :Container 3: XmlWebApplicationContext
