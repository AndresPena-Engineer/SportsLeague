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
- **Database**: SQL Server (or other relational databases).
- **API Documentation**: Swagger/OpenAPI.
- **Testing**: xUnit, Moq for unit testing.
- **Dependency Injection**: Built-in DI in ASP.NET Core.

---

## **Setup Instructions**

### **Prerequisites**

- .NET 6.0 SDK or later.
- SQL Server (or your preferred database).
- Visual Studio or your favorite IDE.

### **Steps to Run**

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/your-repo/SportsLeague.git
   cd SportsLeague
   ```

2. **Setup Database**:

   - Update the connection string in `appsettings.json` under the `API` project.
   - Apply migrations:
     ```bash
     dotnet ef database update --project Infrastructure
     ```

3. **Build the Solution**:

   ```bash
   dotnet build
   ```

4. **Run the Application**:

   ```bash
   dotnet run --project API
   ```

5. **Access the API**:

   - Open Swagger at `http://localhost:{port}/swagger` to explore the endpoints.

---

## **Future Enhancements**

1. Add support for multi-league organizations.
2. Introduce caching with Redis for frequently accessed data (e.g., standings, schedules).
3. Implement advanced player statistics and analytics.
4. Provide a front-end client (e.g., React or Angular).
5. Add real-time updates for game results using SignalR.

---

## **Contributing**

Contributions are welcome! Follow these steps to contribute:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature-name`).
3. Commit your changes (`git commit -m 'Add your message'`).
4. Push to the branch (`git push origin feature/your-feature-name`).
5. Open a pull request.

---

## **License**

This project is licensed under the MIT License. See the `LICENSE` file for details.

