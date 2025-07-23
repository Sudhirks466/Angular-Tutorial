## 🔰 Full Angular 19 Course Roadmap

### ✅ Stage 1: Angular Basics (Beginner)

1. **Introduction to Angular**
   * What is Angular?
   * Angular vs AngularJS
   * Angular CLI and Workspace structure

2. **Setup Environment**
   * Install Node.js and Angular CLI
   * Create your first Angular 19 standalone project:
     ```bash
     npm install -g @angular/cli
     ng new my-angular-app --standalone
     cd my-angular-app
     ng serve
     ```

3. **Angular Building Blocks**
   * Modules (now optional with Standalone Components)
   * Components
   * Templates & Interpolation (`{{ }}`)
   * Property Binding, Event Binding
   * Two-way Binding with `[(ngModel)]`

4. **Directives**
   * Built-in directives: `*ngIf`, `*ngFor`, `ngClass`, `ngStyle`
   * Structural vs Attribute Directives
   * Custom Directives

5. **Services and Dependency Injection (DI)**
   * Creating services with `@Injectable()`
   * DI in components

6. **Routing**
   * Angular Router basics
   * Lazy Loading modules & Standalone routes
   * Route Guards (CanActivate, CanDeactivate)
   * New enhancements in Angular 19 Router
     
---

### ✅ Stage 2: Forms, Pipes, and HTTP (Intermediate)

7. **Forms in Angular**
   * Template-driven Forms
   * Reactive Forms
   * Validators and Custom Validators

8. **Pipes**
   * Built-in pipes: `date`, `uppercase`, `currency`
   * Custom Pipes

9. **HTTP Client**
   * Setup `HttpClientModule`
   * GET, POST, PUT, DELETE requests
   * Observables with RxJS
   * Error handling with `catchError`

---

### ✅ Stage 3: Angular 19 Advanced Topics

10. **Signals (Angular 16+)**
    * `signal`, `computed`, `effect`
    * Comparison with RxJS
    * Usage in reactive forms or data flows

11. **Standalone Components**
    * Why they're introduced
    * How to use them with routing and dependency injection

12. **Component Communication**
    * Input and Output decorators
    * ViewChild, ContentChild
    * Services as state containers

13. **Change Detection**
    * Default vs OnPush strategy
    * Zone.js vs NgZone

14. **Performance Optimization**
    * ESBuild integration
    * `ngOptimizedImage`
    * Preloading strategies
    * Deferred Loading

15. **Testing**
    * Unit testing with Karma/Jasmine
    * E2E testing with Cypress or Playwright

16. **Build & Deploy**
    * Build with `ng build`
    * Deploy to Firebase/Netlify/Vercel

---

### 🆕 Angular 19 Features to Cover

* New deferrable views with `@defer`, `@placeholder`, `@loading`, `@error`
* New `Router.configure()` method
* Signals-based reactivity
* Hydration improvements for SSR
* Control flow syntax (`@if`, `@for` etc.)
---

Perfect, Sudhir! Let's begin your **Angular 19 course** step by step. I’ll provide clear explanations with examples. You can practice each step and ask questions anytime.

---

## 🔹 **Lesson 1: What is Angular?**

### ✅ Angular is:

* A **TypeScript-based** open-source front-end framework.
* Developed by **Google**.
* Used for **building SPAs** (Single Page Applications).
* Follows a **component-based architecture**.

---

## 🔹 **Lesson 2: Angular vs AngularJS**

| Feature         | AngularJS (1.x) | Angular (2+ to 19)      |
| --------------- | --------------- | ----------------------- |
| Language        | JavaScript      | TypeScript              |
| Architecture    | MVC             | Component-based         |
| Mobile Support  | No              | Yes                     |
| Performance     | Slower          | Faster with Ivy Engine  |
| Modularity      | Poor            | Highly modular          |
| Modern Features | None            | RxJS, Signals, DI, etc. |

---

## 🔹 **Lesson 3: Install Angular CLI & Create Project**

### ✅ Step 1: Install Node.js (Skip if already installed)

Go to: [https://nodejs.org](https://nodejs.org)

---

### ✅ Step 2: Install Angular CLI globally

```bash
npm install -g @angular/cli
```

---

### ✅ Step 3: Create a new Angular 19 standalone project

```bash
ng new my-angular-app --standalone
cd my-angular-app
```

It will ask:

* Add Angular routing? → Yes
* Which stylesheet format? → Choose `SCSS` or `CSS`

---

### ✅ Step 4: Run your Angular app

```bash
ng serve
```

Then open your browser and go to:
👉 `http://localhost:4200`

You will see the default Angular welcome page.

---

### 🧪 Mini Task for You:

1. Create the project `my-angular-app`
2. Run it locally
3. Reply "done ✅" when you see the default welcome page

---

## 🔹 **Lesson 6: Property Binding & Event Binding in Angular**

These two are **core concepts** in Angular for communication between HTML and component logic.

---

### ✅ Property Binding — `[property]="value"`

It’s used to **pass data from component class → to HTML element or component**.

#### 🧪 Example:

```ts
// hello-world.component.ts
export class HelloWorldComponent {
  imageUrl: string = 'https://angular.io/assets/images/logos/angular/angular.svg';
}
```

```html
<!-- hello-world.component.html -->
<img [src]="imageUrl" width="100" />
```

📝 `src` is the HTML image attribute — we bind it to the `imageUrl` variable.

---

### ✅ Event Binding — `(event)="handler()"`

It’s used to **execute a method in component when an event occurs in the template**.

#### 🧪 Example:

```ts
// hello-world.component.ts
export class HelloWorldComponent {
  counter = 0;

  increment() {
    this.counter++;
  }
}
```

```html
<!-- hello-world.component.html -->
<p>Counter: {{ counter }}</p>
<button (click)="increment()">Increment</button>
```

📝 `(click)` is the event; `increment()` is the function that runs when button is clicked.

---

## 🔁 Combine Both

```ts
export class HelloWorldComponent {
  userName = 'Sudhir';

  changeName() {
    this.userName = 'Angular Hero';
  }
}
```

```html
<p>Hello, {{ userName }}!</p>
<button (click)="changeName()">Change Name</button>
```

---

### ✅ Recap:

| Binding Type     | Syntax    | Direction       |
| ---------------- | --------- | --------------- |
| Property Binding | `[value]` | Component → DOM |
| Event Binding    | `(event)` | DOM → Component |

---

### 🧪 Mini Task:

Try adding:

* An image using `[src]`
* A button with `(click)` that updates some text
---

## 🔹 **Lesson 7: Two-Way Data Binding with `[(ngModel)]`**

### ✅ What is Two-Way Binding?

Two-way binding keeps the data in sync **between the component class and the UI input** — if you change one, the other updates automatically.

### 🔁 Syntax:

```html
[(ngModel)]="property"
```

It’s a **shortcut** for:

```html
[value]="property" (input)="property = $event.target.value"
```

---

### ✅ Setup: Import FormsModule

Go to `app.config.ts` or `main.ts` wherever you're bootstrapping the app.

**Add `importProvidersFrom(FormsModule)`** like this:

```ts
import { provideHttpClient } from '@angular/common/http';
import { importProvidersFrom } from '@angular/core';
import { FormsModule } from '@angular/forms';

export const appConfig: ApplicationConfig = {
  providers: [
    importProvidersFrom(FormsModule),
    provideHttpClient()
  ]
};
```

This allows `[(ngModel)]` to work in your components.

---

### 🧪 Example in Component

#### `hello-world.component.ts`

```ts
export class HelloWorldComponent {
  name = '';
}
```

#### `hello-world.component.html`

```html
<label>Your Name:</label>
<input [(ngModel)]="name" placeholder="Enter name" />
<p>Hello, {{ name }}!</p>
```

🧠 This will automatically update `name` in both UI and class.

---

## ✅ Bonus: Bind to a Number

```ts
age = 0;
```

```html
<input type="number" [(ngModel)]="age" />
<p>Your Age is: {{ age }}</p>
```

---

## 🧪 Mini Task:

1. Add an input for name and show live greeting using `[(ngModel)]`.
2. Add a number input for age and display it.
---

## 🔹 **Lesson 8: Angular Directives**

Angular **Directives** are special instructions in the DOM. They are divided into:

| Type           | Examples                        |
| -------------- | ------------------------------- |
| **Structural** | `*ngIf`, `*ngFor`, `*ngSwitch`  |
| **Attribute**  | `ngClass`, `ngStyle`, `ngModel` |

---

### ✅ 1. `*ngIf` — Conditional Rendering

#### `hello-world.component.ts`

```ts
export class HelloWorldComponent {
  isLoggedIn = false;
}
```

#### `hello-world.component.html`

```html
<button (click)="isLoggedIn = !isLoggedIn">
  Toggle Login
</button>

<p *ngIf="isLoggedIn">Welcome Sudhir!</p>
<p *ngIf="!isLoggedIn">Please log in.</p>
```

---

### ✅ 2. `*ngFor` — Loop Over Arrays

#### `hello-world.component.ts`

```ts
export class HelloWorldComponent {
  fruits = ['Apple', 'Banana', 'Mango'];
}
```

#### `hello-world.component.html`

```html
<ul>
  <li *ngFor="let fruit of fruits">{{ fruit }}</li>
</ul>
```

Add index (optional):

```html
<li *ngFor="let fruit of fruits; index as i">
  {{ i + 1 }}. {{ fruit }}
</li>
```

---

### ✅ 3. `ngClass` — Apply Classes Dynamically

#### `hello-world.component.ts`

```ts
export class HelloWorldComponent {
  isActive = true;
}
```

#### `hello-world.component.html`

```html
<p [ngClass]="{ 'active-text': isActive }">This text is styled</p>

<button (click)="isActive = !isActive">Toggle Style</button>
```

In `hello-world.component.scss`:

```scss
.active-text {
  color: green;
  font-weight: bold;
}
```

---

### ✅ 4. `ngStyle` — Apply Inline Styles Dynamically

```html
<p [ngStyle]="{ color: isActive ? 'green' : 'gray', fontSize: '20px' }">
  Styled with ngStyle
</p>
```

---

## 🧪 Mini Task:

1. Use `*ngIf` to show/hide text.
2. Use `*ngFor` to loop through 3 items.
3. Toggle text color using `ngClass`.

---

## 🔹 **Lesson 9: Services & Dependency Injection (DI)**

### ✅ What is a Service?

A **Service** in Angular is a **class that contains business logic or reusable data**, like:

* API calls
* Shared values
* Utility functions

---

## ✅ What is Dependency Injection (DI)?

DI means **injecting dependencies (like services) into components** automatically. Angular has a built-in DI system.

---

## 🔧 Step-by-Step: Create a Service

### 🔹 Step 1: Generate a Service

Run this in terminal:

```bash
ng generate service user
```

This creates:

```
src/app/user.service.ts
```

---

### 🔹 Step 2: Add Logic in the Service

#### `user.service.ts`

```ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root' // makes it globally available
})
export class UserService {
  getUserName() {
    return 'Sudhir Sahani';
  }
}
```

---

### 🔹 Step 3: Inject and Use It in Component

#### `hello-world.component.ts`

```ts
import { Component } from '@angular/core';
import { UserService } from '../user.service';

@Component({
  selector: 'app-hello-world',
  standalone: true,
  templateUrl: './hello-world.component.html',
  styleUrls: ['./hello-world.component.scss'],
  imports: []
})
export class HelloWorldComponent {
  username: string = '';

  constructor(private userService: UserService) {
    this.username = this.userService.getUserName();
  }
}
```

#### `hello-world.component.html`

```html
<p>Username from service: {{ username }}</p>
```

---

## 🧪 Mini Task:

1. Generate a new service (e.g. `user`)
2. Add a method to return a name
3. Inject it into a component using the constructor
4. Display it in the template

---

## 🔹 **Lesson 10: Routing and Navigation in Angular**

Routing allows your Angular app to move between different **views/pages** (components) **without reloading the page** (SPA behavior).

---

### ✅ Step 1: Create Two Components

Let’s create two standalone components:

```bash
ng generate component home --standalone
ng generate component about --standalone
```

Now you’ll have:

* `home.component.ts`
* `about.component.ts`

---

### ✅ Step 2: Setup Routing

Go to `app/routes.ts` and add:

```ts
import { Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';

export const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'about', component: AboutComponent }
];
```

This defines routes:

* `/` → HomeComponent
* `/about` → AboutComponent

---

### ✅ Step 3: Add `<router-outlet>`

Update `app.component.html`:

```html
<h1>My Angular App 🚀</h1>
<nav>
  <a routerLink="/">Home</a> |
  <a routerLink="/about">About</a>
</nav>

<hr />

<router-outlet></router-outlet>
```

This tells Angular where to **load routed components**.

---

### ✅ Step 4: Add RouterModule to App Config

Go to `app.config.ts` and make sure you import:

```ts
import { provideRouter } from '@angular/router';
import { routes } from './app.routes';

export const appConfig: ApplicationConfig = {
  providers: [
    provideRouter(routes)
  ]
};
```

---

### ✅ Step 5: Run the App

```bash
ng serve
```

* Visit `/` to see Home page.
* Visit `/about` or click the link to navigate to About page.

---

## 🧪 Mini Task:

1. Create 2 components: `home`, `about`
2. Configure routes in `app.routes.ts`
3. Use `<router-outlet>` in `app.component.html`
4. Add `<a routerLink>` navigation

---

## 🔹 **Lesson 11: Template-driven Forms vs Reactive Forms**

Angular offers **two approaches** for building forms:

| Feature       | Template-driven Form       | Reactive Form                           |
| ------------- | -------------------------- | --------------------------------------- |
| Setup         | HTML-based (`[(ngModel)]`) | Code-based (`FormControl`, `FormGroup`) |
| Flexibility   | Simple forms               | Complex logic, validations              |
| Module Needed | `FormsModule`              | `ReactiveFormsModule`                   |
| Best For      | Quick/basic forms          | Large, dynamic, validated forms         |

---

### ✅ A. Template-driven Form (You've already used this!)

```ts
// app.config.ts
import { importProvidersFrom } from '@angular/core';
import { FormsModule } from '@angular/forms';

providers: [
  importProvidersFrom(FormsModule)
]
```

#### Example

```ts
// hello-world.component.ts
export class HelloWorldComponent {
  user = { name: '', email: '' };

  submitForm() {
    console.log('Form submitted:', this.user);
  }
}
```

```html
<form (ngSubmit)="submitForm()">
  <input name="name" [(ngModel)]="user.name" placeholder="Name" required />
  <input name="email" [(ngModel)]="user.email" placeholder="Email" required />
  <button type="submit">Submit</button>
</form>
```

---

### ✅ B. Reactive Forms

### Step 1: Add `ReactiveFormsModule`

```ts
// app.config.ts
import { ReactiveFormsModule } from '@angular/forms';

providers: [
  importProvidersFrom(ReactiveFormsModule)
]
```

---

### Step 2: Use `FormGroup` and `FormControl`

```ts
import { Component } from '@angular/core';
import { FormControl, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'app-hello-world',
  standalone: true,
  imports: [],
  templateUrl: './hello-world.component.html'
})
export class HelloWorldComponent {
  userForm = new FormGroup({
    name: new FormControl('', Validators.required),
    email: new FormControl('', [Validators.required, Validators.email])
  });

  onSubmit() {
    console.log('Reactive form submitted:', this.userForm.value);
  }
}
```

```html
<form [formGroup]="userForm" (ngSubmit)="onSubmit()">
  <input formControlName="name" placeholder="Name" />
  <input formControlName="email" placeholder="Email" />
  <button type="submit">Submit</button>
</form>
```

---

## 🔁 Summary:

| Feature    | Template-driven       | Reactive                |
| ---------- | --------------------- | ----------------------- |
| Simplicity | Easy, declarative     | More powerful, flexible |
| Control    | In HTML               | In Component TS         |
| Validation | With `required`, etc. | With `Validators`       |

---

## 🧪 Mini Task:

1. Try both:

   * A simple template-driven form using `[(ngModel)]`
   * A reactive form using `FormGroup` and `FormControl`
2. Submit and log form values in console

---

## 🔹 **Lesson 12: Angular Form Validation (Built-in + Custom)**

We’ll cover validation for both:

* **Template-driven forms**
* **Reactive forms**

---

## ✅ 1. Template-driven Validation

In HTML, you can add built-in validation attributes like `required`, `minlength`, `email`, etc.

### 🔧 Example:

```html
<form #userForm="ngForm" (ngSubmit)="submitForm(userForm)">
  <input
    name="name"
    [(ngModel)]="user.name"
    required
    minlength="3"
    #nameRef="ngModel"
  />
  <div *ngIf="nameRef.invalid && nameRef.touched">
    <small *ngIf="nameRef.errors?.['required']">Name is required</small>
    <small *ngIf="nameRef.errors?.['minlength']">Min 3 characters</small>
  </div>

  <button [disabled]="userForm.invalid">Submit</button>
</form>
```

---

## ✅ 2. Reactive Form Validation

We use `Validators` from `@angular/forms`.

### 🔧 Example:

#### `hello-world.component.ts`

```ts
import { FormGroup, FormControl, Validators } from '@angular/forms';

export class HelloWorldComponent {
  userForm = new FormGroup({
    name: new FormControl('', [Validators.required, Validators.minLength(3)]),
    email: new FormControl('', [Validators.required, Validators.email])
  });

  onSubmit() {
    console.log(this.userForm.value);
  }
}
```

#### `hello-world.component.html`

```html
<form [formGroup]="userForm" (ngSubmit)="onSubmit()">
  <input formControlName="name" />
  <div *ngIf="userForm.get('name')?.invalid && userForm.get('name')?.touched">
    <small *ngIf="userForm.get('name')?.hasError('required')">Required</small>
    <small *ngIf="userForm.get('name')?.hasError('minlength')">Min 3 chars</small>
  </div>

  <input formControlName="email" />
  <div *ngIf="userForm.get('email')?.invalid && userForm.get('email')?.touched">
    <small *ngIf="userForm.get('email')?.hasError('required')">Email is required</small>
    <small *ngIf="userForm.get('email')?.hasError('email')">Invalid email</small>
  </div>

  <button [disabled]="userForm.invalid">Submit</button>
</form>
```

---

## ✅ 3. Custom Validators

Create your own validation function:

### 🔧 Example: Only allow "Sudhir"

```ts
function customNameValidator(control: FormControl) {
  return control.value === 'Sudhir' ? null : { nameMismatch: true };
}

userForm = new FormGroup({
  name: new FormControl('', [customNameValidator])
});
```

```html
<div *ngIf="userForm.get('name')?.hasError('nameMismatch')">
  Name must be "Sudhir"
</div>
```

---

## 🧪 Mini Task:

1. Add validation to both template and reactive forms.
2. Show validation error messages.
3. Try one **custom validator** too.

---

## 🔹 **Lesson 13: Angular Pipes (Built-in + Custom)**

### ✅ What is a Pipe?

A **Pipe** in Angular transforms **data in the template** — like changing text to uppercase, formatting dates, currencies, etc.

### 🔁 Syntax:

```html
{{ value | pipeName }}
```

---

## ✅ 1. Built-in Pipes

| Pipe        | Usage Example | Output Example       |                        |
| ----------- | ------------- | -------------------- | ---------------------- |
| `uppercase` | \`{{ name     | uppercase }}\`       | JOHN                   |
| `lowercase` | \`{{ name     | lowercase }}\`       | john                   |
| `titlecase` | \`{{ name     | titlecase }}\`       | John Smith             |
| `date`      | \`{{ today    | date:'fullDate' }}\` | Tuesday, July 23, 2025 |
| `currency`  | \`{{ amount   | currency:'INR' }}\`  | ₹1,000.00              |
| `percent`   | \`{{ 0.75     | percent }}\`         | 75%                    |
| `json`      | \`{{ obj      | json }}\`            | formatted JSON string  |

---

### 🧪 Example:

#### `hello-world.component.ts`

```ts
export class HelloWorldComponent {
  name = 'sudhir sahani';
  amount = 2500;
  today = new Date();
  user = { name: 'Sudhir', email: 'sudhir@email.com' };
}
```

#### `hello-world.component.html`

```html
<p>Uppercase: {{ name | uppercase }}</p>
<p>Currency: {{ amount | currency:'INR' }}</p>
<p>Date: {{ today | date:'mediumDate' }}</p>
<p>JSON: {{ user | json }}</p>
```

---

## ✅ 2. Custom Pipe

### 🔧 Step 1: Generate Pipe

```bash
ng generate pipe customGreeting
```

This will create:

```ts
custom-greeting.pipe.ts
```

---

### 🔧 Step 2: Define Pipe Logic

#### `custom-greeting.pipe.ts`

```ts
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'customGreeting',
  standalone: true
})
export class CustomGreetingPipe implements PipeTransform {
  transform(name: string): string {
    return `Welcome, ${name}!`;
  }
}
```

---

### 🔧 Step 3: Use in Component Template

Make sure to import the pipe in your standalone component:

#### `hello-world.component.ts`

```ts
import { CustomGreetingPipe } from '../custom-greeting.pipe';

@Component({
  ...
  imports: [CustomGreetingPipe]
})
```

#### `hello-world.component.html`

```html
<p>{{ name | customGreeting }}</p>
```

---

## 🧪 Mini Task:

1. Use 3 built-in pipes in your template (e.g., `date`, `currency`, `titlecase`)
2. Create and use your own custom pipe (e.g., `customGreeting`)

---

## 🔹 **Lesson 14: HTTP Requests with Angular `HttpClient`**

Angular’s `HttpClient` service is used to make API requests like `GET`, `POST`, `PUT`, `DELETE`.

---

### ✅ Step 1: Import `HttpClientModule`

Go to `app.config.ts` and add:

```ts
import { provideHttpClient } from '@angular/common/http';

export const appConfig: ApplicationConfig = {
  providers: [
    provideHttpClient() // enables HttpClient
  ]
};
```

---

### ✅ Step 2: Create a Service for API Calls

```bash
ng generate service user-api
```

#### `user-api.service.ts`

```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({ providedIn: 'root' })
export class UserApiService {
  private apiUrl = 'https://jsonplaceholder.typicode.com/users';

  constructor(private http: HttpClient) {}

  getUsers(): Observable<any[]> {
    return this.http.get<any[]>(this.apiUrl);
  }

  createUser(user: any): Observable<any> {
    return this.http.post(this.apiUrl, user);
  }
}
```

---

### ✅ Step 3: Use It in Your Component

#### `hello-world.component.ts`

```ts
import { Component, OnInit } from '@angular/core';
import { UserApiService } from '../user-api.service';

@Component({
  selector: 'app-hello-world',
  standalone: true,
  templateUrl: './hello-world.component.html'
})
export class HelloWorldComponent implements OnInit {
  users: any[] = [];

  constructor(private userApi: UserApiService) {}

  ngOnInit(): void {
    this.userApi.getUsers().subscribe((res) => {
      this.users = res;
    });
  }

  addUser() {
    const newUser = {
      name: 'Sudhir',
      email: 'sudhir@email.com'
    };
    this.userApi.createUser(newUser).subscribe((res) => {
      console.log('User created:', res);
    });
  }
}
```

---

### ✅ Step 4: Template Example

#### `hello-world.component.html`

```html
<h3>User List</h3>
<ul>
  <li *ngFor="let user of users">{{ user.name }} ({{ user.email }})</li>
</ul>

<button (click)="addUser()">Add User</button>
```

---

## 🔁 Common HTTP Methods:

| Action     | Method    | Angular Code Example        |
| ---------- | --------- | --------------------------- |
| Read data  | GET       | `this.http.get(url)`        |
| Create new | POST      | `this.http.post(url, body)` |
| Update     | PUT/PATCH | `this.http.put(url, body)`  |
| Delete     | DELETE    | `this.http.delete(url)`     |

---

## 🧪 Mini Task:

1. Create a `user-api.service.ts`
2. Make a GET request to show users
3. Add a POST button to simulate adding a user

---

## 🔹 **Lesson 15: Component Communication (Parent ↔ Child)**

Angular apps have **many components** that often need to **talk to each other**.

There are 3 main ways to communicate between components:

| Communication Type | Used Between         | Mechanism                       |
| ------------------ | -------------------- | ------------------------------- |
| Parent → Child     | Input binding        | `@Input()`                      |
| Child → Parent     | Event binding        | `@Output()` with `EventEmitter` |
| Shared service     | Unrelated components | Via a common `Service`          |

---

## ✅ 1. Parent → Child Communication (`@Input()`)

### Step 1: Create child component

```bash
ng generate component child-box --standalone
```

### Step 2: Accept data using `@Input()`

#### `child-box.component.ts`

```ts
import { Component, Input } from '@angular/core';

@Component({
  selector: 'app-child-box',
  standalone: true,
  template: `<p>Message from parent: {{ message }}</p>`
})
export class ChildBoxComponent {
  @Input() message: string = '';
}
```

### Step 3: Use it in parent (`hello-world.component.ts`)

```ts
import { ChildBoxComponent } from '../child-box/child-box.component';

@Component({
  selector: 'app-hello-world',
  standalone: true,
  imports: [ChildBoxComponent],
  template: `
    <app-child-box [message]="parentMessage"></app-child-box>
  `
})
export class HelloWorldComponent {
  parentMessage = 'Hello from Parent!';
}
```

---

## ✅ 2. Child → Parent Communication (`@Output()`)

### Step 1: Emit event from child

#### `child-box.component.ts`

```ts
import { Component, Output, EventEmitter } from '@angular/core';

@Component({
  selector: 'app-child-box',
  standalone: true,
  template: `<button (click)="sendMessage()">Click Me</button>`
})
export class ChildBoxComponent {
  @Output() childClicked = new EventEmitter<string>();

  sendMessage() {
    this.childClicked.emit('Hi from Child!');
  }
}
```

### Step 2: Handle event in parent

#### `hello-world.component.ts`

```ts
@Component({
  selector: 'app-hello-world',
  standalone: true,
  imports: [ChildBoxComponent],
  template: `
    <app-child-box (childClicked)="receiveMessage($event)"></app-child-box>
    <p>Message from child: {{ childMessage }}</p>
  `
})
export class HelloWorldComponent {
  childMessage = '';

  receiveMessage(msg: string) {
    this.childMessage = msg;
  }
}
```

---

## ✅ 3. Service-Based Communication (Shared State)

For **unrelated components**, use a service with RxJS `Subject`.

If you want to try that, I’ll guide you in the next lesson.

---

## 🧪 Mini Task:

1. Pass data from parent to child using `@Input()`
2. Emit event from child to parent using `@Output()`
   
---

## 🔹 **Lesson 16: Angular Lifecycle Hooks**

### ✅ What are Lifecycle Hooks?

Angular components and directives go through a series of stages — from **creation**, to **update**, to **destruction**.

Angular provides **lifecycle hooks** so you can **tap into each stage**.

---

### 🔁 Most Common Lifecycle Hooks

| Hook                | Triggered When...                     |
| ------------------- | ------------------------------------- |
| `ngOnInit()`        | Component is initialized (runs once)  |
| `ngOnChanges()`     | Any `@Input()` property changes       |
| `ngDoCheck()`       | Custom change detection               |
| `ngAfterViewInit()` | Component view (DOM) initialized      |
| `ngOnDestroy()`     | Component is destroyed (cleanup here) |

---

## ✅ 1. `ngOnInit()` – Initialization Logic

```ts
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-hello-world',
  standalone: true,
  template: `<p>Check console for lifecycle logs</p>`
})
export class HelloWorldComponent implements OnInit {
  ngOnInit() {
    console.log('Component initialized!');
  }
}
```

Use this to:

* Fetch data
* Setup timers
* Initialize values

---

## ✅ 2. `ngOnChanges()` – Detecting `@Input()` Changes

#### In child component:

```ts
import { Component, Input, OnChanges, SimpleChanges } from '@angular/core';

@Component({
  selector: 'app-child-box',
  standalone: true,
  template: `<p>Received: {{ data }}</p>`
})
export class ChildBoxComponent implements OnChanges {
  @Input() data: string = '';

  ngOnChanges(changes: SimpleChanges) {
    console.log('Input changed:', changes);
  }
}
```

---

## ✅ 3. `ngOnDestroy()` – Cleanup

```ts
import { OnDestroy } from '@angular/core';

export class HelloWorldComponent implements OnDestroy {
  interval: any;

  ngOnInit() {
    this.interval = setInterval(() => {
      console.log('Running...');
    }, 1000);
  }

  ngOnDestroy() {
    clearInterval(this.interval);
    console.log('Component destroyed, timer cleared!');
  }
}
```

---

## 🧪 Mini Task:

1. Use `ngOnInit()` to log a message on load.
2. Use `ngOnChanges()` in a child to detect `@Input()` changes.
3. Use `ngOnDestroy()` to clean up a `setInterval`.

---

## 🔹 **Lesson 17: Angular Routing Guards (CanActivate & CanDeactivate)**

### ✅ What are Guards?

Guards let you **protect or restrict routes** in Angular. Common use cases:

* Check if user is **logged in** (`CanActivate`)
* Show confirmation before **navigating away** (`CanDeactivate`)
* Lazy loading control
* Admin vs User access

---

### 🔐 Types of Guards

| Guard              | Purpose                                   |
| ------------------ | ----------------------------------------- |
| `CanActivate`      | Controls access **to a route**            |
| `CanDeactivate`    | Controls navigation **away from a route** |
| `CanActivateChild` | Checks child routes                       |
| `Resolve`          | Pre-fetch data before route loads         |
| `CanLoad`          | Controls lazy-loaded modules              |

---

## ✅ 1. `CanActivate` — Protect a Route

### Step 1: Create a Guard

```bash
ng generate guard auth --standalone
```

### Step 2: Implement Logic

#### `auth.guard.ts`

```ts
import { CanActivateFn } from '@angular/router';

export const authGuard: CanActivateFn = () => {
  const isLoggedIn = confirm('Are you logged in?');
  return isLoggedIn;
};
```

---

### Step 3: Apply to Route

#### `app.routes.ts`

```ts
import { authGuard } from './auth.guard';
import { AboutComponent } from './about/about.component';

export const routes: Routes = [
  { path: '', component: HomeComponent },
  {
    path: 'about',
    component: AboutComponent,
    canActivate: [authGuard]
  }
];
```

Now if you visit `/about`, a confirmation box will appear!

---

## ✅ 2. `CanDeactivate` — Prevent Leaving Page

### Step 1: Create the Guard

```bash
ng generate guard exit --standalone
```

### Step 2: Add Logic

#### `exit.guard.ts`

```ts
import { CanDeactivateFn } from '@angular/router';
import { HelloWorldComponent } from './hello-world/hello-world.component';

export const exitGuard: CanDeactivateFn<HelloWorldComponent> = (component) => {
  return confirm('Do you really want to leave this page?');
};
```

---

### Step 3: Apply to Route

#### `app.routes.ts`

```ts
{
  path: 'hello',
  component: HelloWorldComponent,
  canDeactivate: [exitGuard]
}
```

Now, trying to navigate away from `/hello` will show a confirmation.

---

## 🧪 Mini Task:

1. Create a `CanActivate` guard to simulate login check.
2. Create a `CanDeactivate` guard to confirm navigation away.
3. Apply both to routes like `/about` and `/hello`.

---

## 🔹 **Lesson 18: Angular Signals (Angular 16+ feature)**

**Signals** are a **new way to manage reactive state** in Angular without RxJS.
They’re:

* Easier to understand
* Fine-grained reactive
* Like React’s `useState` but for Angular

---

## ✅ 1. What is a Signal?

A **Signal** is a special reactive value that updates the UI automatically when changed.

### 🔁 Syntax:

```ts
import { signal } from '@angular/core';

const counter = signal(0);

counter();      // read
counter.set(5); // update
counter.update(val => val + 1); // increment
```

---

## ✅ 2. Create a Signal

#### `hello-world.component.ts`

```ts
import { Component, signal } from '@angular/core';

@Component({
  selector: 'app-hello-world',
  standalone: true,
  templateUrl: './hello-world.component.html'
})
export class HelloWorldComponent {
  count = signal(0);

  increment() {
    this.count.update(val => val + 1);
  }
}
```

#### `hello-world.component.html`

```html
<p>Signal Count: {{ count() }}</p>
<button (click)="increment()">Increment</button>
```

---

## ✅ 3. Derived Signals (`computed`)

```ts
import { computed } from '@angular/core';

totalClicks = signal(10);
doubleClicks = computed(() => this.totalClicks() * 2);
```

Now, when `totalClicks` changes, `doubleClicks` auto-updates.

---

## ✅ 4. Side Effects (`effect`)

```ts
import { effect } from '@angular/core';

effect(() => {
  console.log('Count changed:', this.count());
});
```

This logs the new value whenever `count` changes.

---

## ✅ Summary

| Function     | Purpose                    |
| ------------ | -------------------------- |
| `signal()`   | Creates reactive state     |
| `computed()` | Derives new reactive value |
| `effect()`   | Run code on signal change  |

---

## 🧪 Mini Task:

1. Create a counter using `signal`
2. Add a `computed` value (e.g. `count x 2`)
3. Use `effect()` to log count when it changes

---

## 🔹 **Lesson 19: Standalone Components (No NgModules)**

Angular now supports **Standalone Components**, **Directives**, and **Pipes**, which means:

> ✅ You can build apps **without `NgModule` files** — reducing boilerplate and improving clarity.

---

## ✅ What is a Standalone Component?

A **standalone component**:

* Has `standalone: true` in its decorator
* Can be used directly in routing or in other components without being declared in a module

---

### 🔧 Example

#### `hello-world.component.ts`

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-hello-world',
  standalone: true,
  template: `<h2>Hello from Standalone!</h2>`
})
export class HelloWorldComponent {}
```

This can be used directly in the router:

#### `app.routes.ts`

```ts
export const routes: Routes = [
  { path: '', component: HelloWorldComponent }
];
```

No need to declare it in any module!

---

## ✅ Importing Other Standalone Features

When using:

* Forms → `FormsModule`
* Router → `RouterModule`
* Other standalone components → must import them

#### `parent.component.ts`

```ts
import { HelloWorldComponent } from './hello-world.component';

@Component({
  selector: 'app-parent',
  standalone: true,
  imports: [HelloWorldComponent],
  template: `<app-hello-world />`
})
export class ParentComponent {}
```

---

## ✅ Generating Standalone Components

Use the CLI:

```bash
ng generate component my-comp --standalone
ng generate directive my-dir --standalone
ng generate pipe my-pipe --standalone
```

---

## ✅ Benefits

| Standalone Feature   | Benefit                       |
| -------------------- | ----------------------------- |
| `standalone: true`   | No need for NgModule          |
| `imports: []`        | Local control of dependencies |
| Works with routing   | Easy integration              |
| Improved performance | Simpler tree shaking          |

---

## 🧪 Mini Task:

1. Create a new standalone component (`dashboard`)
2. Use it directly in your routes
3. Import and use another standalone component inside it

---

## 🔹 **Lesson 20: Deferred Loading in Angular (`@defer`, `@loading`, `@error`, `@placeholder`)**

### ✅ What is Deferred Loading?

`@defer` lets Angular **delay loading heavy components**, **lazy content**, or **dynamic sections** — **without extra boilerplate** or manual lazy imports.

Think of it like:

> 👉 "Load this part of the page only when needed."

---

## ✅ Syntax:

```html
@defer {
  <heavy-component />
} @placeholder {
  <p>Loading component...</p>
} @loading {
  <p>Still loading...</p>
} @error {
  <p>Failed to load component.</p>
}
```

---

## ✅ Step-by-Step Example

Let’s lazy-load a standalone component using `@defer`.

---

### 🔧 Step 1: Create Lazy Component

```bash
ng generate component lazy-box --standalone
```

#### `lazy-box.component.ts`

```ts
@Component({
  selector: 'app-lazy-box',
  standalone: true,
  template: `<h3>This is a heavy lazy-loaded component 😴</h3>`
})
export class LazyBoxComponent {}
```

---

### 🔧 Step 2: Use `@defer` in Parent Template

#### `hello-world.component.html`

```html
<h2>Welcome to Dashboard</h2>

@defer {
  <app-lazy-box />
} @placeholder {
  <p>Getting ready...</p>
} @loading {
  <p>Still loading...</p>
} @error {
  <p>Error loading the box 😢</p>
}
```

#### Don’t forget to import the lazy component!

#### `hello-world.component.ts`

```ts
import { LazyBoxComponent } from '../lazy-box/lazy-box.component';

@Component({
  ...
  standalone: true,
  imports: [LazyBoxComponent],
  ...
})
```

---

## ✅ Triggers for `@defer`

You can add when/how to defer loading:

```html
@defer (when visible) {
  <app-lazy-box />
}
```

| Trigger        | Meaning                            |
| -------------- | ---------------------------------- |
| `when visible` | Loads only when scrolled into view |
| `on idle`      | Loads when browser is idle         |
| `after 5s`     | Delays by 5 seconds                |

---

## ✅ Benefits

* Reduce **initial load time**
* Improve **LCP** (Largest Contentful Paint)
* Better **user-perceived performance**

---

## 🧪 Mini Task:

1. Create a lazy component like `LazyBoxComponent`
2. Use it with `@defer` and `@placeholder`/`@loading`
3. Test different triggers like `(when visible)` or `(after 3s)`

---

## 🔹 **Lesson 21: Image Optimization with `ngOptimizedImage`**

Angular provides a powerful built-in directive:
👉 `ngSrc` (via `NgOptimizedImage`) — which **loads images faster**, reduces layout shifts, and improves **Core Web Vitals** 🚀

---

## ✅ Why use `ngOptimizedImage`?

* Lazy loads images by default
* Prevents layout shift with `width` and `height`
* Supports `priority` for above-the-fold content
* Works with responsive images

---

## ✅ Step-by-Step Setup

### 🔧 Step 1: Import `provideImageKit` (Angular 15+)

In your `app.config.ts`:

```ts
import { provideImageKit } from '@angular/common';

export const appConfig: ApplicationConfig = {
  providers: [
    provideImageKit()
  ]
};
```

This enables the `ngSrc` directive globally.

---

### 🔧 Step 2: Use in a Component Template

#### `hello-world.component.html`

```html
<h2>Optimized Image</h2>

<img
  ngSrc="https://angular.io/assets/images/logos/angular/angular.svg"
  width="150"
  height="150"
  alt="Angular Logo"
  priority
/>
```

### ⚠️ Required:

* `ngSrc` instead of `src`
* Explicit `width` and `height`

---

## ✅ Optional Features

### 👉 Lazy Loading (default)

```html
<img ngSrc="..." width="200" height="200" />
```

### 👉 Priority (load immediately, no lazy)

```html
<img ngSrc="..." width="200" height="200" priority />
```

### 👉 Responsive Images

```html
<img
  ngSrc="https://picsum.photos/300"
  width="300"
  height="300"
  alt="Responsive"
  [sizes]="'(max-width: 600px) 100vw, 300px'"
/>
```

---

## ✅ Comparison

| Regular `<img>`      | Optimized with `ngSrc`      |
| -------------------- | --------------------------- |
| `<img src="..." />`  | `<img ngSrc="..." />`       |
| Layout shift risk    | Layout is preserved         |
| Manual lazy loading  | Lazy by default             |
| No `priority` option | Use `priority` for fast LCP |

---

## 🧪 Mini Task:

1. Replace a standard `<img>` with `ngSrc`
2. Add width, height, and `priority`
3. Try loading a responsive image using `sizes`

---

## 🔹 **Lesson 22: Angular Animations with `@angular/animations`**

Angular supports **powerful, native animations** using:

* Triggers
* States
* Transitions
* Keyframes
* `@angular/animations` package

---

## ✅ Step 1: Enable Animations

### In `app.config.ts`:

```ts
import { provideAnimations } from '@angular/platform-browser/animations';

export const appConfig: ApplicationConfig = {
  providers: [
    provideAnimations()
  ]
};
```

---

## ✅ Step 2: Add Basic Animation to a Component

### 🔧 `hello-world.component.ts`

```ts
import {
  Component,
  trigger,
  state,
  style,
  transition,
  animate
} from '@angular/core';

@Component({
  selector: 'app-hello-world',
  standalone: true,
  animations: [
    trigger('toggleBox', [
      state('open', style({ height: '200px', backgroundColor: 'lightgreen' })),
      state('closed', style({ height: '100px', backgroundColor: 'lightcoral' })),
      transition('open <=> closed', [animate('300ms ease-in-out')])
    ])
  ],
  templateUrl: './hello-world.component.html'
})
export class HelloWorldComponent {
  isOpen = true;

  toggleBox() {
    this.isOpen = !this.isOpen;
  }
}
```

---

### 🔧 `hello-world.component.html`

```html
<button (click)="toggleBox()">
  Toggle Box
</button>

<div
  [@toggleBox]="isOpen ? 'open' : 'closed'"
  style="width: 300px; margin-top: 10px;"
>
  <p>This box is animated!</p>
</div>
```

---

## ✅ What’s Happening:

| Concept      | Explanation                         |
| ------------ | ----------------------------------- |
| `trigger`    | Name of animation                   |
| `state`      | Define styles for each state        |
| `transition` | Defines how to animate between them |
| `animate`    | Duration and easing of animation    |

---

## ✅ Bonus: Fade In / Fade Out Example

```ts
trigger('fade', [
  transition(':enter', [style({ opacity: 0 }), animate('400ms', style({ opacity: 1 }))]),
  transition(':leave', [animate('400ms', style({ opacity: 0 }))])
])
```

Use this with `*ngIf` blocks:

```html
<div *ngIf="show" @fade>Fades in and out!</div>
```

---

## 🧪 Mini Task:

1. Enable `provideAnimations()` in your config
2. Add a box that changes color/height using animation
3. Try a fade-in/fade-out example

---

## 🔹 **Lesson 23: Building & Deploying an Angular App**

Whether for local testing or public hosting, Angular makes it easy to **build and deploy** your app with just a few commands.

---

## ✅ 1. Production Build

This creates an optimized, minified version of your app for production.

### 🔧 Command:

```bash
ng build --configuration=production
```

> Output will be in the `dist/` folder — e.g., `dist/my-angular-app`

It includes:

* Minified JS
* Tree-shaken code
* Lazy-loaded chunks
* Optimized images (if used)

---

## ✅ 2. Serve Production Build Locally

Install a static file server globally:

```bash
npm install -g http-server
```

Run:

```bash
http-server dist/my-angular-app
```

Open in browser:
👉 `http://localhost:8080`

---

## ✅ 3. Deploy to Firebase (One of the easiest options)

### Step-by-Step:

#### 🔧 Install Firebase CLI:

```bash
npm install -g firebase-tools
```

#### 🔧 Login to Firebase:

```bash
firebase login
```

#### 🔧 Initialize:

```bash
firebase init
```

Choose:

* Hosting
* Select your Firebase project or create one
* Set `dist/my-angular-app` as your public directory

#### 🔧 Deploy:

```bash
firebase deploy
```

🚀 Your app will be live at a `.web.app` or `.firebaseapp.com` domain!

---

## ✅ 4. Alternative Hosting Options

| Host             | Setup                                |
| ---------------- | ------------------------------------ |
| **Netlify**      | Drag & drop `dist` folder or use CLI |
| **Vercel**       | Connect Git repo, auto-deploy        |
| **GitHub Pages** | Use `angular-cli-ghpages` package    |
| **AWS / Azure**  | Use `ng build` output in S3/Blob     |

---

## ✅ Optional: Add Base Href

If deploying to a subfolder (e.g., `/myapp/`), add in `angular.json`:

```json
"baseHref": "/myapp/"
```

Or pass via CLI:

```bash
ng build --configuration=production --base-href="/myapp/"
```

---

## 🧪 Mini Task:

1. Build the project using `ng build --configuration=production`
2. Test locally using `http-server`
3. (Optional) Deploy to Firebase or Netlify

---

## 🔹 **Lesson 24: Angular Interview Questions + Project Ideas**

---

## ✅ Part A: Top Angular Interview Questions (with Answers)

### 1. What are the main building blocks of Angular?

* Components
* Templates
* Directives
* Services
* Dependency Injection
* Routing
* Modules (optional with standalone)

---

### 2. What is the difference between reactive and template-driven forms?

* **Reactive Forms**: Code-driven, more scalable, better for complex forms.
* **Template-driven Forms**: Template-based, simpler, better for basic use cases.

---

### 3. What are Angular Signals?

* Signals are a new reactivity model in Angular.
* They allow fine-grained control over state changes using `signal`, `computed`, and `effect`.

---

### 4. What are lifecycle hooks in Angular?

* `ngOnInit`, `ngOnChanges`, `ngDoCheck`, `ngAfterViewInit`, `ngOnDestroy`, etc.

---

### 5. How does Angular handle routing?

* Using `RouterModule`, routes, guards (`CanActivate`, `CanDeactivate`), and lazy loading.

---

### 6. How are standalone components different from traditional ones?

* No need for `NgModules`
* Uses `standalone: true`
* Declared and imported directly

---

### 7. How do you optimize Angular apps?

* Lazy loading
* `@defer`, `ngOptimizedImage`
* `OnPush` change detection
* ESBuild
* Route preloading strategies

---

## ✅ Part B: Angular Project Ideas (Beginner to Advanced)

### 🟢 Beginner:

* **Task Tracker** (CRUD with localStorage)
* **Weather App** (API + basic UI)
* **Calculator**

### 🟡 Intermediate:

* **User Management Panel** (CRUD + routing + form validation)
* **Blog Platform** (posts, comments, lazy loading)
* **Quiz App** with dynamic questions

### 🔴 Advanced:

* **E-commerce Admin Panel** (product mgmt, users, orders)
* **Chat App** (WebSocket + RxJS + Signals)
* **Learning Platform** (video lessons, authentication, progress tracking)

---

## ✅ Your Angular Journey Summary:

| Topic               | ✅ |
| ------------------- | - |
| Setup & CLI         | ✅ |
| Components, Routing | ✅ |
| Forms & Validation  | ✅ |
| Services & DI       | ✅ |
| Lifecycle & Guards  | ✅ |
| Signals, Standalone | ✅ |
| Deferred Loading    | ✅ |
| Optimized Images    | ✅ |
| Animations          | ✅ |
| Build & Deploy      | ✅ |

You’ve covered **100%** of the Angular 19 course. 💥
