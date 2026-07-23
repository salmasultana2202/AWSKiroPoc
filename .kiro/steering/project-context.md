# Product API - Project Context

## Overview
This is a Spring Boot 3.2.5 CRUD REST API for managing products, using Java 17 and an H2 in-memory database.

## Tech Stack
- Java 17
- Spring Boot 3.2.5
- Spring Data JPA
- H2 Database (in-memory)
- Bean Validation (Jakarta)
- Maven

## Project Structure
```
src/main/java/com/example/productapi/
├── ProductApiApplication.java        (Main entry point)
├── entity/Product.java               (JPA entity)
├── repository/ProductRepository.java (Spring Data JPA repository)
├── service/ProductService.java       (Business logic)
├── controller/ProductController.java (REST endpoints)
└── exception/
    ├── ResourceNotFoundException.java
    └── GlobalExceptionHandler.java
```

## API Endpoints
- GET    /api/products         - List all products
- GET    /api/products/{id}    - Get product by ID
- GET    /api/products/search?name= - Search by name
- POST   /api/products         - Create product
- PUT    /api/products/{id}    - Update product
- DELETE /api/products/{id}    - Delete product

## How to Build & Run
Maven is not on the system PATH. Use IntelliJ's bundled Maven:

```powershell
$env:JAVA_HOME = "C:\Program Files\JetBrains\IntelliJ IDEA 2026.1\jbr"
& "C:\Program Files\JetBrains\IntelliJ IDEA 2026.1\plugins\maven\lib\maven3\bin\mvn.cmd" spring-boot:run
```

Or open the project in IntelliJ IDEA and run `ProductApiApplication.java` directly.

## Conventions
- Standard layered architecture: Controller → Service → Repository
- Global exception handling via @RestControllerAdvice
- Validation via Jakarta Bean Validation annotations on the entity
- Constructor injection (no @Autowired on fields)
