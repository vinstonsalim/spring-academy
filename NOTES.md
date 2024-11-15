# Building REST API with Spring Boot

## REST API Related

1. Use `@RestController` put in the top of the class
    - Controller will be injected to Spring Web
2. Use `@GetMapping`
    - Map the uri example: "/entity/{requestedId}"
    - `findById(@PathVariable Long requestedId)` 
    - Its only for GET Method
3. Use `PathVariable` to access the variable in URI
4. Use `RequestMapping` add prefix to controller
5. Use `ResponseEntity` to send back entity as response body

## Choosing a Database
1. Embedded, in memory database
    - H2 Database for local development
2. Persistent -> External (Postgrel, MySql, etc)

### Using Repository Pattern
- Create interface that `extends CrudRepository<T, Long>`.

## Test Related
- To run test use command `./grandlew test`



### Goal
1. Spring Boot for RESTful API
1. Spring Boot vs Spring Framework
1. Spring Web
1. Spring Data for ORM
1. Spring Security

### Spring vs Spring Boot

Spring
1. Comprehensive framework that provides various modules for building different types of applications.
2. Requires a lot of configurations.

Spring Boot
1. Optionated version of Spring
1. Comes with many pre-configure settings and dependencies that are commonly used in Spring applications. 
1. Spring Boot comes with an embedded web server.

---

### Spring's Inversion of Control Container (IoC)

* Dependency Injection (DI) is a spezialied form of IoC, where objects define their dependencies only through
    1. constructor argument, 
    2. arguments to a factory method or 
    3. properties that are set on the object instance after its constructed

* It's like dependency injection (Providing dependencies at runtime)
    1. By using direct construction
    2. Or using mechanichem such aas Service Locator Pattern

* IoC Container uses
    1. `org.springframework.beans` for framework configuration and basic functionality
    2. `org.springframework.context` for enterprise-specific-funtionalitiy


## Configuration Metadata

1. Spring IoC container consume configuration metadata.
1. To write spring configuration data, we can use:
    1. Annotaion-based configuration: define beans using annotaion-based configuration metadata on application's component class. 
    2. Java-based configuration: define beans external to your application by using java-based configuration class.
        - @Configuration
        - @Bean
        - @Import
        - @DependsOn

1. If referencing class for beans configuration its better not to use relative path  like "../" s

## Bean Overview

- Beans are created with the configuration metadata by for example XML File
- BeanDefinition object contains :
    1. Package-qualified class name: the actual implementation class of the bean beind defined. 
    2. Bean behavioral configuration elements: scope, lifecycle callbacks and so forth.
    3. References to other beans thats are needed for the bean to do its work
    4. Other config to set in the newly created object: size limit of the pool or the number of connections to use in a bean that manages a connection pool.
- Bean can be aliased.


## Resources

- Important methods from Resource interface
    1. getInputStream(): returning an InputStream for reading resource.
    2. exists()
    3. isOpen()
    4. getDescription()
- Built-in Resource Implementations
    1. UrlResource: all string url: file:, https:, ftp:
    2. ClassPathReference
    3. FileSystemResource: implementation for java.io.File
    4. PathResource: implementation for java.nio.file.Path
    5. ServletContextResource: 
    6. InputStreamResource
    7. ByteArrayResource


### Starting With Project
u
1. Open Spring Initializr
1. For packaging use Jar
1. Add dependencies
    1. Spring Web
1. Create as zip file
