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
