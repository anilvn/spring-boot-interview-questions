# Spring Boot Interview Questions & Answers

<!-- <h2 align="center">🙌 Support & Connect</h2> -->

<p align="center">
  <a href="https://github.com/anilvn/spring-boot-interview-questions" target="_blank" rel="noopener noreferrer">
    <img src="https://img.shields.io/github/stars/anilvn/spring-boot-interview-questions?style=social" alt="GitHub Stars" />
  </a>
  &nbsp;
  <a href="https://www.linkedin.com/in/anil-valsa/" target="_blank" rel="noopener noreferrer">
    <img src="https://img.shields.io/badge/LinkedIn--blue?style=social&logo=linkedin" alt="LinkedIn" />
  </a>
</p>

<p align="center">
  ⭐ <strong>Please consider giving it a ⭐️ to show your support!</strong>
  <a href="https://github.com/anilvn/spring-boot-interview-questions" target="_blank" rel="noopener noreferrer">Click here</a>
  &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <strong>Let’s connect professionally:</strong>
  <a href="https://www.linkedin.com/in/anil-valsa/" target="_blank" rel="noopener noreferrer">Anil Valsa on LinkedIn</a>
</p>

---
Welcome to the comprehensive collection of essential Spring and Spring Boot interview questions covering core concepts, annotations, dependency injection, configurations, and best practices to help you prepare for your next Java developer interview.
### Additional Resources

If you found this guide helpful, you might also be interested in my other Spring Framework resources:
- [Core Java & Java-8 Interview Questions](https://github.com/anilvn/Java-Interview-Questions/tree/main)
- [Spring Boot Interview Questions](https://github.com/anilvn/spring-boot-interview-questions/tree/main)
- [Microservices with Spring Cloud Tutorials](https://javatechonline.com/microservices-tutorial/)

Feel free to star and fork these repositories if you find them useful!

---

### Table of Contents

| No. | Questions |
|---- | ---------|
|1 | [What is Spring Boot?](#what-is-spring-boot)|
|2 | [What is Spring?](#what-is-spring)|
|3 | [What are the features of the Spring Framework?](#what-are-the-features-of-the-spring-framework)|
|4 | [Why not plain Spring?](#why-not-plain-spring)|
|5 | [What is RAD, and how can you achieve RAD using Spring Boot?](#what-is-rad-and-how-can-you-achieve-rad-using-spring-boot)|
|6 | [What are different modules in Spring?](#what-are-different-modules-in-spring)|
|7 | [What is Dependency Injection (DI)?](#what-is-dependency-injection-di)|
|8 | [What is Inversion of Control (IOC) in Spring?](#what-is-inversion-of-control-ioc-in-spring-what-is-the-purpose-of-it)|
|9 | [What is a Spring Bean?](#what-is-a-spring-bean)|
|10 | [What are inner beans in Spring?](#what-are-inner-beans-in-spring)|
|11 | [What is Bean Wiring?](#what-is-bean-wiring)|
|12 | [What Bean Scopes Does Spring Provide?](#what-bean-scopes-does-spring-provide)|
|13 | [What is a Spring Configuration File?](#what-is-a-spring-configuration-file)|
|14 | [What is Autowiring in Spring?](#what-is-autowiring-in-spring-and-what-are-the-different-modes-it-has)|
|15 | [What is the Difference Between @Autowired and @Inject?](#what-is-the-difference-between-autowired-and-inject)|
|16 | [What is the Difference Between @Component and @Bean?](#what-is-the-difference-between-component-and-bean)|
|17 | [What is the Use of @Autowired Annotation in Spring?](#what-is-the-use-of-autowired-annotation-in-spring)|
|18 | [What is the Use of @Qualifier Annotation in Spring Framework?](#what-is-the-use-of-qualifier-annotation-in-spring-framework)|
|19 | [What's the Difference Between Constructor and Setter Injection?](#whats-the-difference-between-constructor-and-setter-injection)|
|20 | [What are the Stereotype Annotations?](#what-are-the-stereotype-annotations)|
|21 | [How Many Types of IoC Containers Are There in Spring?](#how-many-types-of-ioc-containers-are-there-in-spring)|
|22 | [What are the Common Implementations of the ApplicationContext?](#what-are-the-common-implementations-of-the-applicationcontext)|
|23 | [What is the Use of @Required Annotation in Spring Framework?](#what-is-the-use-of-required-annotation-in-spring-framework)|
|24 | [What are Lifecycle Methods in Spring?](#what-are-lifecycle-methods-in-spring)|
|25 | [What are Different Ways of Writing Lifecycle Methods in Spring?](#what-are-different-ways-of-writing-lifecycle-methods-in-spring)|
|26 | [What are Profiles in Spring?](#what-are-profiles-in-spring)|
|27 | [Is it possible to change the port of the Embedded Tomcat server in Spring Boot?](#is-it-possible-to-change-the-port-of-the-embedded-tomcat-server-in-spring-boot)|
|28 | [Can we disable the default web server in a Spring Boot application?](#can-we-disable-the-default-web-server-in-a-spring-boot-application)|
|29 | [Can we override or replace the Embedded Tomcat server in Spring Boot?](#can-we-override-or-replace-the-embedded-tomcat-server-in-spring-boot)|
|30 | [How to disable a specific auto-configuration class?](#how-to-disable-a-specific-auto-configuration-class)|
|31 | [What does the @SpringBootApplication annotation do internally?](#what-does-the-springbootapplication-annotation-do-internally)|
|32 | [Explain the @RestController annotation in Spring Boot?](#explain-the-restcontroller-annotation-in-spring-boot)|
|33 | [Difference between @RestController and @Controller in Spring Boot?](#difference-between-restcontroller-and-controller-in-spring-boot)|
|34 | [Major Differences Between @RequestMapping and @GetMapping?](#major-differences-between-requestmapping-and-getmapping)|
|35 | [Spring Actuator and Its Advantages?](#spring-actuator-and-its-advantages)|
|36 | [How to use a property defined in application.properties file into your Java class?](#how-to-use-a-property-defined-in-applicationproperties-file-into-your-java-class)|
|37 | [Use of Profiles in Spring Boot?](#use-of-profiles-in-spring-boot)|

## What is Spring Boot?

Spring Boot is an extension of the Spring Framework that simplifies the process of setting up and developing new Spring applications. It eliminates the need for complex XML configurations and offers various features to enhance developer productivity.

Reasons for using Spring Boot:
- **Auto-Configuration**: Automatically configures Spring and third-party libraries, reducing the need for manual setup.
- **Starter Dependencies**: Provides a set of convenient dependency descriptors for building applications quickly.
- **Embedded Servers**: Comes with embedded web servers like Tomcat, Jetty, or Undertow, making it easy to run applications without external servers.
- **Production-Ready Features**: Includes built-in support for metrics, health checks, and externalized configuration.
- **Minimal Configuration**: Significantly reduces boilerplate code and configuration, allowing developers to focus on writing business logic.

**[⬆ Back to Top](#table-of-contents)**

## What is Spring?

Spring is a comprehensive framework for enterprise Java development. It provides a wide range of functionalities, such as dependency injection, aspect-oriented programming, transaction management, and integration with various data access frameworks. Spring aims to simplify Java development by promoting best practices like loose coupling through dependency injection, declarative programming, and aspect-oriented programming.

**[⬆ Back to Top](#table-of-contents)**

## What are the features of the Spring Framework?

The Spring Framework offers several key features:

- **Dependency Injection (DI)**: Promotes loose coupling by managing object dependencies outside of the application code.
- **Aspect-Oriented Programming (AOP)**: Enables separation of cross-cutting concerns like logging, security, and transaction management.
- **Transaction Management**: Simplifies programmatic and declarative transaction management in Java applications.
- **Data Access Framework**: Provides integration with ORM frameworks (like Hibernate and JPA) and JDBC.
- **Spring MVC**: A robust model-view-controller framework for building web applications.
- **Security**: Offers comprehensive security features to secure Java applications.
- **Integration**: Supports integration with messaging, web services, and enterprise service buses (ESBs).
- **Testing**: Provides a wide range of testing support for integration and unit testing.

**[⬆ Back to Top](#table-of-contents)**

## Why not plain Spring?

While traditional Spring provides great flexibility and control, Spring Boot enhances developer efficiency by reducing setup and configuration overhead. In projects where quick setup and rapid development are priorities, Spring Boot is often preferred. If finer control over application components and configurations is needed, plain Spring might be more suitable.

**[⬆ Back to Top](#table-of-contents)**

## What is RAD, and how can you achieve RAD using Spring Boot?

RAD stands for Rapid Application Development, a methodology that emphasizes quick prototyping and iterative development. Spring Boot achieves RAD through:

- **Convention over Configuration**: Spring Boot follows sensible defaults and auto-configurations, reducing the need for explicit configuration.
- **Starter Projects**: Provides starter dependencies that include commonly used libraries and frameworks, allowing developers to start coding immediately.
- **Embedded Servers**: Eliminates the need for configuring external web servers, speeding up development and testing.
- **Spring Initializr**: An online tool that generates a ready-to-run Spring Boot project with the selected dependencies, saving time during the setup phase.

**[⬆ Back to Top](#table-of-contents)**

## What are different modules in Spring?

The Spring Framework consists of several modules, each providing distinct functionality:

**Spring Core Container**:
- **Beans**: Provides the basis for Spring's dependency injection.
- **Core**: Contains the core components and utilities.
- **Context**: Builds on the core and provides a way to access application objects.
- **Expression Language (SpEL)**: A powerful expression language for querying and manipulating objects at runtime.

**Spring AOP**: Provides aspect-oriented programming capabilities.

**Spring Data Access/Integration**:
- **JDBC**: Simplifies database access.
- **ORM**: Integrates with ORM tools like Hibernate.
- **JMS**: Supports Java Message Service.
- **Transactions**: Manages transactions programmatically or declaratively.

**Spring Web**:
- **Web**: Contains basic web-oriented integration features.
- **Web MVC**: Provides a full-featured MVC implementation.
- **Web Socket**: Supports WebSocket-based communication.

**Spring Security**: Provides security services for applications.

**Spring Test**: Supports testing with JUnit or TestNG.

**[⬆ Back to Top](#table-of-contents)**

## What is Dependency Injection (DI)?

Dependency Injection (DI) is a design pattern used to implement IoC, allowing the inversion of control between a class and its dependencies. In DI, the objects that an object depends on are injected into it, rather than the object creating them itself.

Advantages of DI:
- **Loose Coupling**: Makes the application components loosely coupled, as they don't have to instantiate their dependencies.
- **Easier Testing**: Facilitates unit testing by allowing mock dependencies to be injected.
- **Code Reusability**: Enhances code reuse and flexibility.
- **Configuration Flexibility**: Allows the configuration of different implementations without changing the code.

**[⬆ Back to Top](#table-of-contents)**

## What is Inversion of Control (IOC) in Spring? What is the Purpose of it?

Inversion of Control (IoC) is a principle in software engineering where the control of objects and their dependencies is transferred to a container or framework. In Spring, IoC is implemented through the use of dependency injection.

Purpose of IoC:
- **Decoupling**: Reduces the dependency between components, promoting a loosely coupled architecture.
- **Simplified Testing**: Facilitates testing by allowing dependencies to be easily mocked or stubbed.
- **Configurable Components**: Enables the configuration and assembly of components at runtime, outside of the code.
- **Centralized Configuration**: Provides a centralized configuration for managing dependencies and bean lifecycles.

**[⬆ Back to Top](#table-of-contents)**

## What is a Spring Bean?

A Spring Bean is an object that is managed by the Spring IoC container. Beans are instantiated, configured, and assembled by the container, based on the configuration metadata provided by the developer.

Key Characteristics:
- **Lifecycle Management**: The Spring container manages the lifecycle of beans.
- **Dependency Management**: Beans can be injected with dependencies by the container.
- **Scope**: Beans can be scoped to different levels, such as singleton, prototype, etc.

**[⬆ Back to Top](#table-of-contents)**

## What are inner beans in Spring?

Inner beans are beans that are defined within the scope of another bean's configuration. They are typically used for defining beans that are only used by their enclosing bean.

Characteristics:
- **Anonymous**: Inner beans do not have an identifier or a name and cannot be accessed outside the scope of their enclosing bean.
- **Short-Lived**: They are typically short-lived and not shared between multiple beans.
- **Defined in XML**: Often defined in XML configuration using the `<bean>` element within another `<bean>` element.

**[⬆ Back to Top](#table-of-contents)**

## What is Bean Wiring?

Bean Wiring refers to the process of connecting beans together within the Spring IoC container. This involves specifying how one bean should be injected into another, either through constructor arguments or properties.

Example: emp bean having a field address, so address will be the inner bean.

Ways to Wire Beans:
- **XML Configuration**: Using `<bean>` definitions and `<property>` or `<constructor-arg>` elements.
- **Annotations**: Using annotations like `@Autowired`, `@Inject`, or `@Resource` to declare dependencies.
- **Java Configuration**: Using `@Bean` methods in a `@Configuration` class.

**[⬆ Back to Top](#table-of-contents)**

## What Bean Scopes Does Spring Provide?

Spring provides several bean scopes that determine the lifecycle and visibility of a bean within the application:

- **Singleton**: A single shared instance per Spring IoC container (default scope).
- **Prototype**: A new instance every time a request for that bean is made.
- **Request**: A new instance per HTTP request (web applications only).
- **Session**: A new instance per HTTP session (web applications only).
- **Application**: A single instance per ServletContext (web applications only).
- **WebSocket**: A new instance per WebSocket session.

**[⬆ Back to Top](#table-of-contents)**

## What is a Spring Configuration File?

A Spring Configuration File is an XML or Java-based file that contains metadata for configuring beans, services, and dependencies within a Spring application. It defines how beans are created, initialized, and managed by the Spring IoC container.

Types of Configuration:
- **XML Configuration**: Uses XML files with `<beans>` definitions.
- **Java Configuration**: Uses `@Configuration` annotated classes with `@Bean` methods.
- **Annotation-Based Configuration**: Utilizes annotations like `@Component`, `@Service`, `@Repository`, etc.

**[⬆ Back to Top](#table-of-contents)**

## What is Autowiring in Spring, and What Are the Different Modes It Has?

Autowiring is a feature in Spring that allows the Spring container to automatically resolve and inject dependencies between beans. It simplifies the process of wiring beans by reducing the need for explicit configuration.

Autowiring Modes:
- **no**: Default mode, no autowiring is performed, and dependencies are injected manually.
- **byName**: Autowiring a bean property if there is a bean with the same name in the container.
- **byType**: Autowiring a bean property if there is exactly one bean of the property type in the container.
- **constructor**: Autowired constructor arguments by type.
- **autodetect**: Deprecated, automatically chooses constructor or byType based on the available constructors.

**[⬆ Back to Top](#table-of-contents)**

## What is the Difference Between @Autowired and @Inject?

Both `@Autowired` and `@Inject` are used for dependency injection, but they come from different libraries and have subtle differences:

- **@Autowired**: Provided by the Spring framework and can be used for field, constructor, and method injection. Supports optional dependencies through the required attribute.
- **@Inject**: Part of the Java EE (JSR-330) standard and provided by the javax.inject package. Does not support the required attribute.

Differences:
- **Scope**: `@Autowired` is specific to Spring, while `@Inject` is part of the Java standard.
- **Optional Dependencies**: `@Autowired` supports optional dependencies using `@Autowired(required = false)`, whereas `@Inject` does not.

**[⬆ Back to Top](#table-of-contents)**

## What is the Difference Between @Component and @Bean?

`@Component` and `@Bean` are both used to define beans in Spring, but they are used in different contexts:

- **@Component**: A class-level annotation used to indicate that a class should be managed as a Spring bean. It is part of Spring's stereotype annotations and is used for automatic component scanning.
- **@Bean**: A method-level annotation used in `@Configuration` classes to define beans explicitly. It is typically used for defining beans that require more complex initialization or configuration.

Differences:
- **Declaration**: `@Component` is used on classes, while `@Bean` is used on methods.
- **Automatic Scanning**: `@Component` is detected through component scanning, whereas `@Bean` is explicitly defined in configuration classes.

**[⬆ Back to Top](#table-of-contents)**

## What is the Use of @Autowired Annotation in Spring?

The `@Autowired` annotation is used in Spring to automatically inject dependencies into a bean. It can be applied to constructors, fields, or methods to resolve dependencies.

Use Cases:
- **Field Injection**: `@Autowired` on fields to inject dependencies directly.
- **Constructor Injection**: `@Autowired` on constructors to inject dependencies through constructor arguments.
- **Setter Injection**: `@Autowired` on setter methods to inject dependencies via setters.

**[⬆ Back to Top](#table-of-contents)**

## What is the Use of @Qualifier Annotation in Spring Framework?

The `@Qualifier` annotation is used in Spring to resolve ambiguity when multiple beans of the same type are available for dependency injection. It is used in conjunction with `@Autowired` to specify which bean should be injected.

Example:
```java
public class UserService {
    @Autowired
    @Qualifier("specificUserRepository")
    private UserRepository userRepository;
}
```

In this example, `@Qualifier("specificUserRepository")` indicates that the bean with the specified name should be injected, resolving ambiguity if multiple `UserRepository` beans are present.

**[⬆ Back to Top](#table-of-contents)**

## What's the Difference Between Constructor and Setter Injection?

Constructor Injection and Setter Injection are two ways to inject dependencies in Spring.

**Constructor Injection**:
- **Dependencies**: Injected through the constructor.
- **Mandatory Dependencies**: Ensures all required dependencies are provided at instantiation time.
- **Immutability**: Promotes immutability of the object by making dependencies final.
- **Circular Dependencies**: Can lead to issues if there are circular dependencies.

**Setter Injection**:
- **Dependencies**: Injected through setter methods.
- **Optional Dependencies**: Allows optional dependencies to be set.
- **Mutability**: Makes the object mutable, as dependencies can be changed after instantiation.
- **Readability**: Provides better readability for large objects with many dependencies.

**[⬆ Back to Top](#table-of-contents)**

## What are the Stereotype Annotations?

Stereotype Annotations in Spring are used to define beans that belong to a particular role or layer in the application. They help in organizing and identifying components within the application context.

Common Stereotype Annotations:
- **@Component**: Generic stereotype for any Spring-managed component.
- **@Service**: Indicates a service component, typically containing business logic.
- **@Repository**: Indicates a DAO (Data Access Object) component, typically for data access.
- **@Controller**: Indicates a controller component, typically for handling web requests in Spring MVC.

**[⬆ Back to Top](#table-of-contents)**

## How Many Types of IoC Containers Are There in Spring?

Spring provides two main types of IoC containers:

- **BeanFactory**: The simplest container that provides basic support for dependency injection. It lazily initialized beans, meaning beans are created only when they are requested.
- **ApplicationContext**: A more advanced container that extends BeanFactory, providing additional features like event propagation, internationalization, and declarative mechanisms for creating beans.

**[⬆ Back to Top](#table-of-contents)**

## What are the Common Implementations of the ApplicationContext?

Spring provides several implementations of the ApplicationContext interface, each designed for different environments:

- **AnnotationConfigApplicationContext**: Used for standalone Java applications that use annotations for configuration.
- **ClassPathXmlApplicationContext**: Loads context definition from an XML file located in the classpath.
- **FileSystemXmlApplicationContext**: Loads context definition from an XML file in the filesystem.
- **WebApplicationContext**: A specialized version of ApplicationContext for web applications, used in Spring MVC.

**[⬆ Back to Top](#table-of-contents)**

## What is the Use of @Required Annotation in Spring Framework?

The `@Required` annotation in Spring is used to enforce that a bean property is set during configuration. It can be applied to setter methods to ensure that the corresponding property is populated in the bean configuration.

Example:
```java
public class User {
    private String name;

    @Required
    public void setName(String name) {
        this.name = name;
    }
}
```

In this example, the `@Required` annotation ensures that the name property is set in the configuration. If the property is not provided, the container will throw an exception.

**[⬆ Back to Top](#table-of-contents)**

## What are Lifecycle Methods in Spring?

Lifecycle Methods in Spring are methods that are called at specific points in the lifecycle of a bean. These methods allow developers to perform custom initialization and cleanup tasks.

Common Lifecycle Methods:
- **init Method**: Called after the bean is fully initialized, allowing for custom initialization logic.
- **destroy Method**: Called before the bean is removed from the container, allowing for cleanup tasks.
- **PostConstruct and PreDestroy Annotations**: `@PostConstruct` and `@PreDestroy` are used to define lifecycle methods in Java-based configuration.

**[⬆ Back to Top](#table-of-contents)**

## What are Different Ways of Writing Lifecycle Methods in Spring?

Spring provides several ways to define lifecycle methods:

1. **XML Configuration**: Define `init-method` and `destroy-method` attributes in `<bean>` definitions.
2. **Annotations**: Use `@PostConstruct` and `@PreDestroy` annotations on methods in bean classes.
3. **Implementing Interfaces**: Implement `InitializingBean` and `DisposableBean` interfaces and override `afterPropertiesSet()` and `destroy()` methods.
4. **Java Configuration**: Use `@Bean` annotations with `initMethod` and `destroyMethod` attributes in `@Configuration` classes.

**[⬆ Back to Top](#table-of-contents)**

## What are Profiles in Spring?

Profiles in Spring are a way to segregate different parts of an application configuration and make them available only in specific environments. This is useful for environment-specific configurations, such as development, testing, and production.

Usage:
- **Defining Profiles**: Use the `@Profile` annotation on beans or configuration classes.
- **Activating Profiles**: Use the `spring.profiles.active` property to activate profiles in application.properties or as a JVM argument.

**[⬆ Back to Top](#table-of-contents)**

## Is it possible to change the port of the Embedded Tomcat server in Spring Boot?

Yes, it is possible to change the port of the embedded Tomcat server in Spring Boot. You can do this by configuring the `server.port` property in the application.properties or application.yml file.

Example:
```properties
server.port=8081
```

Or in application.yml:
```yaml
server:
  port: 8081
```

**[⬆ Back to Top](#table-of-contents)**

## Can we disable the default web server in a Spring Boot application?

Yes, you can disable the default embedded web server in a Spring Boot application. This is typically done in applications that are not web-based or when using Spring Boot for batch processing or background services.

How to Disable:
- **In Code**: Use `SpringApplicationBuilder` to disable the web environment.
- **In Properties**: Set the `spring.main.web-application-type` property to `none`.

**[⬆ Back to Top](#table-of-contents)**

## Can we override or replace the Embedded Tomcat server in Spring Boot?

Yes, you can override or replace the embedded Tomcat server in Spring Boot with another server, such as Jetty or Undertow.

How to Replace:
1. **Exclude Tomcat**: Exclude the Tomcat dependency from the Spring Boot starter.
2. **Add New Server**: Add a dependency for the new server, such as Jetty or Undertow.

**[⬆ Back to Top](#table-of-contents)**

## How to disable a specific auto-configuration class?

You can disable a specific auto-configuration class in Spring Boot using the `exclude` attribute of the `@SpringBootApplication` annotation or the `spring.autoconfigure.exclude` property.

Using `@SpringBootApplication`:
```java
@SpringBootApplication(exclude = {DataSourceAutoConfiguration.class})
public class MyApplication {
    public static void main(String[] args) {
        SpringApplication.run(MyApplication.class, args);
    }
}
```

Using Properties:
```properties
spring.autoconfigure.exclude=org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration
```

**[⬆ Back to Top](#table-of-contents)**

## What does the @SpringBootApplication annotation do internally?

The `@SpringBootApplication` annotation is a convenience annotation that combines several other annotations into one, simplifying Spring Boot application configuration.

Components of `@SpringBootApplication`:
- **@Configuration**: Indicates that the class is a source of bean definitions.
- **@EnableAutoConfiguration**: Enables Spring Boot's auto-configuration feature, which automatically configures beans based on classpath settings and other conditions.
- **@ComponentScan**: Scans for Spring components (like `@Component`, `@Service`, `@Repository`, etc.) in the package where the application class is located and its sub-packages.

**[⬆ Back to Top](#table-of-contents)**

## Explain the @RestController annotation in Spring Boot?

The `@RestController` annotation in Spring Boot is a specialized version of the `@Controller` annotation that is used to create RESTful web services.

Features:
- **Combines @Controller and @ResponseBody**: Eliminates the need to use `@ResponseBody` on each handler method, as it automatically serializes returned objects into HTTP response bodies.
- **RESTful Endpoints**: Simplifies the creation of RESTful endpoints by handling HTTP requests and responses directly.

**[⬆ Back to Top](#table-of-contents)**

## Difference between @RestController and @Controller in Spring Boot?

`@RestController` and `@Controller` are both used to define controller components in Spring Boot, but they serve different purposes:

- **@Controller**: Used for traditional MVC controllers that return views (e.g., JSPs or Thymeleaf templates). Methods in a `@Controller` are typically annotated with `@ResponseBody` to return data directly.
- **@RestController**: A specialized version of `@Controller` for RESTful services, where each method returns data directly (as JSON or XML) and is automatically annotated with `@ResponseBody`.

**[⬆ Back to Top](#table-of-contents)**

## Major Differences Between @RequestMapping and @GetMapping?

`@RequestMapping` and `@GetMapping` are used to map HTTP requests to handler methods, but they differ in specificity and use cases:

- **@RequestMapping**: A versatile annotation that can map requests based on HTTP methods, paths, headers, and more. It can be used at both the class and method levels.
- **@GetMapping**: A shorthand annotation for `@RequestMapping` that is specific to HTTP GET requests. It improves readability and conciseness for methods that handle GET requests.

**[⬆ Back to Top](#table-of-contents)**

## Spring Actuator and Its Advantages?

Spring Actuator is a sub-project of Spring Boot that provides a set of tools and features for monitoring and managing Spring Boot applications.

Advantages:
- **Health Checks**: Provides health information about the application.
- **Metrics**: Exposes metrics about the application, such as memory usage, CPU usage, and request statistics.
- **Application Info**: Displays information about the application, including build details and environment properties.
- **Endpoints**: Offers various endpoints for managing and monitoring the application (e.g., `/actuator/health`, `/actuator/metrics`).
- **Custom Endpoints**: Allows developers to create custom endpoints for application-specific monitoring.

**[⬆ Back to Top](#table-of-contents)**

## How to use a property defined in application.properties file into your Java class?

You can use properties defined in the application.properties file in your Java classes by leveraging Spring's `@Value` annotation or `Environment` interface.

Using `@Value` Annotation:
```java
import org.springframework.beans.factory.annotation.Value;
import org.springframework.stereotype.Component;

@Component
public class MyService {

    @Value("${my.property}")
    private String myProperty;

    public void printProperty() {
        System.out.println("Property Value: " + myProperty);
    }
}
```

Using `Environment` Interface:
```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.core.env.Environment;
import org.springframework.stereotype.Component;

@Component
public class MyService {

    @Autowired
    private Environment environment;

    public void printProperty() {
        String myProperty = environment.getProperty("my.property");
        System.out.println("Property Value: " + myProperty);
    }
}
```

**[⬆ Back to Top](#table-of-contents)**

## Use of Profiles in Spring Boot?

Profiles in Spring Boot are used to segregate different parts of an application configuration and make them available only in specific environments. They help manage different configurations for development, testing, and production environments.

Advantages:
- **Environment-Specific Configuration**: Profiles allow for different configurations based on the environment.
- **Simplified Configuration Management**: Makes it easier to manage multiple configurations within a single application.
- **Flexible Activation**: Profiles can be activated through properties files, environment variables, or command-line arguments.

How to Use:
- **Define Profiles**: Use `@Profile` annotation in configuration classes or bean definitions.
- **Activate Profiles**: Use `spring.profiles.active` property to activate specific profiles.
- **Environment-Specific Properties**: Create separate properties files for each profile, such as `application-dev.properties`, `application-test.properties`, etc.

**[⬆ Back to Top](#table-of-contents)**

