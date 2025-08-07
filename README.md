# Building Microservices Architecture - Complete Learning Project

A comprehensive hands-on learning project that demonstrates the evolution from monolithic architecture to advanced microservices with monitoring, logging, and DevOps practices.

## 📚 Project Overview

This repository contains a complete learning journey through microservices architecture, starting from basic concepts and progressing to advanced implementations with monitoring, logging, and containerization.

## 🏗️ Architecture Evolution

### Day 1: Microservice Design Patterns
- **Monolithic Banking Application**: Traditional single-tier architecture
- **Design Pattern Analysis**: Understanding when and how to break down monoliths
- **Key Concepts**: Service boundaries, domain-driven design, and architectural patterns

**Projects:**
- `day1/bank-monolith/` - Monolithic banking application
- `day1/monolithbank/` - Alternative monolithic implementation

### Day 2: Building Microservices
- **Basic Microservices**: Core banking services with Spring Boot
- **Service Discovery**: Eureka server for service registration
- **API Gateway**: Centralized routing and security
- **Configuration Management**: Spring Cloud Config Server

**Projects:**
- `day2/microserives/` - Complete microservices banking application

**Services:**
- Config Server (Port 8888)
- Eureka Server (Port 8761)
- API Gateway (Port 8080)
- Customer Service (Port 8081)
- Account Service (Port 8082)
- Transaction Service (Port 8083)
- Web Client (Port 8090)

### Day 3: Microservice Deep Dive
- **Advanced Features**: Monitoring, logging, and enhanced security
- **Observability**: Prometheus, Grafana, and ELK stack integration
- **API Documentation**: Swagger aggregator for unified documentation
- **Notification Service**: Asynchronous communication patterns

**Projects:**
- `day3/bank-app-v2/` - Enhanced microservices with monitoring

**Additional Services:**
- Notification Service
- Swagger Aggregator
- Prometheus Monitoring
- Logstash Pipeline

### Day 4: Docker, Kubernetes & CI/CD
- **Containerization**: Docker implementation for all services
- **Orchestration**: Kubernetes deployment strategies
- **CI/CD Pipelines**: Automated testing and deployment
- **DevOps Practices**: Infrastructure as Code and automation

## 🚀 Quick Start

### Prerequisites
- Java 21
- Maven 3.6+
- Docker and Docker Compose
- MySQL 8.0
- Node.js (for some frontend components)

### Running the Applications

#### Day 2 - Basic Microservices
```bash
cd day2/microserives
docker-compose up -d
./start-services.bat  # Windows
# or
./start-services.sh   # Linux/Mac
```

#### Day 3 - Advanced Microservices
```bash
cd day3/bank-app-v2
docker-compose up -d
./start-services.bat  # Windows
# or
./start-services.sh   # Linux/Mac
```

### Access Points
- **Web Client**: http://localhost:8090
- **API Gateway**: http://localhost:8080
- **Eureka Dashboard**: http://localhost:8761
- **Swagger UI**: 
  - Customer Service: http://localhost:8081/swagger-ui.html
  - Account Service: http://localhost:8082/swagger-ui.html
  - Transaction Service: http://localhost:8083/swagger-ui.html
- **Prometheus**: http://localhost:9090
- **Grafana**: http://localhost:3000

## 🏦 Banking Application Features

### Core Functionality
- **Customer Management**: Create, read, update, delete customer profiles
- **Account Management**: Multiple account types (Savings, Checking)
- **Transaction Processing**: Deposits, withdrawals, transfers
- **Interest Calculation**: Automated quarterly interest processing
- **Security**: Role-based access control (Customer/Admin)

### Technical Features
- **Service Discovery**: Automatic service registration with Eureka
- **Load Balancing**: Client-side load balancing with Spring Cloud
- **Centralized Configuration**: Externalized configuration management
- **API Documentation**: OpenAPI 3.0 with Swagger UI
- **Caching**: Redis-based caching for improved performance
- **Batch Processing**: Spring Batch for scheduled operations
- **Monitoring**: Health checks, metrics, and distributed tracing
- **Logging**: Centralized logging with ELK stack

## 📊 Database Architecture

The application uses a polyglot persistence approach with separate databases for each service:

- `banking_customers` - Customer data
- `banking_accounts` - Account and balance information
- `banking_transactions` - Transaction history

## 🔧 API Endpoints

### Customer Service
- `POST /api/customers` - Create customer
- `GET /api/customers/{id}` - Get customer by ID
- `GET /api/customers` - Get all customers (Admin only)
- `PUT /api/customers/{id}` - Update customer
- `DELETE /api/customers/{id}` - Delete customer (Admin only)

### Account Service
- `POST /api/accounts` - Create account
- `GET /api/accounts/{id}` - Get account by ID
- `GET /api/accounts/customer/{customerId}` - Get accounts by customer
- `PUT /api/accounts/{accountNumber}/balance` - Update balance
- `POST /api/accounts/interest/apply` - Apply quarterly interest (Admin only)

### Transaction Service
- `POST /api/transactions/deposit` - Deposit money
- `POST /api/transactions/withdraw` - Withdraw money
- `POST /api/transactions/transfer` - Transfer money
- `GET /api/transactions/account/{accountNumber}` - Get transactions by account

## 📚 Learning Materials

### Documentation
- `Architecting Microservices v16-Nov 24.xlsx` - Comprehensive architecture guide
- `day1/1. MicroService Design Pattern.docx` - Design pattern fundamentals
- `day2/2 Building MicroService.docx` - Microservices implementation guide
- `day3/3 MicroService Deep Dive.docx` - Advanced microservices concepts
- `day4/4 Docker K8s CICD.docx` - Containerization and DevOps practices

### Extras
The `Extras/` directory contains additional learning resources:
- Microservice design patterns and best practices
- API protocols and communication patterns
- Spring Boot annotations and configurations
- System design roadmaps and architecture styles
- DevOps tools and practices
- Performance optimization strategies

## 🛠️ Technology Stack

### Backend
- **Java 21** - Programming language
- **Spring Boot 3.5.4** - Application framework
- **Spring Cloud** - Microservices framework
- **Spring Security** - Authentication and authorization
- **Spring Batch** - Batch processing
- **Spring Cache** - Caching abstraction

### Database & Storage
- **MySQL 8.0** - Primary database
- **Redis** - Caching layer

### Service Discovery & Configuration
- **Eureka Server** - Service discovery
- **Spring Cloud Config** - Configuration management

### API & Documentation
- **Spring Cloud Gateway** - API gateway
- **Swagger/OpenAPI 3** - API documentation
- **Feign Client** - Service-to-service communication

### Monitoring & Observability
- **Spring Boot Actuator** - Application monitoring
- **Prometheus** - Metrics collection
- **Grafana** - Metrics visualization
- **ELK Stack** - Logging and analysis

### Containerization & Orchestration
- **Docker** - Containerization
- **Docker Compose** - Multi-container orchestration
- **Kubernetes** - Container orchestration (Day 4)

## 🔍 Monitoring & Observability

### Health Checks
All services expose health endpoints at `/actuator/health`

### Metrics
- Application metrics via Spring Boot Actuator
- Custom business metrics
- Prometheus integration for metrics collection

### Logging
- Structured logging with Logback
- Centralized log aggregation with ELK stack
- Distributed tracing for request tracking

## 🚀 Deployment

### Docker Deployment
```bash
# Build and run with Docker Compose
docker-compose up -d

# Scale services
docker-compose up -d --scale customer-service=3
```

### Kubernetes Deployment (Day 4)
- YAML manifests for all services
- Service mesh integration
- Horizontal Pod Autoscaling
- Ingress controllers for external access

## 🤝 Contributing

This is a learning project. Feel free to:
- Experiment with different architectural patterns
- Add new features or services
- Improve documentation
- Share your learnings and improvements

## 📝 License

This project is for educational purposes. Use it to learn and understand microservices architecture concepts.

## 🎯 Learning Objectives

By completing this project, you will understand:

1. **Monolithic vs Microservices**: When to use each approach
2. **Service Design**: Domain-driven design and service boundaries
3. **Service Communication**: Synchronous and asynchronous patterns
4. **Service Discovery**: Automatic service registration and discovery
5. **Configuration Management**: Centralized configuration strategies
6. **Security**: Authentication, authorization, and API security
7. **Monitoring**: Health checks, metrics, and observability
8. **Containerization**: Docker and Kubernetes deployment
9. **DevOps**: CI/CD pipelines and automation
10. **Best Practices**: Microservices design patterns and anti-patterns

---

**Happy Learning! 🚀**