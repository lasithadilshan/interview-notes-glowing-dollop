### Angular Interview Questions and Answers

#### 1. What is Angular?
**Answer:**
Angular is an open-source, front-end web application framework developed by Google. It is used to build dynamic and single-page applications (SPAs) using HTML, CSS, and TypeScript. Angular provides a structured and modular approach to web development.

#### 2. What are the main features of Angular?
**Answer:**
- **Two-Way Data Binding**: Synchronizes data between the model and the view.
- **Dependency Injection**: Manages dependencies and makes it easier to maintain code.
- **Directives**: Extend HTML with custom attributes and elements.
- **Components**: Encapsulate the view logic and can be reused across the application.
- **Services**: Share data and functionality across components.
- **Routing**: Provides navigation and deep linking capabilities.
- **Forms**: Supports template-driven and reactive forms for handling user input.

#### 3. What is a component in Angular?
**Answer:**
A component is a fundamental building block of an Angular application. It is a class annotated with the `@Component` decorator, which defines the metadata, template, and styles for the component. Components control a part of the UI and can be nested within other components.

#### 4. What is a module in Angular?
**Answer:**
A module in Angular is a class annotated with the `@NgModule` decorator. It serves as a container for a cohesive block of code, including components, directives, pipes, and services. Modules help organize an application into functional areas and manage dependencies.

#### 5. What is the purpose of the `@NgModule` decorator?
**Answer:**
The `@NgModule` decorator is used to define an Angular module. It takes a metadata object that describes the module's components, directives, pipes, services, and other modules it depends on. The metadata includes properties like `declarations`, `imports`, `providers`, and `bootstrap`.

#### 6. What is data binding in Angular?
**Answer:**
Data binding is a mechanism that allows synchronization between the model and the view. Angular supports four types of data binding:
- **Interpolation**: `{{ expression }}` for binding data from the component to the template.
- **Property Binding**: `[property]="expression"` for binding data to DOM properties.
- **Event Binding**: `(event)="handler"` for binding events to methods in the component.
- **Two-Way Binding**: `[(ngModel)]="property"` for binding data in both directions.

#### 7. What are directives in Angular?
**Answer:**
Directives are classes that add behavior to elements in the DOM. Angular has three types of directives:
- **Component Directives**: Use the `@Component` decorator to create components.
- **Structural Directives**: Change the DOM layout by adding or removing elements (e.g., `*ngIf`, `*ngFor`).
- **Attribute Directives**: Change the appearance or behavior of elements (e.g., `ngClass`, `ngStyle`).

#### 8. What is dependency injection in Angular?
**Answer:**
Dependency injection (DI) is a design pattern used to manage dependencies in an application. Angular's DI system allows you to inject services and other dependencies into components, directives, and other services. This promotes modularity, reusability, and testability.

#### 9. How do you create a service in Angular?
**Answer:**
To create a service in Angular, you define a class annotated with the `@Injectable` decorator. The `@Injectable` decorator marks the class as a service that can be injected into other components and services.

```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class MyService {
  constructor() {}

  getData() {
    return 'Hello, Angular!';
  }
}
```

#### 10. What is Angular CLI?
**Answer:**
Angular CLI (Command Line Interface) is a powerful tool that helps automate the development process in Angular. It provides commands for creating, building, and managing Angular projects. It simplifies tasks like scaffolding components, services, and modules, as well as running tests and deploying applications.

#### 11. What is Angular Universal?
**Answer:**
Angular Universal is a technology that enables server-side rendering (SSR) for Angular applications. It allows rendering Angular applications on the server, which improves performance, SEO, and initial load time. Angular Universal generates static HTML on the server and sends it to the client.

#### 12. What are reactive forms in Angular?
**Answer:**
Reactive forms provide a model-driven approach to handling form inputs. They are built around observable streams and offer more control and flexibility compared to template-driven forms. Reactive forms use the `FormControl`, `FormGroup`, and `FormArray` classes to manage form inputs and validation.

#### 13. How do you handle routing in Angular?
**Answer:**
Routing in Angular is managed by the `@angular/router` package. It allows you to define routes, navigate between views, and pass parameters. You configure routes using the `RouterModule` and the `Routes` array.

```typescript
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';

const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'about', component: AboutComponent },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

#### 14. What is the purpose of the `ngOnInit` lifecycle hook?
**Answer:**
The `ngOnInit` lifecycle hook is a method defined in the `OnInit` interface. It is called once after the component's data-bound properties have been initialized. It is commonly used for initialization logic, such as fetching data from a service or setting up initial state.

```typescript
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-example',
  templateUrl: './example.component.html',
  styleUrls: ['./example.component.css'],
})
export class ExampleComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {
    // Initialization logic here
  }
}
```

#### 15. What is Angular Ivy?
**Answer:**
Angular Ivy is the new rendering engine introduced in Angular 9. It improves compilation and rendering performance, reduces bundle size, and offers better debugging capabilities. Ivy enables features like tree-shaking, which removes unused code, and allows for more efficient code generation.

#### 16. How do you create a custom pipe in Angular?
**Answer:**
To create a custom pipe in Angular, you define a class annotated with the `@Pipe` decorator and implement the `PipeTransform` interface. The `transform` method contains the logic for transforming the input value.

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'customPipe'
})
export class CustomPipe implements PipeTransform {
  transform(value: string, ...args: any[]): string {
    return value.toUpperCase();
  }
}
```

#### 17. What is change detection in Angular?
**Answer:**
Change detection is the process by which Angular checks for changes in the application's data model and updates the view accordingly. Angular uses a change detection mechanism that compares the current state of the model with the previous state and updates the DOM if there are any differences.

#### 18. How do you optimize the performance of an Angular application?
**Answer:**
- **Lazy Loading**: Load modules only when needed to reduce initial load time.
- **Ahead-of-Time (AOT) Compilation**: Precompile templates and components to reduce runtime overhead.
- **Tree Shaking**: Remove unused code during the build process.
- **Change Detection Strategy**: Use `OnPush` change detection strategy for components with immutable data.
- **Caching**: Use caching mechanisms for HTTP requests and static assets.
- **Optimize Rendering**: Avoid unnecessary DOM manipulations and use trackBy for `*ngFor` loops.

#### 19. How do you handle authentication in Angular?
**Answer:**
Authentication in Angular can be handled using services and guards. A common approach is to create an authentication service that manages login, logout, and token storage. Route guards can be used to protect routes and ensure that only authenticated users can access certain parts of the application.

```typescript
import { Injectable } from '@angular/core';
import { CanActivate, Router } from '@angular/router';
import { AuthService } from './auth.service';

@Injectable({
  providedIn: 'root',
})
export class AuthGuard implements CanActivate {
  constructor(private authService: AuthService, private router: Router) {}

  canActivate(): boolean {
    if (this.authService.isAuthenticated()) {
      return true;
    } else {
      this.router.navigate(['/login']);
      return false;
    }
  }
}
```

#### 20. What is Angular Material?
**Answer:**
Angular Material is a UI component library for Angular applications, based on Google's Material Design principles. It provides a set of reusable, well-designed components like buttons, forms, tables, dialogs, and more, which help developers build consistent and visually appealing user interfaces.
