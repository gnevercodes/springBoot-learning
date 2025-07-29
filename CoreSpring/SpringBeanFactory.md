# Spring - BeanFactory - INTERFACE , SPRING IOC CONTAINER, PARENT INTERFACE OF APPLICATION CONTEXT.

- Spring is a container and behaves as the factory of beans.
- `BeanFactory interface is the simplest container providing an advanced configuration mechanism to instantiate, configure, and manage the life cycle of beans.`
  <br>

- Beans are java objects that are configured at run time by Spring IOC Container.
- `BeanFactory represents a basic IoC container which is a parent interface of ApplicationContext.`
  _bold_ BeanFactory does not support Annotation-based configuration whereas ApplicationContext does _bold_

## how beans are created:

- `BeanFactory uses Beans and their dependencies metadata to create and configure them at run-time.`.
  > we know beans can be created in multiple ways so : `BeanFactory loads the bean definitions and dependency amongst the beans based on a configuration file (XML) or the beans can be directly returned when required using Java Configuration.`.

## method and description

1. containsBean(String name) ; does the bean factory contain this bean.
2. getAliases(String name) return the aliases.
3. getBean(class<T> requiredType) return the bean that uniquely matches the given object type.
4. getBean(class<T> req type obj args) :: return an instance.
5. getBean(String Name) ; return the instance,

| Feature                                               | **BeanFactory** | **ApplicationContext** |
| ----------------------------------------------------- | --------------- | ---------------------- |
| Basic IoC                                             | ✅ Yes          | ✅ Yes                 |
| **Annotation support (@Component, @Autowired, etc.)** | ❌ **Nope**     | ✅ **Yes!**            |
| Lifecycle callbacks (`@PostConstruct`, `@PreDestroy`) | ❌              | ✅                     |
| Internationalization (i18n)                           | ❌              | ✅                     |
| Event propagation                                     | ❌              | ✅                     |
| Eager bean loading (by default)                       | ❌ Lazy         | ✅ Eager               |
| Most commonly used in Spring apps                     | ❌              | ✅ ✅ ✅               |

## important point : applicationCOntext ----> implements BeanFactory(parent)

1. so application context supports annotations but not beanfactory so it uses `classpathxmlapplicationContext`.
2. What if You Used BeanFactory? : `This will work only for XML-based configuration, and it has no idea what to do with annotations. It’ll be like:`.
