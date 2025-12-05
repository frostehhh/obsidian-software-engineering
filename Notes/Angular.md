---
tags:
  - notes
  - programming-languages/javascript/angular
Draft: true
has-questions: true
---

- Frontend JavaScript framework made by Google

# Example Component

```
@Component({
	selector: 'app-home',
	template: `
		<div class="main">
			Hello world!
		</div>
	`,
	style: `
		.main {
			font-color: blue;
		}
	`
})
export class App {
}
```

# CLI
`ng`
https://angular.dev/tools/cli
# Fundamental Concepts
## Component
- `@Component` Decorator
- Command: `ng generate component my-component`
## Dependency Injection and Services
- `inject` function
- Command: `ng generate service my-service`
## Interface
- Command: `ng generate interface my-interface`
## Signals
- For dynamic data and reactive values

| Function | Description                                         |
| -------- | --------------------------------------------------- |
| signal   | dynamic value                                       |
| computed | signal that recomputes based on other signal values |
# Routing
- `provideRouter(routeConfig)`
- `Routes` type
- `RouterOutlet` - component where to render page
- `RouterLink` - directive for navigating to path
	`<a [routerLink]=['/details', homeLocation().id]` />

# Questions
- what is an observable type?