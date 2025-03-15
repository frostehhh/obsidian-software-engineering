
Beans are managed by the Spring IoC container with configuration metadata supplied to the container.[^1]

## Overriding Beans
- happens when there is already an existing bean with the same identifier
- Will be deprecated in the future
- To disable overriding, `allowBeanDefinitionOverriding` flag to `false` on the `ApplicationContext`[^2]
- When using Java configuration, silent overriding occurs as long as the return type of the Bean method matches that bean class to override.

## Naming Beans
- camel-cased
- `accountManager`, `accountService`, `userDao`
- You can alias a bean outside of the bean definition via @Bean annotation with Java configuration. With annotation configuration, you can use the `alias` element

## Instantiating Beans
The [[Reference Notes/Spring/Spring Framework/Inversion of Control Container/Introduction|IoC]] Container looks at bean definitions to create the object.
Instantiation methods
- with a constructor
- with a static factory method [^3]
- by using an instance factory method[^4]

[^1]: https://docs.spring.io/spring-framework/reference/core/beans/definition.html
[^2]: https://docs.spring.io/spring-framework/reference/core/beans/definition.html#beans-definition-overriding
[^3]: https://docs.spring.io/spring-framework/reference/core/beans/definition.html#beans-factory-class-static-factory-method
[^4]: https://docs.spring.io/spring-framework/reference/core/beans/definition.html#beans-factory-class-instance-factory-method