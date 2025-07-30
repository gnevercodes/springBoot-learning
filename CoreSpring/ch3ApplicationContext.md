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
