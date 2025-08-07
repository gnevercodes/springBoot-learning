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
3.  SpelExpressionParser (Class)
    • This is the default implementation of ExpressionParser.
    • It knows how to understand SpEL syntax like:
4.  EvaluationContext (Interface)
    • It provides context for evaluation.
    • Like, where should the SpEL look for variables, beans, etc.?

---

```java
import org.springframework.expression.ExpressionParser;
import org.springframework.expression.spel.standard.SpelExpressionParser;
import org.springframework.expression.Expression;
import org.springframework.expression.spel.support.StandardEvaluationContext;

public class SpELDemo {
    public static void main(String[] args) {
        Person person = new Person("Ganesh", 25);

        ExpressionParser parser = new SpelExpressionParser();
        StandardEvaluationContext context = new StandardEvaluationContext(person);

        Expression exp = parser.parseExpression("name");
        String name = exp.getValue(context, String.class); // → "Ganesh"

        System.out.println("Person name is: " + name);
    }
}

class Person {
    private String name;
    private int age;

    public Person(String name, int age) { this.name = name; this.age = age; }
    public String getName() { return name; }
    public int getAge() { return age; }
}
```
