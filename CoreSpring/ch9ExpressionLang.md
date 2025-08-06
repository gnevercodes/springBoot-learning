# Expression Language (SpEL)

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
