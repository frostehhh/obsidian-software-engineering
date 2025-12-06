---
tags:
  - notes
  - programming-languages/javascript/angular
Draft: false
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
## Property Binding
`[...]` for binding values
`(...)` for binding callback functions
```
	<input [value]="myValue" (click)="handleClick($event)" />
```
## Component
- `@Component` Decorator
- Command: `ng generate component my-component`
## Dependency Injection and Services
- `inject` function
- Command: `ng generate service my-service`
```javascript

// service declaration
import {Injectable} from '@angular/core';

@Injectable({providedIn: 'root'})
export class Calculator {
	add(x: number, y: number) {
		return x + y;
	}
}

// service usage
export class App {
	private calculator = inject(Calculator);
	...
	
	constructor() {
		...
	}
}
```
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

# Reactive Forms
- via ReactiveFormsModule - includes imports of other required directives and objects
- FormControl -> init form value
- FormGroup -> init form instance. Contains FormControl instances
- `formControlName` -> `<input ... formControlName="input-name" />`
```
<form [formGroup]="applyForm" (submit)="submitApplication()">
	<label for="first-name">First Name</label>
	<input id="first-name" type="text" formControlName="firstName" />
	<button type="submit" class="primary">Apply now</button>
</form>
```
- `[formGroup]` directive binds the `applyForm` `FormGroup` to the `form` DOM element

# Questions
- what is an observable type? -> RXJS type
- What happened to the old `.bind` usage? It seems we no longer need to do that.
- 2-way sync?
- reactivity docs for `[]` and `(...)` in HTML elements?