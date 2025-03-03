# @Autowired Annotation
It allows Spring to resolve and inject collaborating beans into our bean.[^1]

## Ways to use @Autowired
### Properties

```java
@Component("fooFormatter")
public class FooFormatter {
    public String format() {
        return "foo";
    }
}
```
### Setters
```java
public class FooService {
    private FooFormatter fooFormatter;
    @Autowired
    public void setFormatter(FooFormatter fooFormatter) {
        this.fooFormatter = fooFormatter;
    }
}

```

### Constructors
```java
public class FooService {
    private FooFormatter fooFormatter;
    @Autowired
    public FooService(FooFormatter fooFormatter) {
        this.fooFormatter = fooFormatter;
    }
}
```

## Optional Dependencies
```java
public class FooService {
    @Autowired(required = false)
    private FooDAO dataAccessor; 
}
```

## Autowire Disambiguation
### Autowiring by @Qualifier
```java
public class FooService {
    @Autowired
    @Qualifier("fooFormatter")
    private Formatter formatter;
}
```
### Autowiring by Custom Qualifier
See https://www.baeldung.com/spring-autowire#2-autowiring-by-custom-qualifier

### Autowiring by Name
```java
public class FooService {
 @Autowired 
private Formatter fooFormatter; 
}
```

# See also
https://www.baeldung.com/spring-autowire

[^1]: https://www.baeldung.com/spring-autowire#overview