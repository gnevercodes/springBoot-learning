# Expression Language (SpEL) - `“A way to talk to Java objects using expressions at runtime. Like math, logic, and method calls… all in strings.”`

SpEL (Spring Expression Language) is like a mini language inside Spring that lets you write expressions to:

1. access bean props.
2. call methods.
3. perform arithmetic ops .
4. conditional logic.

```java
@Value("#{systemProperties['user.name']}")
@Value("#{environment['JAVA_HOME']}")
@Value("#{5 * 10}")
private int calculatedValue;

```

🔐 Gotchas:
• Use #{} not ${} — ${} is for property placeholder (like application.properties), whereas #{} is for SpEL.
• SpEL runs at runtime — so if you mess up the expression, it will fail at runtime, not compile time.

main :

1.  Expression : this is a compiled expresion like end result of some additin : like the end result of parsing your expression string
2.  ExpressionParser (Interface)
    • This is the engine that takes your SpEL expression string and turns it into an Expression object.
    • It’s an interface, meaning you don’t directly use it—you use its implementation.
