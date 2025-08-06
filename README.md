# 🌱 Spring Framework Tutorial 

Welcome to my Spring Framework learning journey!

This repository documents my hands-on practice and notes as I explore and implement key Spring concepts. I’ve built this tutorial from scratch by combining lessons from trusted sources like [GeeksforGeeks](https://www.geeksforgeeks.org/) and my own interpretations to truly understand the Spring ecosystem.

---

## ✅ What You’ll Learn

This project focuses on mastering the Spring Core module with real code examples and clear structure. Topics covered include:

- 🔧 **Beans & IOC Containers**
  - Understanding `BeanFactory` and `ApplicationContext`
  - Managing bean lifecycles and scope (`singleton`, `prototype`, etc.)

- 🧩 **Dependency Injection (DI)**
  - Constructor Injection
  - Setter Injection
  - XML and Annotation-based configurations

- 🧠 **Spring Expression Language (SpEL)**
  - Dynamically injecting values into beans using expressions

- 💡 **Common Spring Annotations**
  - `@Component`, `@Service`, `@Repository`, `@Controller`
  - `@Autowired`, `@Qualifier`, `@Value`, and more

- 🧙‍♂️ **Annotation vs XML Config**
  - Legacy XML-based bean configuration vs modern annotation-driven development

---

## 📁 Project Structure
```
spring-tutorial/ # actual project flow in every springboot application. 
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/ganesh/spring/    # Core Java logic
│   │   └── resources/
│   │       └── beans.xml             # XML configs
├── pom.xml                           # Maven build file
├── README.md
```
---

## ⚙️ Prerequisites

- Java 8+
- Maven
- IDE (IntelliJ IDEA / Eclipse / VS Code)

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/spring-tutorial.git
   cd spring-tutorial
   ```

2. Compile and run:
```bash
mvn clean install
```
