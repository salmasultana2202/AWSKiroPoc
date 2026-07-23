# Product API

A Spring Boot CRUD REST API for managing products.

## Tech Stack

- Java 17
- Spring Boot 3.2.5
- Spring Data JPA
- H2 In-Memory Database
- Maven

## Prerequisites

- Java 17+ (bundled with IntelliJ IDEA JBR, or install separately)
- Maven (bundled with IntelliJ IDEA, or install from https://maven.apache.org/download.cgi)

## Running the Application

### Option 1: Using IntelliJ's bundled Maven (PowerShell)

```powershell
$env:JAVA_HOME = "C:\Program Files\JetBrains\IntelliJ IDEA 2026.1\jbr"
& "C:\Program Files\JetBrains\IntelliJ IDEA 2026.1\plugins\maven\lib\maven3\bin\mvn.cmd" spring-boot:run
```

### Option 2: Using IntelliJ IDEA

1. Open this folder in IntelliJ IDEA
2. Wait for Maven import to complete
3. Run `ProductApiApplication.java`

### Option 3: With Maven on PATH

```bash
mvn spring-boot:run
```

The application starts on **http://localhost:8080**.

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/products` | Get all products |
| GET | `/api/products/{id}` | Get product by ID |
| GET | `/api/products/search?name=` | Search products by name |
| POST | `/api/products` | Create a new product |
| PUT | `/api/products/{id}` | Update a product |
| DELETE | `/api/products/{id}` | Delete a product |

## Example Requests

### Create a product

```bash
curl -X POST http://localhost:8080/api/products \
  -H "Content-Type: application/json" \
  -d '{"name": "Laptop", "description": "Gaming laptop", "price": 999.99, "quantity": 10}'
```

### Get all products

```bash
curl http://localhost:8080/api/products
```

## H2 Console

Access the database console at: http://localhost:8080/h2-console

- JDBC URL: `jdbc:h2:mem:productdb`
- Username: `sa`
- Password: *(empty)*

## Project Structure

```
src/main/java/com/example/productapi/
├── ProductApiApplication.java         - Application entry point
├── entity/Product.java                - JPA entity
├── repository/ProductRepository.java  - Data access layer
├── service/ProductService.java        - Business logic
├── controller/ProductController.java  - REST controller
└── exception/
    ├── ResourceNotFoundException.java - Custom 404 exception
    └── GlobalExceptionHandler.java    - Centralized error handling
```
