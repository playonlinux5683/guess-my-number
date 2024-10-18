# Number Guessing Game

We’ll build a Number Guessing Game with the following features:

1. **User Management**:
   - **Registration**: User can create an account.
   - **Authentication**: User can log in to access the game.
2. **Gameplay Tracking**:
   - **Start Game**: User can start a new game session. A random number is generated
   - **Guess Number**: User attempt to guess the randomly generated number.
   - **Best Score**: Track and display the user’s best (lowest number of attempts) score.

## Purposes ##

Create a Java-based number guessing game that adheres to Hexagonal Architecture (or Clean Architecture), SOLID principles, Test-Driven Development (TDD), and Behavior-Driven Development (BDD) is a robust approach to ensure maintainability, scalability, and reliability. 

There is no wrong answer. Just be yourself and ***HAVE FUN*** !!!!

## Interaction with the API

Here’s the markdown code for the curl commands you provided:

#### Register a user
```bash
curl -X POST "http://localhost:8080/api/users/register?username=john_doe&password=securePass123"
```
#### Login the user
```bash
curl -X POST "http://localhost:8080/api/users/login?username=john_doe&password=securePass123"
```
#### Start a game
```bash
curl -X POST "http://localhost:8080/api/games/start?userId=1"
```
#### Make a guess in the game
```bash
curl -X POST "http://localhost:8080/api/games/guess?userId=1&number=50"
```
#### Get the user’s best score
```bash
curl -X GET "http://localhost:8080/api/games/best-score?userId=1"
```

## Good to know
### Architectural Principles

#### Hexagonal Architecture

Hexagonal Architecture, also known as ***Ports*** and ***Adapters***, emphasizes decoupling the core business logic from external systems. It allows the application to be equally driven by users, programs, automated tests, or batch scripts.

- ***Core (Domain)***: Contains business logic and entities.
- ***Ports***: Interfaces that define communication points.
- ***Adapters***: Implementations of ports that interact with external systems (e.g., databases, web frameworks).

#### Clean Architecture

Clean Architecture focuses on organizing systems to make them highly modular, with a clear separation between business rules and external dependencies. The idea is to keep core logic independent of frameworks, UI, databases, and other external systems, allowing for easier testing and scalability.

- ***Entities (Domain)***: Contains enterprise-wide business rules and core entities. These are the most abstract and independent elements of the system.
- ***Use Cases (Application)***: Holds application-specific business rules, including application workflows and operations, ensuring the domain logic is applied correctly.
- ***Interface Adapters***: Mediates between the core application logic and external systems like databases, web services, or UIs. This layer converts data from the format most convenient for the core logic to what’s needed by external systems.
- ***Frameworks & Drivers***: External infrastructure such as databases, web frameworks, and user interfaces. They are the most volatile and prone to change, and therefore should be kept at the outermost layer.

#### SOLID Principles

Adhering to SOLID principles ensures that the codebase is maintainable, scalable, and easy to understand.

1. ***Single Responsibility Principle (SRP)***: A class should have only one reason to change.
2. ***Open/Closed Principle (OCP)***: Software entities should be open for extension but closed for modification.
3. ***Liskov Substitution Principle (LSP)***: Objects of a superclass should be replaceable with objects of subclasses without affecting the correctness.
4. ***Interface Segregation Principle (ISP)***: Many client-specific interfaces are better than one general-purpose interface.
5. ***Dependency Inversion Principle (DIP)***: Depend on abstractions, not on concrete implementations.

