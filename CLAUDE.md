# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Subair Backend is a Spring Boot 3.5.7 application using Java 21 and Maven for build management. This is currently a minimal Spring Boot starter project with DevTools enabled for development.

**Group ID**: `com.biryuzabear`
**Artifact ID**: `subair`
**Base Package**: `com.biryuzabear.subair`

## Build and Development Commands

### Prerequisites
- Java 21 must be installed and JAVA_HOME environment variable must be set correctly

### Building the Project
```bash
# Clean and build
./mvnw clean install

# Build without running tests
./mvnw clean install -DskipTests

# Package the application
./mvnw package
```

### Running the Application
```bash
# Run the Spring Boot application
./mvnw spring-boot:run

# Run with specific profile
./mvnw spring-boot:run -Dspring-boot.run.profiles=dev
```

### Health Check
The application includes Spring Boot Actuator with health endpoint:
```bash
# Check application health (application must be running)
curl http://localhost:8080/actuator/health

# Available actuator endpoints
curl http://localhost:8080/actuator
```

### Testing
```bash
# Run all tests
./mvnw test

# Run a specific test class
./mvnw test -Dtest=SubairApplicationTests

# Run tests with coverage
./mvnw clean test jacoco:report
```

### Development
```bash
# Run with DevTools (hot reload enabled)
./mvnw spring-boot:run

# Compile without running
./mvnw compile
```

## Project Architecture

### Current Structure
- **Main Application**: `SubairApplication.java` - Standard Spring Boot entry point with `@SpringBootApplication` annotation
- **Configuration**: `application.properties` - Application name and Actuator endpoints configuration (health, info)
- **Testing**: Basic Spring Boot test setup with `SubairApplicationTests.java`
- **Health Endpoint**: `/actuator/health` - Available for CI/CD and deployment verification

### Dependencies
- `spring-boot-starter-web` - Web application support with embedded Tomcat
- `spring-boot-starter-actuator` - Production-ready features (health checks, metrics, etc.)
- `spring-boot-devtools` - Development-time features (hot reload, auto-restart)
- `spring-boot-starter-test` - Testing framework with JUnit, Mockito, AssertJ

### Expected Development Patterns
As this is a Spring Boot 3.x application, follow these conventions:
- Place REST controllers in `com.biryuzabear.subair.controller`
- Place service layer classes in `com.biryuzabear.subair.service`
- Place repository/DAO classes in `com.biryuzabear.subair.repository`
- Place domain models in `com.biryuzabear.subair.model` or `com.biryuzabear.subair.entity`
- Place DTOs in `com.biryuzabear.subair.dto`
- Place configuration classes in `com.biryuzabear.subair.config`

### Maven Wrapper
The project uses Maven Wrapper (mvnw/mvnw.cmd), so developers don't need to install Maven separately. Always use `./mvnw` (Linux/Mac) or `mvnw.cmd` (Windows) instead of `mvn`.
