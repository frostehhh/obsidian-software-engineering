---
tags: 
 - java
 - spring
 - notes
---


| Annotation      | Purpose                                                     | Targets              |
| --------------- | ----------------------------------------------------------- | -------------------- |
| @Component      | Indicates that a class is a bean                            | Class                |
| @Bean           | Basic unit of dependency                                    | Method               |
| @Service        | Implementation of @Component. For service-level classes     | Class                |
| @Configuration  | Indicates that class is a source of method bean definitions | Class                |
| @Repository     | For persistence-level implementations                       | Interface            |
| @CrudRepository |                                                             |                      |
| @RestController | For API-level classes                                       | Class                |
| @WebController  | For API-level classes                                       | Class                |
| @Autowired      | For auto-injecting dependencies                             | Method, Field Member |
| @ComponentScan  |                                                             |                      |
| @Value          |                                                             |                      |
| @Entity         |                                                             |                      |

# A Comprehensive Technical Analysis of Annotation-Driven Development in the Spring and Spring Boot Ecosystems

## Core Stereotype and Framework Annotations

|**Annotation**|**Category**|**Description**|**Target**|
|---|---|---|---|
|`@Component`|Stereotype|The foundational archetype for any class that Spring should manage. It marks the class as a candidate for auto-detection during classpath scanning.|Class|
|`@Service`|Stereotype|A specialization of `@Component` intended for classes in the service layer. It signifies that the class contains business logic.|Class|
|`@Repository`|Stereotype|A specialization of `@Component` for data access objects (DAOs). It enables the automatic translation of persistence-layer exceptions.|Class|
|`@Controller`|Stereotype|Marks a class as a web controller within the Spring MVC framework, allowing it to handle HTTP requests.|Class|
|`@RestController`|Stereotype|A composed annotation that combines `@Controller` and `@ResponseBody`. It is the standard for building REST APIs.|Class|
|`@Configuration`|Configuration|Indicates that a class is a source of bean definitions.|Class|
|`@Bean`|Bean Definition|Annotates a method in a `@Configuration` class that returns an object to be registered in the Spring context.|Method|
|`@ComponentScan`|Configuration|Configures the scanning directives for the container, specifying which packages should be searched for components.|Class|
|`@Import`|Configuration|Allows for the loading of additional `@Configuration` classes to modularize configuration.|Class|
|`@PropertySource`|Configuration|Provides a declarative mechanism for adding property files to Spring's Environment.|Class|

## Dependency Injection and Wiring Annotations

|**Annotation**|**Category**|**Description**|**Target**|
|---|---|---|---|
|`@Autowired`|Dependency Injection|Instructs Spring to inject a dependency by type.|Constructor, Field, Method|
|`@Qualifier`|Dependency Injection|Resolves ambiguity when multiple beans of the same type exist by specifying the exact bean name.|Field, Parameter, Method|
|`@Primary`|Dependency Injection|Designates a specific bean as the default choice when multiple candidates are available for a single-valued dependency.|Class, Method|
|`@Value`|Configuration|Injects externalized values from property files or environment variables into fields or parameters.|Field, Parameter, Method|
|`@Lazy`|Lifecycle|Delays the initialization of a bean until its first use.|Class, Method|
|`@Scope`|Lifecycle|Defines the lifecycle of a bean (e.g., singleton, prototype, request, session).|Class, Method|
|`@Lookup`|Method Injection|Indicates a method that the container will override to return an instance of a specific bean.|Method|
|`@DependsOn`|Lifecycle|Forces the container to initialize one or more specific beans before the annotated bean.|Class, Method|
|`@Resource`|Dependency Injection|A JSR-250 standard annotation for injection, primarily name-driven.|Field, Method|

## Request Mapping and Data Binding Annotations

|**Annotation**|**Category**|**Description**|**Target**|
|---|---|---|---|
|`@RequestMapping`|Web|The primary annotation for mapping web requests to specific methods or classes.|Class, Method|
|`@GetMapping`|Web|A specialized shortcut for GET method endpoints, used for retrieving data.|Method|
|`@PostMapping`|Web|A specialized shortcut for POST method endpoints, used for submitting new data.|Method|
|`@PutMapping`|Web|A specialized shortcut for PUT method endpoints, used for updating existing resources.|Method|
|`@DeleteMapping`|Web|A specialized shortcut for DELETE method endpoints, used for removing resources.|Method|
|`@RequestParam`|Data Binding|Binds query parameters or form data from the request URL to a method parameter.|Parameter|
|`@PathVariable`|Data Binding|Extracts a dynamic segment from the URI path and binds it to a method parameter.|Parameter|
|`@RequestBody`|Data Binding|Instructs Spring to deserialize the HTTP request body into a Java object parameter.|Parameter|
|`@ResponseBody`|Data Binding|Indicates that a method's return value should be serialized directly into the HTTP response body.|Method, Class|
|`@RequestHeader`|Data Binding|Maps a specific HTTP request header value to a method argument.|Parameter|
|`@CookieValue`|Data Binding|Maps a specific HTTP cookie value to a method argument.|Parameter|
|`@CrossOrigin`|Web|Enables Cross-Origin Resource Sharing (CORS) for a specific controller or method.|Class, Method|

## Spring Boot Auto-Configuration and Properties Annotations

|**Annotation**|**Category**|**Description**|**Target**|
|---|---|---|---|
|`@SpringBootApplication`|Boot Core|A composed annotation that marks the main class and includes `@Configuration`, `@EnableAutoConfiguration`, and `@ComponentScan`.|Class|
|`@EnableAutoConfiguration`|Boot Core|Activates the auto-configuration engine to configure beans based on library dependencies.|Class|
|`@ConfigurationProperties`|Properties|Binds external configuration properties to a Java bean in a type-safe manner.|Class, Method|
|`@ConditionalOnClass`|Conditional|Triggers configuration only if the specified class is found on the classpath.|Class, Method|
|`@ConditionalOnMissingBean`|Conditional|Triggers configuration only if a specific bean is not already defined.|Class, Method|
|`@ConditionalOnProperty`|Conditional|Enables or disables a bean based on the presence and value of a specific configuration property.|Class, Method|
|`@ConditionalOnWebApplication`|Conditional|Ensures a configuration is only active within the context of a web-based application.|Class, Method|
|`@ConditionalOnResource`|Conditional|Activates a bean definition only if a specified resource is present.|Class, Method|

## JPA Mapping and Repository Annotations

|**Annotation**|**Category**|**Description**|**Target**|
|---|---|---|---|
|`@Entity`|JPA Mapping|Marks a class as a JPA entity to be mapped to a database table.|Class|
|`@Id`|JPA Mapping|Designates the primary key of the entity.|Field, Method|
|`@GeneratedValue`|JPA Mapping|Specifies the strategy for generating primary key values.|Field, Method|
|`@Table`|JPA Mapping|Specifies the name of the database table and optional constraints.|Class|
|`@Column`|JPA Mapping|Customizes the mapping between a Java field and a database column.|Field, Method|
|`@Transient`|JPA Mapping|Instructs the persistence provider to ignore the field.|Field, Method|
|`@Query`|Repository|Allows the definition of custom JPQL or native SQL queries directly on a repository method.|Method|
|`@Modifying`|Repository|Required for queries that perform updates or deletions.|Method|
|`@Transactional`|Transaction|Manages transactional boundaries for database operations.|Class, Method|
|`@Param`|Repository|Binds method parameters to named parameters within a custom `@Query`.|Parameter|
|`@CreatedDate`|Auditing|Automatically captures the timestamp of creation for an entity.|Field|
|`@LastModifiedDate`|Auditing|Automatically captures the timestamp of the last modification.|Field|

## Aspect-Oriented Programming and Security Annotations

|**Annotation**|**Category**|**Description**|**Target**|
|---|---|---|---|
|`@Aspect`|AOP|Declares a class as an aspect containing pointcuts and advice.|Class|
|`@Pointcut`|AOP|Defines a predicate that matches join points where advice should be applied.|Method|
|`@Before`|AOP|Advice that executes before the target method is called.|Method|
|`@After`|AOP|Advice that executes after the target method finishes.|Method|
|`@Around`|AOP|Advice that runs around a method execution, controlling when and if it runs.|Method|
|`@PreAuthorize`|Security|Uses SpEL to evaluate authorization logic before a method is executed.|Method, Class|
|`@Secured`|Security|A traditional role-based security annotation restricting access to methods.|Method, Class|
|`@EnableMethodSecurity`|Security|Activates method-level security throughout the application context.|Class|

## Lifecycle and Validation Annotations

|**Annotation**|**Category**|**Description**|**Target**|
|---|---|---|---|
|`@PostConstruct`|Lifecycle|Marks a method to be run immediately after the bean's dependencies are injected.|Method|
|`@PreDestroy`|Lifecycle|Marks a method to be run just before the bean is removed from the context.|Method|
|`@Valid`|Validation|Standard JSR-303/380 annotation used to trigger validation on an object's fields.|Parameter, Field|
|`@Validated`|Validation|A Spring-specific annotation enabling validation groups for specific operations.|Class, Parameter|
|`@NotNull`|Validation|Constrains a field or parameter so that it cannot be null.|Field, Parameter|
|`@NotBlank`|Validation|Constrains a string so it must be non-null and not empty after trimming.|Field, Parameter|
|`@Email`|Validation|Ensures that a field value conforms to the standard email format.|Field, Parameter|
|`@Size`|Validation|Validates that the length of a string or collection is within a specific range.|Field, Parameter|

## Task Management and Execution Annotations

|**Annotation**|**Category**|**Description**|**Target**|
|---|---|---|---|
|`@EnableScheduling`|Configuration|Enables the container's ability to process `@Scheduled` methods.|Class|
|`@Scheduled`|Scheduling|Marks a method to be run periodically based on cron, fixed rates, or delays.|Method|
|`@EnableAsync`|Configuration|Enables Spring's ability to run methods annotated with `@Async` in a thread pool.|Class|
|`@Async`|Execution|Indicates that a method should be executed asynchronously on a background thread.|Method, Class|

## Testing and Mocking Annotations

|**Annotation**|**Category**|**Description**|**Target**|
|---|---|---|---|
|`@SpringBootTest`|Testing|Loads the full application context for integration testing.|Class|
|`@MockBean`|Mocking|Creates a Mockito mock and registers it in the application context.|Field|
|`@SpyBean`|Mocking|Wraps a real bean in the context with a Mockito spy for verification.|Field|
|`@ContextConfiguration`|Testing|Defines the configuration sources used to initialize the context for a test.|Class|
|`@ActiveProfiles`|Testing|Specifies which bean definition profiles should be active during the test.|Class|
|`@Sql`|Testing|Instructs the framework to run specific SQL scripts before or after a test method.|Class, Method|
|`@DirtiesContext`|Testing|Indicates a test modified the context, forcing it to be closed and reloaded.|Class, Method|
|`@Commit`|Testing|Forces the transaction for a test method to be committed to the database.|Class, Method|
|`@Rollback`|Testing|Indicates that the transaction for a test method should be rolled back (default).|Class, Method|
|`@DynamicPropertySource`|Testing|Allows adding dynamic property values to the Environment, often for Testcontainers.|Method|