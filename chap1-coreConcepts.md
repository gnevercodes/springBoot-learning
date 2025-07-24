# core concepts in spring.

## Dependency injection :

- dependency injection is a design pattern used in software development to implement inversion of control
- this allow's it's class to receive dependencies from another `source` rather than creating them with the `same class`.
- This reduces the main class dependencies with other classes.

### Types of dependency injection :

- Constructor injection : he dependent object is provided to the class via its constructor. The dependencies are passed when an instance of the class is created.
- setter injection : n setter injection, the dependent object is provided to the class via a setter method after the class is instantiated. This allows you to change the dependencies dynamically.
- field injection :
