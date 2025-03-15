- `@Configuration` and `ComponentScan`
	```kotlin
	@Configuration
	@ComponentScan("com.baeldung.autowire.sample")
	```
- `@SpringBootApplication`
	```kotlin
	@SpringBootApplication
	public class App {
		public static void main(String[] args) {
			SpringApplication.run(App.class, args); 
		}
	}
	```