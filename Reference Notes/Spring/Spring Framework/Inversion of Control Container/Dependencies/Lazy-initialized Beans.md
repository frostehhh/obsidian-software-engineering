By default, all singleton beans are part of the initialization process. This can be prevented via the `@Lazy` annotation[^1]. This causes a bean to be initialized only when requested, and not during startup. This can also be added to a `@Configuration` class

[^1]: https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-lazy-init.html