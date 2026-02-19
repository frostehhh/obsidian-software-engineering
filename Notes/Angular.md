---
tags:
  - notes
  - javascript/angular
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
## Property Binding and Event Binding
`[...]` for binding values
`(...)` for binding events
```
	<input [value]="myValue" (click)="handleClick($event)" />
```

## Two-way Binding
`[(ngModel)]`
```angular
	<input [(ngModel)]="myValue" ... />
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
## Conditionals

| Condition          | Deprecated | v21 |
| ------------------ | ---------- | --- |
| if                 | *ngIf      | @if |
| if... then... else | *ngThen    |     |
### If Then Else
```
<ng-container *ngIf="condition; then thenBlock else elseBlock"></ng-container>

<ng-template #thenBlock>
  <!-- Content to render when condition is true -->
  <p>This is the 'then' content.</p>
</ng-template>

<ng-template #elseBlock>
  <!-- Content to render when condition is false -->
  <p>This is the 'else' content.</p>
</ng-template>

```
## ngTemplate, ngContainer and ngTemplateOutlet
https://blog.angular-university.io/angular-ng-template-ng-container-ngtemplateoutlet/
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