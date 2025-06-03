# AOP Spring Boot Interview Questions & Answers

## Basic Level Questions

### 1. What is AOP in Spring?
**Answer:** AOP (Aspect-Oriented Programming) is a programming paradigm that separates cross-cutting concerns (logging, security, transactions) from business logic using aspects, advice, and pointcuts.

### 2. What are cross-cutting concerns?
**Answer:** Functionalities that span multiple layers/modules like logging, security, validation, transaction management, error handling, and performance monitoring.

### 3. What is an Aspect?
**Answer:** A module that encapsulates cross-cutting concerns. It contains advice (what to do) and pointcuts (where to apply).

### 4. What is a Join Point?
**Answer:** A point in program execution where an aspect can be applied, typically method invocations in Spring AOP.

### 5. What is a Pointcut?
**Answer:** An expression that defines which join points an advice should be applied to. Uses execution expressions to match methods.

### 6. What is Advice?
**Answer:** The action taken by an aspect at a particular join point. Types: @Before, @After, @AfterReturning, @AfterThrowing, @Around.

### 7. What is Weaving?
**Answer:** The process of applying aspects to target objects to create advised objects. Spring uses runtime weaving through proxies.

### 8. How to enable AOP in Spring Boot?
**Answer:** Add `spring-boot-starter-aop` dependency and use `@EnableAspectJAutoProxy` annotation (auto-configured in Spring Boot).

## Intermediate Level Questions

### 9. What are the types of advice in Spring AOP?
**Answer:**
- `@Before` - Executes before method
- `@After` - Executes after method (finally block)
- `@AfterReturning` - Executes after successful return
- `@AfterThrowing` - Executes when exception thrown
- `@Around` - Surrounds method execution (most powerful)

### 10. What's the difference between @After and @AfterReturning?
**Answer:** `@After` executes regardless of method outcome (like finally), while `@AfterReturning` only executes when method returns successfully without exceptions.

### 11. What is ProceedingJoinPoint?
**Answer:** Used in `@Around` advice to control target method execution. Calling `proceed()` executes the original method. Can modify arguments and return values.

### 12. What are the limitations of Spring AOP?
**Answer:**
- Only works with Spring beans
- Only public methods can be advised
- Self-invocation doesn't trigger advice
- Works through proxies (JDK dynamic or CGLIB)

### 13. JDK Dynamic Proxy vs CGLIB Proxy?
**Answer:**
- **JDK Dynamic:** For interfaces, faster creation, slower execution
- **CGLIB:** For classes, slower creation, faster execution, can't proxy final methods/classes

### 14. What is the execution order of advice?
**Answer:** @Around(before) → @Before → Target Method → @Around(after) → @After → @AfterReturning/@AfterThrowing

### 15. How to control the order of aspects?
**Answer:** Use `@Order(value)` annotation on aspect classes. Lower values have higher priority.

## Advanced Level Questions

### 16. How to write a pointcut expression for all service layer methods?
**Answer:**
```java
@Pointcut("execution(* com.example.service.*Service.*(..))")
public void serviceLayer() {}
```

### 17. How to access method arguments in advice?
**Answer:**
```java
@Before("execution(* com.example.service.*.*(..))")
public void logArgs(JoinPoint joinPoint) {
    Object[] args = joinPoint.getArgs();
    // Process arguments
}
```

### 18. How to modify method arguments in @Around advice?
**Answer:**
```java
@Around("execution(* com.example.*.*(..))")
public Object modifyArgs(ProceedingJoinPoint pjp) throws Throwable {
    Object[] args = pjp.getArgs();
    // Modify args[0], args[1], etc.
    return pjp.proceed(args);
}
```

### 19. How to handle different return types in @Around advice?
**Answer:**
```java
@Around("execution(* com.example.*.*(..))")
public Object handleReturnTypes(ProceedingJoinPoint pjp) throws Throwable {
    Object result = pjp.proceed();
    if (result instanceof String) {
        return result.toString().toUpperCase();
    }
    return result;
}
```

### 20. How to create custom annotation for AOP?
**Answer:**
```java
@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface LogExecutionTime {}

@Around("@annotation(LogExecutionTime)")
public Object logTime(ProceedingJoinPoint pjp) throws Throwable {
    // Implementation
}
```

### 21. How to implement caching using AOP?
**Answer:**
```java
@Around("@annotation(Cacheable)")
public Object cache(ProceedingJoinPoint pjp) throws Throwable {
    String key = generateKey(pjp);
    Object cached = cache.get(key);
    if (cached != null) return cached;
    
    Object result = pjp.proceed();
    cache.put(key, result);
    return result;
}
```

### 22. What is @DeclareParents annotation?
**Answer:** Used for introduction (mixin) to add new methods/interfaces to existing classes without modifying them.

### 23. How to handle exceptions in @Around advice?
**Answer:**
```java
@Around("execution(* com.example.*.*(..))")
public Object handleException(ProceedingJoinPoint pjp) throws Throwable {
    try {
        return pjp.proceed();
    } catch (Exception e) {
        // Log exception, transform, or rethrow
        throw new CustomException("Processed: " + e.getMessage());
    }
}
```

### 24. What's the difference between Spring AOP and AspectJ?
**Answer:**
- **Spring AOP:** Runtime weaving, proxy-based, Spring beans only, simpler
- **AspectJ:** Compile/load-time weaving, more powerful, any Java object, complex setup

## Scenario-Based Questions

### 25. How would you implement audit logging for all database operations?
**Answer:**
```java
@AfterReturning("execution(* com.example.repository.*.*(..))")
public void auditDbOperation(JoinPoint jp) {
    String method = jp.getSignature().getName();
    auditService.log("DB Operation: " + method, getCurrentUser());
}
```

### 26. How to log execution time for methods taking more than 2 seconds?
**Answer:**
```java
@Around("execution(* com.example.service.*.*(..))")
public Object logSlowMethods(ProceedingJoinPoint pjp) throws Throwable {
    long start = System.currentTimeMillis();
    Object result = pjp.proceed();
    long duration = System.currentTimeMillis() - start;
    
    if (duration > 2000) {
        log.warn("Slow method: {} took {}ms", pjp.getSignature(), duration);
    }
    return result;
}
```

### 27. How to implement retry mechanism using AOP?
**Answer:**
```java
@Around("@annotation(Retryable)")
public Object retry(ProceedingJoinPoint pjp) throws Throwable {
    int attempts = 0;
    while (attempts < 3) {
        try {
            return pjp.proceed();
        } catch (Exception e) {
            attempts++;
            if (attempts >= 3) throw e;
            Thread.sleep(1000); // Wait before retry
        }
    }
    return null;
}
```

### 28. How to validate method parameters using AOP?
**Answer:**
```java
@Before("@annotation(ValidateParams)")
public void validateParams(JoinPoint jp) {
    Object[] args = jp.getArgs();
    for (Object arg : args) {
        if (arg == null) {
            throw new IllegalArgumentException("Parameter cannot be null");
        }
    }
}
```

### 29. How would you implement transaction management using AOP?
**Answer:**
```java
@Around("@annotation(Transactional)")
public Object manageTransaction(ProceedingJoinPoint pjp) throws Throwable {
    TransactionStatus status = transactionManager.getTransaction(definition);
    try {
        Object result = pjp.proceed();
        transactionManager.commit(status);
        return result;
    } catch (Exception e) {
        transactionManager.rollback(status);
        throw e;
    }
}
```

### 30. How to implement security check using AOP?
**Answer:**
```java
@Before("@annotation(RequiresRole)")
public void checkSecurity(JoinPoint jp) {
    RequiresRole annotation = getAnnotation(jp);
    String requiredRole = annotation.value();
    
    if (!currentUser.hasRole(requiredRole)) {
        throw new SecurityException("Access denied");
    }
}
```

## Troubleshooting Questions

### 31. Why is my AOP advice not executing?
**Answer:** Check: Bean is Spring-managed, method is public, correct pointcut expression, AOP is enabled, no self-invocation.

### 32. How to debug AOP issues?
**Answer:** Enable debug logging, use `@EnableAspectJAutoProxy(exposeProxy = true)`, check proxy creation, verify pointcut expressions.

### 33. What happens with self-invocation in AOP?
**Answer:** Self-invocation bypasses proxy, so advice doesn't execute. Use `AopContext.currentProxy()` or restructure code.

### 34. Performance impact of AOP?
**Answer:** Minimal overhead due to proxy creation and method interception. Use specific pointcuts and lightweight advice to minimize impact.

### 35. Can AOP work with final methods/classes?
**Answer:** No with CGLIB proxies (can't extend final). JDK dynamic proxies work with interfaces regardless of final implementations.

## Best Practices Questions

### 36. What are AOP best practices?
**Answer:**
- Use specific pointcut expressions
- Keep advice lightweight
- Separate concerns into different aspects
- Handle exceptions properly
- Use appropriate advice types
- Consider performance impact

### 37. How to organize AOP code structure?
**Answer:**
```
src/main/java/
├── aspect/
│   ├── LoggingAspect.java
│   ├── SecurityAspect.java
│   └── PerformanceAspect.java
├── service/
└── config/AopConfig.java
```

### 38. When to use AOP vs Interceptors vs Filters?
**Answer:**
- **AOP:** Cross-cutting concerns across service layers
- **Interceptors:** Web layer concerns, request/response processing
- **Filters:** Servlet-level processing, authentication, encoding

### 39. How to test AOP aspects?
**Answer:**
- Unit test: Mock dependencies, test advice logic
- Integration test: Test complete flow with Spring context
- Use `@MockBean` for dependencies in aspect testing

### 40. What are common AOP anti-patterns?
**Answer:**
- Overusing AOP for simple logic
- Complex business logic in aspects
- Too broad pointcut expressions
- Ignoring performance implications
- Not handling exceptions in advice