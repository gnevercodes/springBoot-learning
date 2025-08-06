# Bean life cycle:

Sequence of steps going from creation to destruction.

## phases of bean life cycle:

1. Container Started: The Spring IoC container is initialized.
2. Bean Instantiated: The container creates an instance of the bean.
3. Dependencies Injected: The container injects the dependencies into the bean.
4. Custom init() method: If the bean implements 5. InitializingBean or has a custom initialization method specified via @PostConstruct or init-method.
5. Bean is Ready: The bean is now fully initialized and ready to be used.
6. Custom utility method: This could be any custom method you have defined in your bean.
7. Custom destroy() method: If the bean implements DisposableBean or has a custom destruction method specified via @PreDestroy or destroy-method, it is called when the container is shutting down.

## Ways to Implement the Bean Life Cycle

Spring provides three ways to implement the life cycle of a bean.

1. `Using XML Configuration` : In this approach, in order to avail custom init() and destroy() methods for a bean we have to register these two methods inside the Spring XML configuration file while defining a bean.
   > if we declare a custom iniatilization method or preconstruct or a postconstruct like destroy() methods which are defined in our java class we have to mention it in the xml file.

```xml
<beans xmlns="http://www.springframework.org/schema/beans//////"
       xmlns:xsi="https://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans//////
           http://www.springframework.org/schema/beans///////spring-beans.xsd">

    <bean id="hw" class="beans.HelloWorld"
          init-method="init" destroy-method="destroy"/>
</beans>
```

2. Using Programmatic Approach (Interface)
   > To provide the facility to the created bean to invoke custom init() method on the startup of a spring container and to invoke the custom destroy() method on closing the container, we need to implement our bean with two interfaces.

> so here we need to implement two predefined methods :
> `override their methods afterPropertiesSet() and destroy() method`

```java
package beans;

import org.springframework.beans.factory.DisposableBean;
import org.springframework.beans.factory.InitializingBean;

public class HelloWorld implements InitializingBean,DisposableBean {

	@Override
	public void afterPropertiesSet() throws Exception
	{
		System.out.println("Bean HelloWorld has been "	+ "instantiated and I'm the " + "init() method");
	}

	@Override
	public void destroy() throws Exception
	{
		System.out.println("Container has been closed "+ "and I'm the destroy() method");
	}
}
```

3. using annotations.  
   **To provide the facility to the created bean to invoke custom init() method on the startup of a spring container and to invoke the custom destroy() method on closing the container, we need to annotate init() method by @PostConstruct annotation and destroy() method by @PreDestroy annotation**

```java
package beans;

import javax.annotation.PostConstruct;
import javax.annotation.PreDestroy;

public class HelloWorld {

	@PostConstruct
	public void init() throws Exception
	{
		System.out.println(
			"Bean HelloWorld has been "	+ "instantiated and I'm the " + "init() method");
	}

	@PreDestroy
	public void destroy() throws Exception
	{
		System.out.println("Container has been closed " + "and I'm the destroy() method");
	}
}
```

`When you might need ConfigurableApplicationContext:   
You would only need ConfigurableApplicationContext if you need to:
Manually control the application context lifecycle
Add/remove bean definitions at runtime
Configure the context programmatically
Access more advanced configuration options
`
