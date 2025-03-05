### NestJS Interview Questions and Answers

#### 1. What is NestJS?
**Answer:**
NestJS is a progressive Node.js framework for building efficient, reliable, and scalable server-side applications. It is built with TypeScript and uses Express.js under the hood, but can also be configured to use Fastify.

#### 2. What are the main features of NestJS?
**Answer:**
- **Modular Architecture**: NestJS uses modules to organize components and services, promoting modularity and reusability.
- **Dependency Injection**: Provides a powerful and easy-to-use dependency injection system, making it easier to manage and test components.
- **TypeScript Support**: Fully supports TypeScript, offering type safety and modern JavaScript features.
- **Middleware**: Supports middleware to handle requests and responses.
- **Decorators**: Uses decorators to define routes, middleware, and other application elements, improving code readability and structure.

#### 3. What is a module in NestJS?
**Answer:**
A module is a class annotated with the `@Module()` decorator. It organizes related components, services, and other modules, encapsulating them in a cohesive block of functionality.

#### 4. What are controllers in NestJS?
**Answer:**
Controllers are responsible for handling incoming requests and returning responses to the client. They are defined using the `@Controller()` decorator and contain route handlers (methods) decorated with route decorators like `@Get()`, `@Post()`, etc.

#### 5. What is the purpose of the `@Injectable()` decorator in NestJS?
**Answer:**
The `@Injectable()` decorator marks a class as a provider that can be managed by NestJS's dependency injection system. It allows the class to be injected into other classes (like controllers and services) as a dependency.

#### 6. How does dependency injection work in NestJS?
**Answer:**
Dependency injection in NestJS allows you to inject instances of providers (services, repositories, etc.) into other classes. It uses the `@Injectable()` decorator to mark a class as a provider and the constructor to inject dependencies.

#### 7. What is a service in NestJS?
**Answer:**
A service is a class annotated with the `@Injectable()` decorator that contains business logic and can be injected into controllers or other services. Services are typically used to abstract and encapsulate complex logic and data access.

#### 8. What is middleware in NestJS, and how is it used?
**Answer:**
Middleware is a function that can be executed before the route handler. It can modify the request and response objects or terminate the request-response cycle. Middleware is defined as a class that implements the `NestMiddleware` interface and can be applied to routes using the `apply()` method in the module's configuration.

#### 9. What are guards in NestJS?
**Answer:**
Guards are classes that implement the `CanActivate` interface and are used to determine whether a request should be allowed to proceed or not. They can be used for authentication, authorization, or other conditions that need to be checked before processing a request.

#### 10. What are interceptors in NestJS?
**Answer:**
Interceptors are classes that implement the `NestInterceptor` interface and can be used to bind extra logic before or after method execution. They can be used for logging, transforming responses, handling exceptions, etc.

#### 11. What is a pipe in NestJS?
**Answer:**
A pipe is a class that implements the `PipeTransform` interface and can be used to transform and validate incoming data. Pipes can be applied to route parameters, request bodies, or globally.

#### 12. How do you handle exceptions in NestJS?
**Answer:**
Exceptions in NestJS are handled using exception filters. An exception filter is a class that implements the `ExceptionFilter` interface and contains logic for handling exceptions. You can create custom exception filters or use built-in ones like `HttpException`.

#### 13. What is the purpose of the `@Param()`, `@Query()`, and `@Body()` decorators in NestJS?
**Answer:**
- `@Param()`: Extracts route parameters from the request.
- `@Query()`: Extracts query parameters from the request.
- `@Body()`: Extracts the body of the request.

#### 14. How do you implement database integration in NestJS?
**Answer:**
Database integration in NestJS can be achieved using various libraries like TypeORM, Mongoose, Sequelize, etc. You define entities or schemas, create repositories, and use services to interact with the database.

#### 15. What is the purpose of the `@Module()` decorator in NestJS?
**Answer:**
The `@Module()` decorator is used to define a module in NestJS. It takes an object with properties like `controllers`, `providers`, `imports`, and `exports` to configure the module and its dependencies.
