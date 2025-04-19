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
### Additional Resources

If you found this guide helpful, you might also be interested in my other Spring Framework resources:
- [Core Java & Java-8 Interview Questions](https://github.com/anilvn/Java-Interview-Questions/tree/main)
- [Spring Boot Interview Questions](https://github.com/anilvn/spring-boot-interview-questions/tree/main)
- [Microservices with Spring Cloud Tutorials](https://javatechonline.com/microservices-tutorial/)

Feel free to star and fork these repositories if you find them useful!

---

## Table of Contents

| # | Question | 
|---|----------|
| 1 | [What is the Spring Web Module?](#what-is-the-spring-web-module) |
| 2 | [What is REST and RESTful?](#what-is-rest-and-restful) |
| 3 | [What is a REST Resource?](#what-is-a-rest-resource) |
| 4 | [What is URI?](#what-is-uri) |
| 5 | [What are the features of RESTful Web Services?](#what-are-the-features-of-restful-web-services) |
| 6 | [What is the concept of statelessness in REST?](#what-is-the-concept-of-statelessness-in-rest) |
| 7 | [What are the HTTP Methods?](#what-are-the-http-methods) |
| 8 | [What are Annotations for HTTP request methods?](#what-are-annotations-for-http-request-methods) |
| 9 | [What are the @RequestBody and @ResponseBody Annotations?](#what-are-the-requestbody-and-responsebody-annotations) |
| 10 | [What is the purpose of @PathVariable Annotation?](#what-is-the-purpose-of-pathvariable-annotation) |
| 11 | [Explain @PathVariable and @RequestParam Annotations](#explain-pathvariable-and-requestparam-annotations) |
| 12 | [What is the role of @ResponseBody Annotation?](#what-is-the-role-of-responsebody-annotation) |
| 13 | [What is ResponseEntity\<T\> in Spring REST?](#what-is-responseentityt-in-spring-rest) |
| 14 | [Why is @RequestHeader used in Spring Web?](#why-is-requestheader-used-in-spring-web) |
| 15 | [How to map controller class and its methods with URL?](#how-to-map-controller-class-and-its-methods-with-url) |
| 16 | [What are the common HTTP Response Status Codes?](#what-are-the-common-http-response-status-codes) |
| 17 | [What is the cross-origin concept in Spring Web?](#what-is-the-cross-origin-concept-in-spring-web) |
| 18 | [How many types of input are getting from clients?](#how-many-types-of-input-are-getting-from-clients) |
| 19 | [What is PathVariable and RequestParam in Spring Boot?](#what-is-pathvariable-and-requestparam-in-spring-boot) |

## What is the Spring Web Module?

The Spring Web Module is a part of the Spring Framework that provides comprehensive support for web-based application development. It includes features for building both web MVC applications and RESTful web services.

### Key Features:
- **Spring MVC**: Implements the Model-View-Controller (MVC) design pattern for building web applications.
- **REST Support**: Provides built-in support for creating RESTful services using annotations and serialization/deserialization of data.
- **View Technologies**: Supports various view technologies like JSP, Thymeleaf, FreeMarker, etc.
- **Internationalization (i18n)**: Supports internationalization for developing applications in multiple languages.
- **Validation**: Provides built-in validation support using JSR-303/JSR-380 (Bean Validation) and custom validators.
- **Multipart File Upload**: Supports file uploads and processing through MultipartResolver.
- **Error Handling**: Provides mechanisms for exception handling and custom error pages.

### Example Structure:
- **Controllers**: Classes annotated with `@Controller` or `@RestController` to handle HTTP requests.
- **Views**: Templates or JSPs that render the UI.
- **Models**: POJOs (Plain Old Java Objects) that hold data passed between controllers and views.

[Back to Top](#table-of-contents)

## What is REST and RESTful?

REST (Representational State Transfer) is an architectural style for designing networked applications. REST uses a stateless, client-server, cacheable communications protocol, typically HTTP, and is based on resources identified by URIs (Uniform Resource Identifiers).

### Key Concepts of REST:
- **Stateless**: Each request from the client contains all the information needed by the server to fulfill the request.
- **Resource-Based**: Interactions are based on resources, which are represented by URIs.
- **HTTP Methods**: Uses HTTP methods explicitly (GET, POST, PUT, DELETE, etc.) for performing CRUD operations on resources.
- **Uniform Interface**: Provides a standardized way to access resources.
- **Representation-Oriented**: Resources are represented in formats like JSON, XML, HTML, etc.

RESTful Web Services are services that implement REST principles. They expose resources via URIs and provide a uniform interface for accessing and manipulating these resources.

[Back to Top](#table-of-contents)

## What is a REST Resource?

A REST Resource is an object or representation of data that can be accessed and manipulated via RESTful web services. Each resource is identified by a URI and can have different representations, such as JSON, XML, or HTML.

### Key Characteristics:
- **Identified by URIs**: Each resource is uniquely identified by a URI (e.g., `/users/1`).
- **Representation-Oriented**: Resources can be represented in multiple formats (JSON, XML, etc.).
- **State Transfer**: REST allows clients to modify the state of resources through HTTP methods.

### Example Resource:
Consider a resource representing a user in a system:
- **URI**: `/users/{id}`
- **Representation**: JSON or XML
- **HTTP Methods**:
  - **GET**: Retrieve the user.
  - **POST**: Create a new user.
  - **PUT**: Update an existing user.
  - **DELETE**: Remove a user.

[Back to Top](#table-of-contents)

## What is URI?

A URI (Uniform Resource Identifier) is a string of characters used to identify a resource on a network. URIs provide a standard way to access resources in RESTful services.

### Types of URI:
- **URL (Uniform Resource Locator)**: Specifies the location of a resource and how to access it.
- **URN (Uniform Resource Name)**: Specifies a resource's name within a namespace.

### URI Components:
- **Scheme**: Indicates the protocol (e.g., http, https).
- **Authority**: Contains the domain name or IP address (e.g., example.com).
- **Path**: Specifies the resource's location on the server (e.g., `/users/1`).
- **Query**: Contains additional parameters (e.g., `?page=1`).
- **Fragment**: Identifies a specific part of the resource (e.g., `#section2`).

### Example URI:
```
http://example.com/users/1
```

- **Scheme**: http
- **Authority**: example.com
- **Path**: /users/1

[Back to Top](#table-of-contents)

## What are the features of RESTful Web Services?

RESTful Web Services provide a set of features that enable the development of scalable and flexible web services.

### Key Features:
- **Statelessness**: Each request is independent, and the server does not store client state.
- **Cacheability**: Responses can be cached to improve performance.
- **Layered System**: Supports a layered architecture where intermediaries can improve scalability and security.
- **Uniform Interface**: Provides a consistent way to interact with resources using standard HTTP methods.
- **Resource-Based**: Exposes resources via URIs and supports multiple representations.
- **Client-Server Architecture**: Separates client and server concerns, allowing independent development.
- **Code on Demand (Optional)**: Servers can provide executable code to clients (e.g., JavaScript).

### Example RESTful Service:
A RESTful service for managing users might have the following endpoints:
- **GET /users**: Retrieve a list of users.
- **POST /users**: Create a new user.
- **GET /users/{id}**: Retrieve a specific user.
- **PUT /users/{id}**: Update a specific user.
- **DELETE /users/{id}**: Remove a specific user.

[Back to Top](#table-of-contents)

## What is the concept of statelessness in REST?

Statelessness is a fundamental principle of REST architecture, where each HTTP request from a client to a server must contain all the information needed to understand and process the request.

### Key Aspects:
- **No Client Context**: The server does not store any client context between requests.
- **Self-Contained Requests**: Each request is independent and self-contained.
- **Improved Scalability**: Statelessness allows servers to handle requests independently, improving scalability.
- **Simplified Server Design**: Servers do not need to manage session state, simplifying design and implementation.

### Implications:
- **State Management**: Any stateful information must be stored on the client and passed to the server with each request (e.g., using cookies, query parameters, or headers).
- **Session Data**: Session data can be maintained on the client side or in external storage like databases or cache systems.

### Example:
When a client requests a specific user resource, it must include all necessary authentication and state information in the request:
```
GET /users/1 HTTP/1.1
Host: example.com
Authorization: Bearer <token>
```

[Back to Top](#table-of-contents)

## What are the HTTP Methods?

HTTP methods are standardized actions used to perform operations on resources in RESTful web services. They correspond to CRUD (Create, Read, Update, Delete) operations.

### Common HTTP Methods:
- **GET**: Retrieve a resource or a list of resources. It is safe and idempotent.
  - Example: `GET /users`
- **POST**: Create a new resource. It is not idempotent.
  - Example: `POST /users`
- **PUT**: Update an existing resource or create a new resource if it does not exist. It is idempotent.
  - Example: `PUT /users/1`
- **DELETE**: Remove a resource. It is idempotent.
  - Example: `DELETE /users/1`
- **PATCH**: Partially update an existing resource. It is not idempotent.
  - Example: `PATCH /users/1`
- **HEAD**: Retrieve metadata about a resource. It is safe and idempotent.
  - Example: `HEAD /users`
- **OPTIONS**: Retrieve supported HTTP methods for a resource.
  - Example: `OPTIONS /users`

### Safety and Idempotency:
- **Safe Methods**: Methods that do not modify resources (e.g., GET, HEAD).
- **Idempotent Methods**: Methods that have the same result regardless of the number of times they are called (e.g., GET, PUT, DELETE).

[Back to Top](#table-of-contents)

## What are Annotations for HTTP request methods?

Spring provides a set of annotations for mapping HTTP requests to controller methods. These annotations simplify the process of handling requests and implementing RESTful services.

### Common Annotations:
- **@RequestMapping**: General-purpose request handling annotation.
- **@GetMapping**: Shortcut for `@RequestMapping(method = RequestMethod.GET)`.
- **@PostMapping**: Shortcut for `@RequestMapping(method = RequestMethod.POST)`.
- **@PutMapping**: Shortcut for `@RequestMapping(method = RequestMethod.PUT)`.
- **@DeleteMapping**: Shortcut for `@RequestMapping(method = RequestMethod.DELETE)`.
- **@PatchMapping**: Shortcut for `@RequestMapping(method = RequestMethod.PATCH)`.

[Back to Top](#table-of-contents)

## What are the @RequestBody and @ResponseBody Annotations?

The `@RequestBody` and `@ResponseBody` annotations are used in Spring MVC to bind HTTP request and response bodies to and from Java objects.

### @RequestBody:
- **Purpose**: Binds the HTTP request body to a method parameter.
- **Serialization**: Automatically deserializes JSON or XML input to a Java object.
- **Usage**: Typically used in POST, PUT, and PATCH methods.

```java
@PostMapping("/users")
public ResponseEntity<User> createUser(@RequestBody User user) {
    // Logic to create a user
}
```

### @ResponseBody:
- **Purpose**: Binds the method return value to the HTTP response body.
- **Serialization**: Automatically serializes the return value to JSON or XML.
- **Usage**: Typically used in RESTful services to return data.

```java
@GetMapping("/users/{id}")
@ResponseBody
public User getUserById(@PathVariable Long id) {
    // Logic to retrieve a user
}
```

### With @RestController:
If a controller is annotated with `@RestController`, all methods automatically use `@ResponseBody`, eliminating the need to specify it for each method.

```java
@RestController
@RequestMapping("/users")
public class UserController {
    @GetMapping("/{id}")
    public User getUserById(@PathVariable Long id) {
        // Logic to retrieve a user
    }
}
```

[Back to Top](#table-of-contents)

## What is the purpose of @PathVariable Annotation?

The `@PathVariable` annotation is used in Spring MVC to bind a URI template variable to a method parameter.

### Key Features:
- **URI Template Variables**: Binds variables in the URI path to method parameters.
- **Type Conversion**: Automatically converts URI variables to the specified method parameter type.
- **Ease of Use**: Simplifies extraction of values from URIs for use in method logic.

### Example Usage:
Consider a URI with a variable path segment:

```java
@GetMapping("/users/{id}")
public User getUserById(@PathVariable Long id) {
    // Logic to retrieve a user
}
```

- **URI**: `/users/123`
- **@PathVariable**: Binds 123 to the id parameter.

### Multiple Path Variables:

```java
@GetMapping("/users/{userId}/orders/{orderId}")
public Order getOrderForUser(@PathVariable Long userId, @PathVariable Long orderId) {
    // Logic to retrieve an order for a user
}
```

- **URI**: `/users/123/orders/456`
- **Path Variables**: Binds 123 to userId and 456 to orderId.

[Back to Top](#table-of-contents)

## Explain @PathVariable and @RequestParam Annotations

The `@PathVariable` and `@RequestParam` annotations are used in Spring MVC to bind request parameters to method parameters.

### @PathVariable:
- **Purpose**: Binds URI template variables to method parameters.
- **Usage**: Extracts values from the URI path.

```java
@GetMapping("/users/{id}")
public User getUserById(@PathVariable Long id) {
    // Logic to retrieve a user
}
```

### @RequestParam:
- **Purpose**: Binds query parameters or form data to method parameters.
- **Usage**: Extracts values from the query string or form data.

```java
@GetMapping("/users")
public List<User> getUsersByAge(@RequestParam int age) {
    // Logic to retrieve users by age
}
```

### Differences:
- **Path Variable**:
  - Used for extracting values from the URI path.
  - Typically used in RESTful APIs to identify resources.
- **Request Parameter**:
  - Used for extracting values from the query string or form data.
  - Typically used for filtering, sorting, or pagination.

### Example:
Consider a URI with both path and query parameters:

```
GET /users/123?age=30
```

- **@PathVariable**: Extracts 123 from the path.
- **@RequestParam**: Extracts 30 from the query string.

```java
@GetMapping("/users/{id}")
public User getUserByIdAndAge(@PathVariable Long id, @RequestParam int age) {
    // Logic to retrieve a user by ID and age
}
```

### Optional Parameters:
```java
@GetMapping("/users")
public List<User> getUsersByAge(@RequestParam(required=false) Integer age, @RequestParam(defaultValue="2") int page) {
    // Logic to retrieve users by age with pagination
}
```

[Back to Top](#table-of-contents)

## What is the role of @ResponseBody Annotation?

The `@ResponseBody` annotation in Spring MVC is used to bind the method return value to the HTTP response body.

### Key Features:
- **Serialization**: Automatically converts the return value to a specified format (e.g., JSON, XML).
- **RESTful Support**: Facilitates returning data in RESTful services.
- **Integration with HttpMessageConverters**: Uses converters to serialize the return value.

### Example Usage:

```java
@GetMapping("/users/{id}")
@ResponseBody
public User getUserById(@PathVariable Long id) {
    // Logic to retrieve a user
}
```

- **Serialization**: The User object is automatically serialized to JSON or XML based on the Accept header in the request.

### With @RestController:
- **Automatic Application**: If a controller is annotated with `@RestController`, all methods automatically use `@ResponseBody`.

```java
@RestController
@RequestMapping("/users")
public class UserController {
    @GetMapping("/{id}")
    public User getUserById(@PathVariable Long id) {
        // Logic to retrieve a user
    }
}
```

### Usage in RESTful Services:
- **Data Return**: Simplifies returning data objects from controller methods without explicitly specifying `@ResponseBody` for each method.

[Back to Top](#table-of-contents)

## What is ResponseEntity\<T\> in Spring REST?

`ResponseEntity<T>` is a Spring MVC class that represents an HTTP response, including headers, status code, and body. It is used to provide more control over the HTTP response returned by a RESTful service.

### Key Features:
- **Custom Headers**: Allows setting custom HTTP headers.
- **Status Code**: Enables specifying HTTP status codes.
- **Body Content**: Contains the response body content.

### Example Usage:

```java
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class UserController {

    @GetMapping("/users/{id}")
    public ResponseEntity<User> getUserById(@PathVariable Long id) {
        User user = userService.findUserById(id);

        if (user != null) {
            return ResponseEntity.ok(user); // 200 OK
        } else {
            return ResponseEntity.notFound().build(); // 404 Not Found
        }
    }
}
```

### Advantages of ResponseEntity:
- **Status Control**: Provides precise control over the HTTP status code returned.
- **Headers**: Allows setting and manipulating HTTP headers.
- **Flexible Responses**: Supports returning different responses based on application logic.

### Common Methods:
- **ResponseEntity.ok(T body)**: Returns a 200 OK response with a body.
- **ResponseEntity.notFound()**: Returns a 404 Not Found response.
- **ResponseEntity.badRequest()**: Returns a 400 Bad Request response.
- **ResponseEntity.status(HttpStatus status)**: Sets a specific HTTP status.

[Back to Top](#table-of-contents)

## Why is @RequestHeader used in Spring Web?

The `@RequestHeader` annotation in Spring MVC is used to bind HTTP request headers to method parameters.

### Key Features:
- **Header Binding**: Binds request headers to method parameters.
- **Type Conversion**: Automatically converts header values to the specified method parameter type.
- **Optional Headers**: Supports specifying default values for optional headers.

### Example Usage:
```java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestHeader;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class UserController {

    @GetMapping("/greeting")
    public String greetUser(@RequestHeader("User-Agent") String userAgent) {
        return "Hello, your user agent is: " + userAgent;
    }
}
```

- **Header Extraction**: Extracts the User-Agent header value from the request.

### Multiple Headers:
```java
@GetMapping("/greeting")
public String greetUser(@RequestHeader("User-Agent") String userAgent, 
                        @RequestHeader(value = "Accept-Language", defaultValue = "en") String language) {
    return "Hello, your user agent is: " + userAgent + " and your language is: " + language;
}
```

- **Default Values**: Specifies a default value for optional headers.

### Usage Scenarios:
- **Custom Headers**: Extract custom headers for security, localization, etc.
- **Metadata**: Access metadata about the request, such as User-Agent or Accept-Language.

[Back to Top](#table-of-contents)

## How to map controller class and its methods with URL?

Mapping controller classes and methods to URLs in Spring MVC involves using annotations to define request mappings.

### Key Annotations:
- **@RequestMapping**: Maps URLs to controller classes and methods.
- **@GetMapping, @PostMapping, @PutMapping, @DeleteMapping**: Specialized annotations for specific HTTP methods.

### Example Controller:
```java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
@RequestMapping("/users")
public class UserController {

    // Class-level mapping: /users
    @GetMapping
    public List<User> getAllUsers() {
        // Logic to retrieve all users
    }

    // Method-level mapping: /users/{id}
    @GetMapping("/{id}")
    public User getUserById(@PathVariable Long id) {
        // Logic to retrieve a user by ID
    }

    // Method-level mapping: /users/active
    @GetMapping("/active")
    public List<User> getActiveUsers() {
        // Logic to retrieve active users
    }
}
```

### Mapping Structure:
- **Class-Level Mapping**: `@RequestMapping` on the class defines the base path for all methods in the controller.
- **Method-Level Mapping**: Specific HTTP method annotations define additional path segments and methods.

### Multiple Paths:
```java
@GetMapping({"/active", "/status/active"})
public List<User> getActiveUsers() {
    // Logic to retrieve active users
}
```

- **Multiple Path Mappings**: Map multiple paths to a single method.

### Usage:
- **Organize Controllers**: Use class-level mappings to group related endpoints.
- **HTTP Methods**: Use specific method annotations for handling different HTTP methods.

[Back to Top](#table-of-contents)

## What are the common HTTP Response Status Codes?

HTTP response status codes indicate the result of an HTTP request. They are divided into categories based on the type of response.

### Categories of Status Codes:
1. **1xx: Informational**: Request received, continuing process.
   - **100 Continue**: Indicates that the initial part of a request has been received and has not yet been rejected by the server.

2. **2xx: Success**: The request was successfully received, understood, and accepted.
   - **200 OK**: The request has succeeded.
   - **201 Created**: The request has been fulfilled, resulting in the creation of a new resource.
   - **204 No Content**: The server successfully processed the request, but is not returning any content.

3. **3xx: Redirection**: Further action needs to be taken in order to complete the request.
   - **301 Moved Permanently**: The resource has been moved to a new URL permanently.
   - **302 Found**: The resource is temporarily located at a different URI.
   - **304 Not Modified**: The resource has not been modified since the last request.

4. **4xx: Client Error**: The request contains bad syntax or cannot be fulfilled.
   - **400 Bad Request**: The server could not understand the request due to invalid syntax.
   - **401 Unauthorized**: The request requires user authentication.
   - **403 Forbidden**: The server understood the request, but refuses to authorize it.
   - **404 Not Found**: The server cannot find the requested resource.
   - **405 Method Not Allowed**: The request method is not supported for the requested resource.

5. **5xx: Server Error**: The server failed to fulfill an apparently valid request.
   - **500 Internal Server Error**: The server encountered an unexpected condition that prevented it from fulfilling the request.
   - **502 Bad Gateway**: The server received an invalid response from the upstream server.
   - **503 Service Unavailable**: The server is currently unable to handle the request due to temporary overloading or maintenance.

### Usage in RESTful Services:
- **Success Codes**: Return 200 OK for successful retrievals, 201 Created for successful creations, and 204 No Content for successful deletions.
- **Client Errors**: Use 400 Bad Request for invalid input, 401 Unauthorized for authentication failures, and 404 Not Found for missing resources.
- **Server Errors**: Return 500 Internal Server Error for unexpected server failures.

[Back to Top](#table-of-contents)

## What is the cross-origin concept in Spring Web?

The cross-origin concept, also known as Cross-Origin Resource Sharing (CORS), is a security feature implemented by browsers to restrict web pages from making requests to a different domain than the one that served the web page.

### Key Concepts:
- **Same-Origin Policy**: A web page can only request resources from the same domain that served the web page.
- **CORS**: Allows servers to specify which domains are permitted to access resources, overcoming the restrictions of the same-origin policy.

### Configuring CORS in Spring:
#### Global CORS Configuration:
```java
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.web.servlet.config.annotation.CorsRegistry;
import org.springframework.web.servlet.config.annotation.WebMvcConfigurer;

@Configuration
public class WebConfig implements WebMvcConfigurer {
    @Override
    public void addCorsMappings(CorsRegistry registry) {
        registry.addMapping("/**")
                .allowedOrigins("http://allowed-origin.com")
                .allowedMethods("GET", "POST", "PUT", "DELETE")
                .allowedHeaders("*")
                .allowCredentials(true);
    }
}
```

#### Controller-Level CORS Configuration:
```java
import org.springframework.web.bind.annotation.CrossOrigin;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class UserController {

    @CrossOrigin(origins = "http://allowed-origin.com")
    @GetMapping("/users")
    public List<User> getAllUsers() {
        // Logic to retrieve users
    }
}
```

### Key Parameters:
- **allowedOrigins**: Specifies which origins are allowed to access the resource.
- **allowedMethods**: Specifies which HTTP methods are permitted.
- **allowedHeaders**: Specifies which headers can be used in the request.
- **allowCredentials**: Specifies whether credentials are allowed.

### Benefits:
- **Security**: Provides a mechanism to control access to resources from different domains.
- **Flexibility**: Allows web applications to access resources across domains when needed.

### Usage Scenarios:
- **APIs**: Enable CORS for APIs that are accessed by web applications hosted on different domains.
- **Microservices**: Allow communication between microservices hosted on different domains.

[Back to Top](#table-of-contents)

## How many types of input are getting from clients?

In a Spring MVC application, inputs from clients can be obtained in several ways, depending on the nature of the data and its source in the HTTP request.

### Types of Input:
1. **HTTP Headers**: Meta-information sent with the request that can be used for content negotiation, authentication, etc.
   - **Usage**: Use the `@RequestHeader` annotation to access headers.

```java
@GetMapping("/headers")
public ResponseEntity<String> getHeaderInfo(@RequestHeader("User-Agent") String userAgent) {
    return ResponseEntity.ok("User-Agent: " + userAgent);
}
```

2. **Request Body**: Contains the payload of the request, often used in POST and PUT requests for submitting data.
   - **Usage**: Use the `@RequestBody` annotation to bind the body to a method parameter.

```java
@PostMapping("/users")
public ResponseEntity<User> createUser(@RequestBody User user) {
    // Logic to create user
}
```

3. **URI Parameters**: Parameters embedded in the URI path, typically used to identify resources.
   - **Usage**: Use the `@PathVariable` annotation to bind URI parameters.

```java
@GetMapping("/users/{id}")
public ResponseEntity<User> getUserById(@PathVariable Long id) {
    // Logic to retrieve user
}
```

4. **Query Parameters**: Parameters included in the URL query string, often used for filtering and sorting.
   - **Usage**: Use the `@RequestParam` annotation to bind query parameters.

```java
@GetMapping("/users")
public ResponseEntity<List<User>> getUsers(@RequestParam String name) {
    // Logic to filter users by name
}
```

5. **Form Parameters**: Parameters submitted via form submissions, typically in POST requests.
   - **Usage**: Use the `@RequestParam` annotation to bind form parameters.

```java
@PostMapping("/submit")
public ResponseEntity<String> submitForm(@RequestParam String username, @RequestParam String password) {
    // Logic to handle form submission
}
```

### Input Processing in Spring:
- **Type Conversion**: Spring automatically converts input data to the required method parameter types.
- **Validation**: Use annotations like `@Valid` and custom validators to validate input data.
- **Binding Errors**: Handle binding errors using BindingResult or `@ExceptionHandler` methods.

### Example Controller:
```java
@RestController
@RequestMapping("/api")
public class ApiController {

    // Get user by ID from URI
    @GetMapping("/users/{id}")
    public ResponseEntity<User> getUserById(@PathVariable Long id) {
        // Logic to retrieve user
    }

    // Create user from JSON body
    @PostMapping("/users")
    public ResponseEntity<User> createUser(@RequestBody User user) {
        // Logic to create user
    }

    // Get user by query parameter
    @GetMapping("/users")
    public ResponseEntity<List<User>> getUsersByName(@RequestParam String name) {
        // Logic to retrieve users by name
    }

    // Submit form data
    @PostMapping("/submit")
    public ResponseEntity<String> submitForm(@RequestParam String username, @RequestParam String password) {
        // Logic to handle form submission
    }

    // Get header information
    @GetMapping("/headers")
    public ResponseEntity<String> getHeaderInfo(@RequestHeader("User-Agent") String userAgent) {
        return ResponseEntity.ok("User-Agent: " + userAgent);
    }
}
```

[Back to Top](#table-of-contents)

## What is PathVariable and RequestParam in Spring Boot?

In Spring Boot, `@PathVariable` and `@RequestParam` are annotations used to bind request parameters to method parameters in controller classes.

### @PathVariable:
- **Purpose**: Binds URI template variables to method parameters.
- **Use Case**: Typically used for extracting values from the URI path to identify resources.

### Example:
```java
@RestController
@RequestMapping("/api/users")
public class UserController {

    // Example of using @PathVariable
    @GetMapping("/{id}")
    public ResponseEntity<User> getUserById(@PathVariable Long id) {
        // Logic to retrieve user by ID
    }
}
```

- **URI**: `/api/users/123`
- **Description**: The `{id}` path variable in the URI is bound to the `id` parameter in the `getUserById` method.

### @RequestParam:
- **Purpose**: Binds query parameters or form data to method parameters.
- **Use Case**: Typically used for extracting values from the query string or form data for filtering or processing.

### Example:
```java
@RestController
@RequestMapping("/api/users")
public class UserController {

    // Example of using @RequestParam
    @GetMapping
    public ResponseEntity<List<User>> getUsersByAge(@RequestParam int age) {
        // Logic to retrieve users by age
    }
}
```

- **URI**: `/api/users?age=30`
- **Description**: The `age` query parameter is bound to the `age` parameter in the `getUsersByAge` method.

### Key Differences:
- **PathVariable**:
  - Extracts values from the URI path.
  - Used for resource identification.
- **RequestParam**:
  - Extracts values from the query string or form data.
  - Used for filtering, sorting, or data submission.

### Advanced Usage:
#### Optional Parameters:
`@RequestParam` supports optional parameters with default values.

```java
@GetMapping("/search")
public ResponseEntity<List<User>> searchUsers(@RequestParam(required = false, defaultValue = "0") int age) {
    // Logic to search users
}
```

#### Multiple Parameters:
Both annotations support multiple parameters.