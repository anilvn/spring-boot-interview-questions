# Spring Web Module Interview Questions

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

This document is a comprehensive guide to Spring Web Module and RESTful web services, covering essential concepts like HTTP methods, annotations, controllers, and resource handling. It serves as a reference for developers working with Spring Boot to build web applications and APIs.

## Additional Resources

If you found this guide helpful, you might also be interested in my other Spring Framework resources:
- [Core Java & Java-8 Interview Questions](https://github.com/anilvn/Java-Interview-Questions/tree/main)
- [Spring Boot Interview Questions](https://github.com/anilvn/spring-boot-interview-questions/tree/main)
- [Microservices with Spring Cloud Tutorials](https://javatechonline.com/microservices-tutorial/)

Please consider starring and forking this repository if you find it useful!

---

## Table of Contents

| # | Question |
|---|----------|
| 1 | [What is ORM?](#what-is-orm) |
| 2 | [What is JPA?](#what-is-jpa) |
| 3 | [What are some advantages of using JPA?](#what-are-some-advantages-of-using-jpa) |
| 4 | [How can we enable Spring Data JPA?](#how-can-we-enable-spring-data-jpa) |
| 5 | [What is the use of Dialect and give some examples?](#what-is-the-use-of-dialect-and-give-some-examples) |
| 6 | [What is the Spring Data JPA repository?](#what-is-the-spring-data-jpa-repository) |
| 7 | [Explain Mapping Rule in JPA?](#explain-mapping-rule-in-jpa) |
| 8 | [What is an Entity class and commonly used annotations for this?](#what-is-an-entity-class-and-commonly-used-annotations-for-this) |
| 9 | [What is the difference between JPA and Hibernate?](#what-is-the-difference-between-jpa-and-hibernate) |
| 10 | [How can we create a custom repository in Spring Data JPA?](#how-can-we-create-a-custom-repository-in-spring-data-jpa) |
| 11 | [What are pre-defined methods given by Repository interfaces?](#what-are-pre-defined-methods-given-by-repository-interfaces) |
| 12 | [Differentiate between findById() and getOne()?](#differentiate-between-findbyid-and-getone) |
| 13 | [What is the naming convention for finder methods in the Spring Data repository interface?](#what-is-the-naming-convention-for-finder-methods-in-the-spring-data-repository-interface) |
| 14 | [What is the difference between PagingAndSortingRepository and JpaRepository?](#what-is-the-difference-between-pagingandsorting-repository-and-jparepository) |
| 15 | [What is PagingAndSortingRepository?](#what-is-pagingandsorting-repository) |
| 16 | [What is @Query used for?](#what-is-query-used-for) |
| 17 | [What type of Queries can be implemented using @Query annotation?](#what-type-of-queries-can-be-implemented-using-query-annotation) |
| 18 | [Give an example of using @Query annotation with JPQL?](#give-an-example-of-using-query-annotation-with-jpql) |
| 19 | [What are Collection Mappings Supported by JPA?](#what-are-collection-mappings-supported-by-jpa) |
| 20 | [What are different types of Joins supported by JPA?](#what-are-different-types-of-joins-supported-by-jpa) |
| 21 | [What is @EntityGraph in Spring Data JPA?](#what-is-entitygraph-in-spring-data-jpa) |
| 22 | [What is the Criteria API?](#what-is-the-criteria-api) |
| 23 | [What is the use of an Entity Manager?](#what-is-the-use-of-an-entity-manager) |

## What is ORM?

**Object-Relational Mapping (ORM)** is a programming technique used to convert data between incompatible type systems in object-oriented programming languages. ORM allows developers to work with databases using objects rather than writing SQL queries, providing a more intuitive and flexible way to manage data.

Key Features of ORM:

- **Abstraction**: Hides the complexity of database operations behind a simple object-oriented interface
- **Database Independence**: Allows applications to switch between different databases with minimal changes
- **Automated SQL Generation**: Automatically generates SQL queries for CRUD operations
- **Mapping**: Maps database tables to classes, rows to objects, and columns to fields
- **Transaction Management**: Provides mechanisms for managing transactions programmatically or declaratively

Examples of ORM Frameworks:

- Hibernate
- JPA (Java Persistence API)
- Entity Framework (for .NET)
- Django ORM (for Python)
- Active Record (for Ruby on Rails)

[Back to Top](#table-of-contents)

## What is JPA?

**Java Persistence API (JPA)** is a specification for managing relational data in Java applications. It provides a standard way to map Java objects to database tables and manage persistent data using an ORM approach. JPA is part of the Java EE (Enterprise Edition) platform but can also be used in Java SE (Standard Edition).

Key Features of JPA:

- **Standardization**: Provides a standard API for ORM, making it easier to switch between different ORM implementations like Hibernate, EclipseLink, and OpenJPA
- **Annotations**: Uses annotations to define entity mappings, relationships, and queries
- **Entity Lifecycle**: Manages the lifecycle of entities, including their creation, persistence, update, and removal
- **JPQL (Java Persistence Query Language)**: Provides a SQL-like query language for querying entities
- **Caching**: Supports caching mechanisms to improve performance by reducing database access

[Back to Top](#table-of-contents)

## What are some advantages of using JPA?

Using JPA offers several advantages when working with relational databases in Java applications:

- **Simplified Development**: Reduces boilerplate code for database operations, allowing developers to focus on business logic
- **Database Independence**: Provides database-agnostic development, enabling easy migration between different databases
- **Type Safety**: Offers type-safe queries through JPQL and Criteria API, reducing runtime errors
- **Object-Oriented Approach**: Allows developers to work with objects rather than relational data, providing a more natural way to interact with data
- **Automatic Schema Generation**: Can automatically generate database schemas based on entity mappings
- **Lazy and Eager Loading**: Supports different fetching strategies to optimize data retrieval
- **Transaction Management**: Integrates with transaction management systems to ensure data integrity
- **Caching**: Improves performance through first-level and second-level caching

[Back to Top](#table-of-contents)

## How can we enable Spring Data JPA?

To enable Spring Data JPA in a Spring Boot application, follow these steps:

1. **Add Dependencies**: Include the spring-boot-starter-data-jpa dependency in your pom.xml (for Maven) or build.gradle (for Gradle) file.

   **Maven**:
   ```xml
   <dependency>
       <groupId>org.springframework.boot</groupId>
       <artifactId>spring-boot-starter-data-jpa</artifactId>
   </dependency>
   <dependency>
       <groupId>com.h2database</groupId>
       <artifactId>h2</artifactId>
       <scope>runtime</scope>
   </dependency>
   ```

   **Gradle**:
   ```groovy
   implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
   runtimeOnly 'com.h2database:h2'
   ```

2. **Configure Data Source**: Define database connection properties in the application.properties or application.yml file.

   **application.properties**:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/mydatabase
   spring.datasource.username=root
   spring.datasource.password=password
   spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   ```

   **application.yml**:
   ```yaml
   spring:
     datasource:
       url: jdbc:mysql://localhost:3306/mydatabase
       username: root
       password: password
       driver-class-name: com.mysql.cj.jdbc.Driver

     jpa:
       hibernate:
         ddl-auto: update
       show-sql: true
   ```

3. **Enable JPA Repositories**: Use the @EnableJpaRepositories annotation in your main application class or configuration class.

   ```java
   import org.springframework.boot.SpringApplication;
   import org.springframework.boot.autoconfigure.SpringBootApplication;
   import org.springframework.data.jpa.repository.config.EnableJpaRepositories;

   @SpringBootApplication
   @EnableJpaRepositories
   public class MyApplication {
       public static void main(String[] args) {
           SpringApplication.run(MyApplication.class, args);
       }
   }
   ```

4. **Define Entity Classes**: Create entity classes and annotate them with @Entity, @Table, @Id, etc.

   ```java
   import javax.persistence.Entity;
   import javax.persistence.Id;
   import javax.persistence.Table;

   @Entity
   @Table(name = "users")
   public class User {
       @Id
       private Long id;
       private String name;
       private String email;

       // Getters and setters
   }
   ```

5. **Create Repository Interfaces**: Define repository interfaces extending JpaRepository or CrudRepository.

   ```java
   import org.springframework.data.jpa.repository.JpaRepository;

   public interface UserRepository extends JpaRepository<User, Long> {
       // Custom query methods
   }
   ```

[Back to Top](#table-of-contents)

## What is the use of Dialect and give some examples?

In the context of Hibernate and JPA, a **Dialect** is a configuration setting that allows the ORM framework to generate optimized SQL for a specific relational database. Dialects define the behavior of SQL generation to accommodate differences between various databases.

Use of Dialect:

- **SQL Optimization**: Generates SQL queries optimized for the specific database
- **Compatibility**: Ensures compatibility with different databases by handling differences in SQL syntax and features
- **Customization**: Provides options to customize SQL generation for specific database features

Examples of Dialects:

- **H2 Database Dialect**: `org.hibernate.dialect.H2Dialect`
- **MySQL Dialect**: `org.hibernate.dialect.MySQLDialect`
- **PostgreSQL Dialect**: `org.hibernate.dialect.PostgreSQLDialect`
- **Oracle Dialect**: `org.hibernate.dialect.OracleDialect`
- **SQL Server Dialect**: `org.hibernate.dialect.SQLServerDialect`

How to Set Dialect:

You can specify the dialect in the application.properties or application.yml file:

```properties
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect
```

[Back to Top](#table-of-contents)

## What is the Spring Data JPA repository?

The **Spring Data JPA Repository** is a central component of Spring Data JPA, providing a high-level abstraction for managing data access. It simplifies data access by providing CRUD operations, pagination, sorting, and custom query support.

Key Features:

- **CRUD Operations**: Provides methods for creating, reading, updating, and deleting entities
- **Custom Queries**: Supports custom queries using method names or @Query annotation
- **Pagination and Sorting**: Offers built-in support for pagination and sorting
- **Repository Interfaces**: Allows defining repository interfaces with minimal boilerplate code
- **Type Safety**: Ensures type safety by using generics

Example of a JPA Repository:

```java
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.stereotype.Repository;

@Repository
public interface UserRepository extends JpaRepository<User, Long> {
    User findByEmail(String email);
}
```

[Back to Top](#table-of-contents)

## Explain Mapping Rule in JPA?

Mapping rules in JPA define how Java objects are mapped to database tables and how fields are mapped to columns. These rules are specified using annotations or XML configuration.

Key Mapping Rules:

1. **Entity Mapping**: Use the @Entity annotation to map a class to a database table.
   ```java
   @Entity
   public class User {
       // Fields and methods
   }
   ```

2. **Table Mapping**: Use the @Table annotation to specify the table name.
   ```java
   @Entity
   @Table(name = "users")
   public class User {
       // Fields and methods
   }
   ```

3. **Primary Key Mapping**: Use the @Id annotation to mark the primary key field.
   ```java
   @Id
   private Long id;
   ```

4. **Column Mapping**: Use the @Column annotation to specify column properties.
   ```java
   @Column(name = "email", nullable = false, unique = true)
   private String email;
   ```

5. **Relationship Mapping**: Define relationships between entities using annotations like @OneToOne, @OneToMany, @ManyToOne, and @ManyToMany.
   ```java
   @OneToMany(mappedBy = "user")
   private List<Order> orders;
   ```

6. **Embedded Objects**: Use @Embedded and @Embeddable to map composite objects.
   ```java
   @Embeddable
   public class Address {
       private String street;
       private String city;
   }

   @Embedded
   private Address address;
   ```

[Back to Top](#table-of-contents)

## What is an Entity class and commonly used annotations for this?

An **Entity class** is a lightweight, persistent domain object that represents a table in a relational database. In JPA, an entity is typically a POJO (Plain Old Java Object) that is annotated with JPA annotations to define its mapping to a database table.

Commonly Used Annotations for Entity Classes:

1. **@Entity**: Marks a class as a JPA entity.
   ```java
   @Entity
   public class User {
       // Fields and methods
   }
   ```

2. **@Table**: Specifies the table name and schema.
   ```java
   @Table(name = "users")
   ```

3. **@Id**: Identifies the primary key field.
   ```java
   @Id
   private Long id;
   ```

4. **@GeneratedValue**: Defines the strategy for generating primary key values.
   ```java
   @GeneratedValue(strategy = GenerationType.IDENTITY)
   ```

5. **@Column**: Configures the column properties, such as name, length, and nullability.
   ```java
   @Column(name = "email", nullable = false, unique = true)
   private String email;
   ```

6. **@OneToOne**: Maps a one-to-one relationship.
   ```java
   @OneToOne
   @JoinColumn(name = "address_id")
   private Address address;
   ```

7. **@OneToMany**: Maps a one-to-many relationship.
   ```java
   @OneToMany(mappedBy = "user")
   private List<Order> orders;
   ```

8. **@ManyToOne**: Maps a many-to-one relationship.
   ```java
   @ManyToOne
   @JoinColumn(name = "department_id")
   private Department department;
   ```

9. **@ManyToMany**: Maps a many-to-many relationship.
   ```java
   @ManyToMany
   @JoinTable(
       name = "user_role",
       joinColumns = @JoinColumn(name = "user_id"),
       inverseJoinColumns = @JoinColumn(name = "role_id")
   )
   private Set<Role> roles;
   ```

10. **@Embedded and @Embeddable**: Maps embedded objects.
    ```java
    @Embeddable
    public class Address {
        private String street;
        private String city;
    }

    @Embedded
    private Address address;
    ```

[Back to Top](#table-of-contents)

## What is the difference between JPA and Hibernate?

JPA (Java Persistence API) and Hibernate are both used for ORM in Java, but they have some key differences:

| Aspect | JPA | Hibernate |
|--------|-----|-----------|
| **Type** | Specification | Implementation |
| **API** | Standardized API | Proprietary API |
| **Vendor** | Java EE Specification | Red Hat/JBoss |
| **Flexibility** | Allows switching between implementations | Tightly coupled with its own features |
| **Features** | Basic ORM features | Advanced features (e.g., caching, filters) |
| **Query Language** | JPQL | HQL |
| **XML Mapping** | Supported but not recommended | Supported and extensively used |
| **Annotations** | JPA annotations (standardized) | Hibernate-specific annotations (proprietary) |

**Usage**:
- **JPA**: Use JPA when you need a standardized API and the flexibility to switch between different ORM implementations.
- **Hibernate**: Use Hibernate when you need advanced features and are willing to work with its specific API and annotations.

[Back to Top](#table-of-contents)

## How can we create a custom repository in Spring Data JPA?

Creating a custom repository in Spring Data JPA involves defining additional methods in a repository interface and implementing those methods in a custom repository class.

Steps to Create a Custom Repository:

1. **Define a Custom Repository Interface**: Create an interface that declares custom methods.
   ```java
   public interface CustomUserRepository {
       List<User> findUsersByCustomCriteria(String criteria);
   }
   ```

2. **Implement the Custom Repository Interface**: Create a class that implements the custom repository interface and provides the implementation for the custom methods.
   ```java
   import javax.persistence.EntityManager;
   import javax.persistence.PersistenceContext;
   import javax.persistence.TypedQuery;

   public class CustomUserRepositoryImpl implements CustomUserRepository {

       @PersistenceContext
       private EntityManager entityManager;

       @Override
       public List<User> findUsersByCustomCriteria(String criteria) {
           String queryString = "SELECT u FROM User u WHERE u.name LIKE :criteria";
           TypedQuery<User> query = entityManager.createQuery(queryString, User.class);
           query.setParameter("criteria", "%" + criteria + "%");
           return query.getResultList();
       }
   }
   ```

3. **Extend the Custom Repository Interface**: In your main repository interface, extend the custom repository interface along with JpaRepository or CrudRepository.
   ```java
   import org.springframework.data.jpa.repository.JpaRepository;

   public interface UserRepository extends JpaRepository<User, Long>, CustomUserRepository {
       // Custom query methods
   }
   ```

4. **Spring Boot Configuration**: Ensure that Spring Boot is configured to detect the custom implementation. By convention, Spring Data JPA looks for a class with the same name as the interface suffixed with `Impl`.

   No additional configuration is needed if the naming convention is followed. If not, configure the custom implementation using @EnableJpaRepositories:
   ```java
   import org.springframework.context.annotation.Configuration;
   import org.springframework.data.jpa.repository.config.EnableJpaRepositories;

   @Configuration
   @EnableJpaRepositories(repositoryBaseClass = CustomUserRepositoryImpl.class)
   public class JpaConfig {
       // Configuration code
   }
   ```

[Back to Top](#table-of-contents)

## What are pre-defined methods given by Repository interfaces?

Spring Data JPA provides several predefined methods in its repository interfaces to perform common database operations. These methods are part of the CrudRepository, JpaRepository, and other repository interfaces.

Common Pre-defined Methods:

**CrudRepository**:
- `save(S entity)`: Saves an entity
- `saveAll(Iterable<S> entities)`: Saves multiple entities
- `findById(ID id)`: Finds an entity by its ID
- `existsById(ID id)`: Checks if an entity exists by its ID
- `findAll()`: Retrieves all entities
- `findAllById(Iterable<ID> ids)`: Retrieves entities by their IDs
- `count()`: Counts the number of entities
- `deleteById(ID id)`: Deletes an entity by its ID
- `delete(T entity)`: Deletes an entity
- `deleteAll(Iterable<? extends T> entities)`: Deletes multiple entities
- `deleteAll()`: Deletes all entities

**JpaRepository** (extends CrudRepository):
- `flush()`: Flushes changes to the database
- `saveAndFlush(S entity)`: Saves an entity and flushes changes immediately
- `deleteInBatch(Iterable<T> entities)`: Deletes entities in batch mode
- `deleteAllInBatch()`: Deletes all entities in batch mode
- `getOne(ID id)`: Returns a reference to an entity by its ID

**PagingAndSortingRepository**:
- `findAll(Sort sort)`: Retrieves all entities sorted by the given sort criteria
- `findAll(Pageable pageable)`: Retrieves entities in a paginated format

[Back to Top](#table-of-contents)

## Differentiate between findById() and getOne()?

`findById()` and `getOne()` are methods provided by Spring Data JPA for retrieving entities, but they have different behaviors:

**findById()**:
- **Return Type**: `Optional<T>`
- **Behavior**: Performs a database query to retrieve the entity immediately
- **Null Safety**: Returns an Optional to handle null values safely
- **Usage**: Suitable for cases where you need to check for the presence of an entity

**getOne()**:
- **Return Type**: `T`
- **Behavior**: Returns a proxy object and does not perform a database query immediately. The actual query is executed when the entity is accessed
- **Lazy Loading**: Useful for scenarios where lazy loading is desired
- **Exception**: Throws EntityNotFoundException if the entity does not exist when accessed

Example:
```java
// findById()
Optional<User> userOpt = userRepository.findById(1L);
userOpt.ifPresent(user -> {
    System.out.println(user.getName());
});

// getOne()
User user = userRepository.getOne(1L);
System.out.println(user.getName()); // Executes the query if the entity is accessed
```

[Back to Top](#table-of-contents)

## What is the naming convention for finder methods in the Spring Data repository interface?

Spring Data JPA provides a convention-based approach to define finder methods in repository interfaces. The method names are parsed by Spring Data to generate queries automatically.

Naming Convention:

- **Prefix**: Method names typically start with a prefix like `findBy`, `readBy`, `queryBy`, `getBy`, or `searchBy`
- **Property Name**: Follow the prefix with the property name of the entity (e.g., `findByName`)
- **Logical Operators**: Use logical operators like `And`, `Or` to combine multiple criteria (e.g., `findByFirstNameAndLastName`)
- **Comparison Keywords**: Use keywords like `LessThan`, `GreaterThan`, `Like`, `Between`, etc., for comparisons (e.g., `findByAgeGreaterThan`)

Example Finder Methods:

```java
// Find by single property
User findByEmail(String email);

// Find by multiple properties
List<User> findByFirstNameAndLastName(String firstName, String lastName);

// Find by comparison
List<User> findByAgeGreaterThan(int age);

// Find by like
List<User> findByNameLike(String namePattern);

// Find by between
List<User> findByCreatedDateBetween(LocalDate startDate, LocalDate endDate);
```

[Back to Top](#table-of-contents)

## What is the difference between PagingAndSorting Repository and JpaRepository?

Both PagingAndSortingRepository and JpaRepository are part of the Spring Data JPA repository hierarchy, but they offer different functionalities.

**PagingAndSortingRepository**:
- **Purpose**: Provides methods for pagination and sorting
- **Key Methods**: Includes `findAll(Sort sort)` and `findAll(Pageable pageable)` for pagination and sorting
- **Use Case**: Suitable for applications requiring basic CRUD operations with pagination and sorting

**JpaRepository**:
- **Purpose**: Extends PagingAndSortingRepository and provides additional JPA-specific operations
- **Key Methods**: Includes methods like `flush()`, `saveAndFlush()`, `deleteInBatch()`, and `getOne()`
- **Use Case**: Suitable for applications requiring advanced JPA operations along with pagination and sorting

Comparison:

| Feature | PagingAndSortingRepository | JpaRepository |
|---------|----------------------------|--------------|
| **Pagination** | Yes | Yes |
| **Sorting** | Yes | Yes |
| **Flush** | No | Yes (e.g., `flush()`, `saveAndFlush()`) |
| **Batch Delete** | No | Yes (e.g., `deleteInBatch()`, `deleteAllInBatch()`) |
| **JPA Operations** | Basic | Advanced (e.g., `getOne()`) |

[Back to Top](#table-of-contents)

## What is PagingAndSorting Repository?

**PagingAndSortingRepository** is an interface provided by Spring Data JPA that extends CrudRepository and adds methods for pagination and sorting.

Key Features:
- **Pagination**: Supports paginated data retrieval using the Pageable interface
- **Sorting**: Supports sorting data retrieval using the Sort class
- **CRUD Operations**: Inherits basic CRUD operations from CrudRepository

Common Methods:
- `Page<T> findAll(Pageable pageable)`: Retrieves entities in a paginated format
- `Iterable<T> findAll(Sort sort)`: Retrieves all entities sorted by the given criteria
- `Page<T> findAll(Specification<T> spec, Pageable pageable)`: Retrieves entities using specifications with pagination

Example Usage:

```java
import org.springframework.data.domain.Page;
import org.springframework.data.domain.PageRequest;
import org.springframework.data.domain.Pageable;
import org.springframework.data.domain.Sort;
import org.springframework.data.repository.PagingAndSortingRepository;

public interface UserRepository extends PagingAndSortingRepository<User, Long> {
    // Custom query methods
}

// Usage in a service
@Service
public class UserService {

    @Autowired
    private UserRepository userRepository;

    public Page<User> getUsers(int page, int size) {
        Pageable pageable = PageRequest.of(page, size, Sort.by("name").ascending());
        return userRepository.findAll(pageable);
    }
}
```

[Back to Top](#table-of-contents)

## What is @Query used for?

The **@Query** annotation in Spring Data JPA is used to define custom queries directly in repository interfaces. It allows you to specify JPQL (Java Persistence Query Language) or native SQL queries.

Key Features:
- **Custom Queries**: Supports defining custom JPQL or SQL queries
- **Dynamic Parameters**: Allows parameter binding using named or positional parameters
- **Flexible**: Provides flexibility in writing complex queries not possible with method names

Example Usage:

```java
import org.springframework.data.jpa.repository.Query;
import org.springframework.data.repository.query.Param;

public interface UserRepository extends JpaRepository<User, Long> {

    // Using JPQL
    @Query("SELECT u FROM User u WHERE u.email = :email")
    User findByEmail(@Param("email") String email);

    // Using native SQL
    @Query(value = "SELECT * FROM users WHERE email = ?1", nativeQuery = true)
    User findByEmailNative(String email);
}
```

[Back to Top](#table-of-contents)

## What type of Queries can be implemented using @Query annotation?

The @Query annotation can be used to implement the following types of queries:

1. **JPQL Queries**: Java Persistence Query Language, an object-oriented query language similar to SQL.
   ```java
   @Query("SELECT u FROM User u WHERE u.name = :name")
   List<User> findByName(@Param("name") String name);
   ```

2. **Native SQL Queries**: Raw SQL queries executed directly against the database.
   ```java
   @Query(value = "SELECT * FROM users WHERE name = ?1", nativeQuery = true)
   List<User> findByNameNative(String name);
   ```

3. **Named Queries**: Predefined queries associated with entity classes.
   ```java
   @NamedQuery(name = "User.findByName", query = "SELECT u FROM User u WHERE u.name = :name")
   ```

4. **Dynamic Queries**: Queries with dynamic parameters using SpEL (Spring Expression Language).
   ```java
   @Query("SELECT u FROM User u WHERE u.name = ?#{[0]}")
   List<User> findByNameDynamic(String name);
   ```

[Back to Top](#table-of-contents)

## Give an example of using @Query annotation with JPQL?

Here's an example of using the @Query annotation with JPQL to retrieve users based on specific criteria:

```java
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.data.jpa.repository.Query;
import org.springframework.data.repository.query.Param;

public interface UserRepository extends JpaRepository<User, Long> {

    // JPQL query to find users by age greater than a specified value
    @Query("SELECT u FROM User u WHERE u.age > :age")
    List<User> findUsersByAgeGreaterThan(@Param("age") int age);

    // JPQL query to find users by first name and last name
    @Query("SELECT u FROM User u WHERE u.firstName = :firstName AND u.lastName = :lastName")
    List<User> findUsersByFullName(@Param("firstName") String firstName, @Param("lastName") String lastName);
}
```

Usage in a Service:

```java
@Service
public class UserService {

    @Autowired
    private UserRepository userRepository;

    public List<User> getUsersByAge(int age) {
        return userRepository.findUsersByAgeGreaterThan(age);
    }

    public List<User> getUsersByFullName(String firstName, String lastName) {
        return userRepository.findUsersByFullName(firstName, lastName);
    }
}
```

[Back to Top](#table-of-contents)

## What are Collection Mappings Supported by JPA?

JPA supports mapping collections of entities and value types to relational database tables. The primary collection mappings include:

1. **One-to-Many**: Maps a collection of entities with a @OneToMany relationship.
   ```java
   @OneToMany(mappedBy = "user")
   private List<Order> orders;
   ```

2. **Many-to-Many**: Maps a collection of entities with a @ManyToMany relationship.
   ```java
   @ManyToMany
   @JoinTable(
       name = "user_role",
       joinColumns = @JoinColumn(name = "user_id"),
       inverseJoinColumns = @JoinColumn(name = "role_id")
   )
   private Set<Role> roles;
   ```

3. **Element Collection**: Maps a collection of basic or embeddable types.
   ```java
   @ElementCollection
   @CollectionTable(name = "user_phone_numbers", joinColumns = @JoinColumn(name = "user_id"))
   @Column(name = "phone_number")
   private Set<String> phoneNumbers;
   ```

Collection Types Supported:
- **List**: Ordered collection, mapped to a database table with a foreign key
- **Set**: Unordered collection, mapped to a database table with a foreign key
- **Map**: Collection of key-value pairs, mapped to a database table with additional columns for keys

[Back to Top](#table-of-contents)


## What are different types of Joins supported by JPA?

JPA supports various join types to fetch data from multiple related tables. The primary types include:

- **Inner Join**: Fetches records with matching values in both tables
- **Left Join** (Left Outer Join): Fetches all records from the left table and matching records from the right table
- **Right Join** (Right Outer Join): Fetches all records from the right table and matching records from the left table
- **Full Join** (Full Outer Join): Fetches all records when there is a match in either left or right table

### SQL and JPQL/HQL Joins Syntax Examples:

#### Inner Join:

SQL:
```sql
SELECT u.name, o.order_id
FROM users u
INNER JOIN orders o ON u.id = o.user_id;
```

JPQL:
```java
@Query("SELECT u FROM User u JOIN u.orders o WHERE o.status = :status")
List<User> findUsersWithOrders(@Param("status") String status);
```

#### Left Join:

SQL:
```sql
SELECT u.name, o.order_id
FROM users u
LEFT JOIN orders o ON u.id = o.user_id;
```

JPQL:
```java
@Query("SELECT u FROM User u LEFT JOIN u.orders o WHERE o.status = :status")
List<User> findUsersWithOrders(@Param("status") String status);
```

#### Right Join:

SQL:
```sql
SELECT u.name, o.order_id
FROM users u
RIGHT JOIN orders o ON u.id = o.user_id;
```

JPQL:
```java
@Query("SELECT u FROM User u RIGHT JOIN u.orders o WHERE o.status = :status")
List<User> findUsersWithOrders(@Param("status") String status);
```

#### Full Join:

SQL:
```sql
SELECT u.name, o.order_id
FROM users u
FULL JOIN orders o ON u.id = o.user_id;
```

JPQL (Full join is not directly supported, emulated with left join and union):
```java
@Query("SELECT u FROM User u LEFT JOIN u.orders o WHERE o.status = :status " +
       "UNION SELECT u FROM User u RIGHT JOIN u.orders o WHERE o.status = :status")
List<User> findUsersWithOrders(@Param("status") String status);
```

[Back to Top](#table-of-contents)

## What is @EntityGraph in Spring Data JPA?

**@EntityGraph** is a Spring Data JPA annotation used to specify a graph of entities to be fetched eagerly. It allows you to define which related entities should be loaded along with the main entity, reducing the number of queries needed.

### Key Features:

- **Eager Loading**: Fetches related entities eagerly, avoiding the N+1 problem
- **Custom Fetching**: Allows custom fetching strategies for specific queries
- **Named Entity Graphs**: Supports defining named entity graphs for reuse

### Example Usage:

```java
import javax.persistence.EntityGraph;
import org.springframework.data.jpa.repository.EntityGraph;
import org.springframework.data.jpa.repository.JpaRepository;

public interface UserRepository extends JpaRepository<User, Long> {

    // Using @EntityGraph to fetch orders along with users
    @EntityGraph(attributePaths = {"orders"})
    List<User> findAllWithOrders();
}
```

### Defining Named Entity Graphs:

```java
import javax.persistence.Entity;
import javax.persistence.NamedAttributeNode;
import javax.persistence.NamedEntityGraph;

@Entity
@NamedEntityGraph(
    name = "User.orders",
    attributeNodes = @NamedAttributeNode("orders")
)
public class User {
    // Fields and methods
}
```

### Using Named Entity Graphs:

```java
import org.springframework.data.jpa.repository.EntityGraph;

public interface UserRepository extends JpaRepository<User, Long> {

    // Using named entity graph
    @EntityGraph(value = "User.orders", type = EntityGraph.EntityGraphType.LOAD)
    List<User> findAllWithOrders();
}
```

[Back to Top](#table-of-contents)

## What is the Criteria API?

The **Criteria API** is a feature of JPA that provides a type-safe, programmatic way to create dynamic queries. It is useful for building complex queries at runtime and allows developers to construct queries using Java objects and methods.

### Key Features:

- **Type Safety**: Provides a type-safe way to construct queries
- **Dynamic Queries**: Allows building dynamic queries based on runtime conditions
- **Programmatic Approach**: Uses Java objects and methods to build queries

### Components:

- **CriteriaBuilder**: The factory class for building Criteria queries
- **CriteriaQuery**: Represents a query object created using the Criteria API
- **Root**: Represents the root entity in the query
- **Predicate**: Represents conditions in the query

### Example Usage:

```java
import javax.persistence.criteria.CriteriaBuilder;
import javax.persistence.criteria.CriteriaQuery;
import javax.persistence.criteria.Predicate;
import javax.persistence.criteria.Root;
import org.springframework.stereotype.Repository;
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;

@Repository
public class UserRepositoryCustom {

    @PersistenceContext
    private EntityManager entityManager;

    public List<User> findUsersByAgeAndName(int age, String name) {
        CriteriaBuilder criteriaBuilder = entityManager.getCriteriaBuilder();
        CriteriaQuery<User> criteriaQuery = criteriaBuilder.createQuery(User.class);
        Root<User> userRoot = criteriaQuery.from(User.class);

        Predicate agePredicate = criteriaBuilder.greaterThan(userRoot.get("age"), age);
        Predicate namePredicate = criteriaBuilder.equal(userRoot.get("name"), name);

        criteriaQuery.where(criteriaBuilder.and(agePredicate, namePredicate));

        return entityManager.createQuery(criteriaQuery).getResultList();
    }
}
```

### Advantages of Criteria API:

- **Type Safety**: Prevents syntax errors at runtime by leveraging compile-time checks
- **Dynamic Querying**: Enables building queries dynamically based on application logic
- **Readability**: Offers a more readable and maintainable approach compared to concatenating strings in JPQL

[Back to Top](#table-of-contents)

## What is the use of an Entity Manager?

The **Entity Manager** is the primary interface in JPA for interacting with the persistence context. It is responsible for managing the lifecycle of entities, executing queries, and synchronizing changes with the database.

### Key Responsibilities:

- **Persisting Entities**: Manages entity states (transient, persistent, detached, removed)
- **Query Execution**: Provides methods for executing JPQL and native SQL queries
- **Transaction Management**: Coordinates with the transaction manager to handle transactions
- **Caching**: Maintains a cache of managed entities for improved performance

### Common Methods:

- **persist(Object entity)**: Persists a new entity to the database
- **merge(Object entity)**: Merges changes to a detached entity back into the persistence context
- **remove(Object entity)**: Removes an entity from the database
- **find(Class<T> entityClass, Object primaryKey)**: Finds an entity by its primary key
- **createQuery(String query)**: Creates a query object for executing JPQL queries
- **createNativeQuery(String query)**: Creates a query object for executing native SQL queries

### Example Usage:

```java
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import org.springframework.stereotype.Repository;

@Repository
public class UserRepository {

    @PersistenceContext
    private EntityManager entityManager;

    public void saveUser(User user) {
        entityManager.persist(user);
    }

    public User findUserById(Long id) {
        return entityManager.find(User.class, id);
    }

    public void deleteUser(User user) {
        entityManager.remove(user);
    }
}
```

### Entity States:

- **Transient**: The entity is not associated with a persistence context
- **Persistent**: The entity is managed by the persistence context
- **Detached**: The entity is no longer managed by the persistence context
- **Removed**: The entity is scheduled for removal from the database

[Back to Top](#table-of-contents)