# SportsLeague

SportsLeague is a Domain-Driven Design (DDD) based application for organizing sports leagues, with a focus on scheduling games, tracking team rosters, maintaining season tables, and monitoring top scorers. This project is built using C# and follows clean architecture principles to ensure modularity, scalability, and maintainability.

---

## **Project Features**

1. **Game Scheduling**:
   - Create and manage game schedules.
   - Update game results and statuses.

2. **Season Management**:
   - Track season standings (season table).
   - Display top scorers and stats for the season.

3. **Team Roster Management**:
   - Maintain team rosters and player details.
   - Add or update player information.

4. **Scalable API**:
   - RESTful APIs for interaction with the system.
   - OpenAPI/Swagger for API documentation.

---

## **Solution Structure**

The solution is divided into multiple projects following DDD principles:

### **1. Domain**
- **Purpose**: Contains the core domain logic.
- **Key Components**:
  - Aggregates: `GameSchedule`, `Season`, `Team`, `Player`.
  - Value Objects: `Score`, `TeamName`.
  - Domain Services: Encapsulate domain-specific business rules.
  - Interfaces: Repository contracts (`IGameScheduleRepository`, `ITeamRepository`, etc.).

### **2. Application**
- **Purpose**: Orchestrates application logic and mediates between the domain and API.
- **Key Components**:
  - Commands: For creating/updating domain objects (e.g., `CreateGameScheduleCommand`).
  - Queries: For retrieving data (e.g., `GetSeasonTableQuery`).
  - DTOs: Data Transfer Objects for API responses.
  - Application Services: Coordinate use cases and enforce application workflows.

### **3. Infrastructure**
- **Purpose**: Implements technical details and integrations.
- **Key Components**:
  - Repositories: Implement domain repository interfaces.
  - Persistence: Database context and migrations (e.g., using EF Core).
  - Integrations: External services (e.g., notification service).
  - Configurations: App configuration files.

### **4. API**
- **Purpose**: Exposes the application functionality via RESTful APIs.
- **Key Components**:
  - Controllers: Handle HTTP requests for games, teams, and seasons.
  - Dependency Injection: Register services and dependencies.
  - Swagger Integration: Provides API documentation.

### **5. Tests**
- **Purpose**: Ensures application quality through testing.
- **Key Components**:
  - Unit Tests: Validate domain logic and application services.
  - Integration Tests: Verify repository and database interactions.
  - Acceptance Tests: Test end-to-end workflows.

---

## **Technologies Used**

- **Programming Language**: C#
- **Frameworks**: 
  - ASP.NET Core for API development.
  - EF Core for database access.
- **Design Principles**: Domain-Driven Design (DDD), Clean Architecture.
- **Database**: SQL Server (or other relational databases