# ContactManager Spring Boot Application
## Technical Report

**Author:** Technical Documentation Team  
**Date:** June 2023  
**Version:** 1.0

---

## Abstract

This comprehensive technical report provides an in-depth analysis of the ContactManager Spring Boot application developed by Suman Kumar Chand. The ContactManager application is a full-featured web-based contact management system that implements complete CRUD (Create, Read, Update, Delete) operations for managing contacts and user accounts. The application incorporates robust user authentication and authorization mechanisms for enhanced security.

The report details the application's architecture, tech stack, database schema, module implementation, user interface design, security features, and deployment considerations. Each component is thoroughly examined to provide a complete understanding of the system's functionality and design decisions.

The ContactManager application demonstrates effective use of modern Java technologies, including Spring Boot, Spring Data JPA, Hibernate, and Oracle SQL, alongside front-end technologies such as HTML, CSS, Bootstrap, and JavaScript. The integration of features like Google OAuth and email-based password recovery showcases the application's professional-grade security implementation.

This document serves as both a comprehensive reference for the application's technical aspects and a guide for future development, maintenance, and enhancement of the system.

---

## Table of Contents

1. **Introduction**
   - 1.1 Project Overview
   - 1.2 Background
   - 1.3 Project Objectives
   - 1.4 Document Purpose and Scope

2. **Technology Stack**
   - 2.1 Java
   - 2.2 Spring Framework Overview
   - 2.3 Spring Boot
   - 2.4 Spring Data JPA
   - 2.5 Hibernate ORM
   - 2.6 Oracle SQL Database
   - 2.7 Front-end Technologies
   - 2.8 Development Tools and Environments

3. **Architecture and Design**
   - 3.1 System Architecture
   - 3.2 Entity-Relationship Diagram
   - 3.3 Class Diagrams
   - 3.4 Sequence Diagrams
   - 3.5 Design Patterns Implementation

4. **Database Schema**
   - 4.1 Database Design Philosophy
   - 4.2 Table Structure
   - 4.3 Relationships and Constraints
   - 4.4 Indexing Strategy
   - 4.5 Data Access Layer

5. **User Authentication and Authorization Module**
   - 5.1 Authentication Flow
   - 5.2 Spring Security Configuration
   - 5.3 User Registration Process
   - 5.4 Login Implementation
   - 5.5 Google OAuth Integration
   - 5.6 Password Reset Functionality
   - 5.7 Authorization Rules

6. **User Management Module**
   - 6.1 User Profile Management
   - 6.2 User CRUD Operations
   - 6.3 Profile Update Features
   - 6.4 Password Management
   - 6.5 User Data Validation

7. **Contact Management Module**
   - 7.1 Contact Data Model
   - 7.2 Contact CRUD Operations
   - 7.3 Favorite Contacts Feature
   - 7.4 Contact Listing and Pagination
   - 7.5 Data Validation and Error Handling

8. **Dynamic Search Functionality**
   - 8.1 Search Implementation Overview
   - 8.2 Query Construction
   - 8.3 Real-time Search Feature
   - 8.4 Search Optimization Techniques
   - 8.5 User Interface Integration

9. **UI/UX Design**
   - 9.1 Design Principles and Guidelines
   - 9.2 Responsive Design Implementation
   - 9.3 Desktop Interface Analysis
   - 9.4 Mobile Interface Analysis
   - 9.5 User Experience Considerations

10. **Code Structure**
    - 10.1 Package Organization
    - 10.2 Controllers Implementation
    - 10.3 Service Layer
    - 10.4 Repository Layer
    - 10.5 Entity Classes
    - 10.6 Utility Classes

11. **API Documentation**
    - 11.1 RESTful API Design
    - 11.2 Endpoint Documentation
    - 11.3 Request/Response Formats
    - 11.4 API Usage Examples
    - 11.5 Error Handling

12. **Security Implementation**
    - 12.1 Security Architecture
    - 12.2 Authentication Mechanisms
    - 12.3 CSRF Protection
    - 12.4 Session Management
    - 12.5 Data Encryption
    - 12.6 Security Best Practices

13. **Testing Strategy**
    - 13.1 Testing Approach
    - 13.2 Unit Testing
    - 13.3 Integration Testing
    - 13.4 User Interface Testing
    - 13.5 Security Testing
    - 13.6 Test Results and Analysis

14. **Deployment Guide**
    - 14.1 Environment Setup
    - 14.2 Deployment Process
    - 14.3 Docker Configuration
    - 14.4 Production Considerations
    - 14.5 Monitoring and Logging

15. **Performance Analysis**
    - 15.1 Performance Metrics
    - 15.2 Bottleneck Identification
    - 15.3 Database Query Optimization
    - 15.4 Caching Strategy
    - 15.5 Optimization Recommendations

16. **Future Enhancements**
    - 16.1 Feature Roadmap
    - 16.2 Scalability Considerations
    - 16.3 Technology Upgrades
    - 16.4 Integration Opportunities
    - 16.5 User Experience Improvements

17. **Conclusion**
    - 17.1 Project Summary
    - 17.2 Lessons Learned
    - 17.3 Final Recommendations

18. **References**

19. **Appendices**
    - Appendix A: Glossary
    - Appendix B: Configuration Files
    - Appendix C: API Reference
    - Appendix D: Database Scripts

## List of Figures

- Figure 3.1: ContactManager System Architecture
- Figure 3.2: Entity-Relationship Diagram
- Figure 3.3: Class Diagram - User Authentication
- Figure 3.4: Class Diagram - Contact Management
- Figure 3.5: Sequence Diagram - User Registration
- Figure 3.6: Sequence Diagram - Contact Creation
- Figure 4.1: Database Schema Diagram
- Figure 5.1: Authentication Flow Diagram
- Figure 5.2: Password Reset Flow
- Figure 9.1: Desktop Home Page
- Figure 9.2: Mobile Home Page
- Figure 9.3: Desktop Login Page
- Figure 9.4: Mobile Login Page
- Figure 9.5: Desktop Contact List
- Figure 9.6: Mobile Contact List
- Figure 9.7: Desktop Profile Page
- Figure 9.8: Mobile Profile Page
- Figure 14.1: Deployment Architecture

---

# Chapter 1: Introduction

## 1.1 Project Overview

The ContactManager is a comprehensive web application developed using Spring Boot that provides users with a robust platform for managing their contacts. Built as a personal project by Suman Kumar Chand, the application demonstrates enterprise-level design patterns and implementation practices while offering a complete set of contact management features.

ContactManager provides a secure, user-friendly interface for storing, organizing, and retrieving contact information. The system allows users to register accounts, authenticate using traditional credentials or Google OAuth, manage their profiles, and perform all fundamental CRUD (Create, Read, Update, Delete) operations on their contacts.

The application incorporates responsive design principles, ensuring optimal user experience across both desktop and mobile platforms. It features an intuitive interface with real-time search functionality, the ability to mark contacts as favorites, and comprehensive user account management capabilities.

## 1.2 Background

In the modern digital landscape, effective contact management is essential for both personal and professional efficiency. While numerous contact management solutions exist, many lack the balance between simplicity and comprehensive features, or they fail to provide adequate security measures for protecting sensitive contact information.

The ContactManager application was developed to address these gaps by creating a self-contained, secure platform that prioritizes both functionality and user experience. By implementing the application as a Spring Boot project, the developer demonstrates the effective use of modern Java technologies for building robust web applications.

The application serves as an exemplary implementation of the Spring Framework ecosystem, showcasing best practices in areas such as:
- Layered architecture with clear separation of concerns
- Security implementation with multiple authentication options
- Data persistence using JPA and Hibernate
- Modern, responsive front-end design
- RESTful API design principles

## 1.3 Project Objectives

The ContactManager project was designed with the following key objectives:

1. **Create a Comprehensive Contact Management System**: Develop a full-featured application that enables users to store, retrieve, update, and delete contact information efficiently.

2. **Implement Robust Security**: Ensure the application provides secure user authentication and authorization with multiple login options, including traditional username/password authentication and Google OAuth integration.

3. **Demonstrate Modern Java Development Practices**: Showcase the effective implementation of Spring Boot, Spring Data JPA, Hibernate, and other Java technologies in building a web application.

4. **Provide an Intuitive User Experience**: Design a responsive, user-friendly interface that works seamlessly across both desktop and mobile devices.

5. **Incorporate Advanced Features**: Implement functionality such as dynamic search, favorite contacts, profile management, and password recovery to enhance the application's utility.

6. **Ensure Data Persistence**: Develop a well-structured database schema using Oracle SQL to securely and efficiently store user and contact information.

7. **Practice Software Engineering Best Practices**: Adhere to design patterns, coding standards, and architectural principles that promote maintainability, scalability, and security.

## 1.4 Document Purpose and Scope

This technical report serves as a comprehensive documentation of the ContactManager Spring Boot application. It is intended for software developers, architects, and technical stakeholders who seek to understand the application's design, implementation, and functionality in detail.

The document covers:

- A detailed analysis of the technology stack and its implementation
- The architectural design, including database schema and system components
- A comprehensive breakdown of each functional module
- Security implementation details and best practices
- User interface design considerations and implementation
- Code structure and organization
- API documentation and usage examples
- Testing strategies and methodologies
- Deployment guidelines and considerations
- Performance analysis and optimization recommendations
- Potential future enhancements and scalability considerations

By providing this level of technical detail, the document aims to:

1. Serve as a reference for maintaining and enhancing the application
2. Provide insights into the design decisions and implementation strategies
3. Demonstrate the application of modern Java technologies in a real-world project
4. Offer guidance for similar application development efforts

The scope of this document is limited to the technical aspects of the ContactManager application and does not cover business aspects such as market analysis, user adoption strategies, or commercial considerations.

---

# Chapter 2: Technology Stack

## 2.1 Java

Java serves as the foundational programming language for the ContactManager application. As one of the most widely used object-oriented programming languages in enterprise application development, Java provides several advantages that make it well-suited for this project:

### 2.1.1 Java Version and Features

The ContactManager application is built using Java 11, which offers numerous improvements over previous versions, including:
- Enhanced performance through optimized string concatenation
- Improved garbage collection mechanisms
- Local variable type inference with the 'var' keyword
- Collection factory methods for easier instantiation of immutable collections
- Improved HTTP client

### 2.1.2 Object-Oriented Design

Java's robust object-oriented programming model allows for:
- Encapsulation of data and behavior within well-defined classes
- Inheritance for code reuse and specialization
- Polymorphism for flexible interface implementations
- Abstraction to hide implementation details

These features facilitate the implementation of complex business logic in a maintainable, modular manner, which is critical for a multi-faceted application like ContactManager.

### 2.1.3 Platform Independence

Java's "write once, run anywhere" capability ensures that the application can be deployed across different operating systems without modification. This cross-platform compatibility extends the potential deployment options for the ContactManager application.

### 2.1.4 Memory Management

Java's automatic memory management through garbage collection reduces the risk of memory leaks and improves application stability. This is particularly important for a web application that needs to handle multiple concurrent user sessions reliably.

## 2.2 Spring Framework Overview

The Spring Framework is a comprehensive programming and configuration model for modern Java-based enterprise applications. ContactManager leverages the Spring Framework as its backbone, benefiting from its modular design and extensive features.

### 2.2.1 Inversion of Control and Dependency Injection

At the core of Spring is the Inversion of Control (IoC) principle, implemented through Dependency Injection (DI). This architectural approach:
- Reduces coupling between application components
- Enhances testability by allowing mock implementations
- Promotes modular design and separation of concerns
- Simplifies configuration management

The ContactManager application extensively uses Spring's DI capabilities to create loosely coupled components that interact through well-defined interfaces.

### 2.2.2 Aspect-Oriented Programming

Spring's support for Aspect-Oriented Programming (AOP) allows for:
- Centralized handling of cross-cutting concerns like logging and security
- Declarative transaction management
- Clean separation of business logic from system-level services

In ContactManager, AOP is particularly valuable for implementing consistent security checks, logging, and performance monitoring across different parts of the application.

### 2.2.3 Spring MVC

The Spring MVC (Model-View-Controller) framework provides a structured approach to building web applications:
- Clear separation between the application's data model, user interface, and control logic
- Flexible view technologies with support for Thymeleaf (used in ContactManager)
- Powerful data binding and validation capabilities
- Seamless integration with other Spring components

This architectural pattern helps organize the application's code into logical components, making it easier to develop, test, and maintain.

## 2.3 Spring Boot

Spring Boot extends the Spring Framework by providing a streamlined configuration approach and embedded server capabilities, significantly reducing the development effort required to create production-ready applications.

### 2.3.1 Auto-Configuration

Spring Boot's auto-configuration feature automatically configures Spring and third-party libraries based on:
- Dependencies present in the classpath
- Environment properties
- User-defined beans

This reduces boilerplate configuration code and accelerates development. In ContactManager, auto-configuration is leveraged to:
- Set up the embedded Tomcat server
- Configure Spring Data JPA with Hibernate
- Establish security settings
- Integrate view templates

### 2.3.2 Embedded Web Server

ContactManager utilizes Spring Boot's embedded Tomcat server, which:
- Eliminates the need for external application server deployment
- Simplifies the development and testing process
- Enables the application to be packaged as a standalone JAR file
- Provides consistent runtime environment across development and production

### 2.3.3 Spring Boot Starters

The application leverages several Spring Boot starter dependencies that bundle together related dependencies for specific functionality:
- `spring-boot-starter-web`: Core web functionality, including Spring MVC
- `spring-boot-starter-data-jpa`: Data access layer with Spring Data and Hibernate
- `spring-boot-starter-security`: Authentication and authorization capabilities
- `spring-boot-starter-thymeleaf`: Integration with Thymeleaf template engine
- `spring-boot-starter-mail`: Email functionality for password recovery

These starters ensure compatible dependency versions and reduce configuration complexity.

### 2.3.4 Externalized Configuration

Spring Boot's support for externalized configuration through `application.properties` allows the ContactManager application to:
- Configure database connection parameters
- Set security properties
- Define email server settings
- Customize application behavior without code changes

## 2.4 Spring Data JPA

Spring Data JPA simplifies data access by reducing the boilerplate code required for implementing data repositories. In ContactManager, it serves as the bridge between the application's domain model and the database.

### 2.4.1 Repository Abstraction

The ContactManager application defines repository interfaces that extend Spring Data's base repositories:
- `JpaRepository` for basic CRUD operations
- `PagingAndSortingRepository` for pagination and sorting capabilities

These interfaces automatically provide implementations for common data access methods, significantly reducing the amount of code that needs to be written.

### 2.4.2 Method Name Query Generation

Spring Data JPA's ability to generate queries based on method names is leveraged in ContactManager for:
- Finding contacts by specific properties (e.g., `findByFirstNameContaining`)
- Retrieving user accounts by email or username
- Filtering contacts by favorite status

This feature reduces the need for manual query writing while maintaining type safety and consistency.

### 2.4.3 Custom Queries

For more complex data access requirements, ContactManager uses:
- `@Query` annotations for custom JPQL (Java Persistence Query Language) queries
- Native SQL queries for database-specific optimizations
- `Specification` interface for dynamic query construction in the search functionality

### 2.4.4 Transaction Management

Spring Data JPA's integration with Spring's transaction management ensures data integrity through:
- Declarative transaction boundaries with `@Transactional` annotations
- Consistent transaction propagation behavior
- Automatic rollback on exceptions

## 2.5 Hibernate ORM

Hibernate serves as the Object-Relational Mapping (ORM) implementation for ContactManager, providing a bridge between the object-oriented domain model and the relational database.

### 2.5.1 Entity Mapping

The application uses Hibernate's annotations to map Java classes to database tables:
- `@Entity` to define entity classes
- `@Table` to specify table names and constraints
- `@Column` to configure column properties
- `@Id` and `@GeneratedValue` for primary key management

These mappings allow the application to work with Java objects while Hibernate handles the translation to and from SQL.

### 2.5.2 Relationship Mapping

ContactManager models complex relationships between entities using Hibernate's relationship annotations:
- `@OneToMany` for the relationship between users and contacts
- `@ManyToOne` for the inverse relationship from contacts to users
- Cascade operations to propagate changes through related entities

### 2.5.3 Lazy Loading and Fetch Strategies

The application optimizes data access patterns through:
- Lazy loading of collections to avoid unnecessary data retrieval
- Strategic fetch joins for scenarios requiring eager loading
- Named entity graphs for specific query use cases

### 2.5.4 Hibernate Validation

Bean Validation (JSR-380) is implemented through Hibernate Validator to enforce data integrity at the domain model level:
- `@NotNull`, `@Size`, `@Email` and other constraints on entity properties
- Custom validation annotations for specific business rules
- Validation groups to apply different validation rules in different contexts

## 2.6 Oracle SQL Database

The ContactManager application uses Oracle SQL as its relational database management system, providing a robust foundation for data persistence.

### 2.6.1 Database Configuration

The application connects to Oracle using the following configuration in `application.properties`:
```
spring.datasource.url=jdbc:oracle:thin:@//MSI:1521/orcl
spring.datasource.driver-class-name=oracle.jdbc.driver.OracleDriver
spring.datasource.username=...
spring.datasource.password=...
```

### 2.6.2 Schema Management

Hibernate's schema generation capabilities are used to:
- Validate the database schema against the entity model
- Update the schema automatically during development
- Generate DDL scripts for controlled production deployments

### 2.6.3 Oracle-Specific Features

The application leverages several Oracle-specific features:
- Sequence generators for primary key values
- Oracle's full-text search capabilities for improved search performance
- Advanced data types for storing large objects like profile images

### 2.6.4 Connection Pooling

HikariCP is used as the connection pool implementation to:
- Efficiently manage database connections
- Monitor connection health and performance
- Optimize connection lifecycle for high-throughput scenarios

## 2.7 Front-end Technologies

The ContactManager application employs a combination of front-end technologies to create a responsive, interactive user interface.

### 2.7.1 HTML5 and CSS3

The application's user interface is built using modern HTML5 and CSS3:
- Semantic HTML elements for improved structure and accessibility
- CSS3 features like flexbox and grid for responsive layouts
- Media queries to adapt the interface to different screen sizes

### 2.7.2 Bootstrap Framework

Bootstrap 4 is utilized to:
- Provide a consistent, responsive grid system
- Style UI components with a modern, professional appearance
- Implement responsive navigation and layout patterns
- Reduce custom CSS requirements through utility classes

### 2.7.3 JavaScript and jQuery

Client-side interactivity is implemented using:
- Vanilla JavaScript for DOM manipulation and event handling
- jQuery for simplified AJAX requests and DOM traversal
- Form validation and dynamic UI updates
- Modal dialogs for contact details and confirmation prompts

### 2.7.4 Thymeleaf Template Engine

Thymeleaf serves as the server-side template engine, offering:
- Natural templating with valid HTML that can be viewed in browsers without a server
- Integration with Spring's security tag library for conditional rendering based on authentication
- Expression language for dynamic content generation
- Fragment-based composition for reusable components

The template engine facilitates the generation of dynamic HTML content while maintaining a clean separation between presentation and business logic.

## 2.8 Development Tools and Environments

The ContactManager application was developed using a comprehensive set of tools and environments.

### 2.8.1 Spring Tool Suite (STS)

Spring Tool Suite, an Eclipse-based IDE, was the primary development environment, providing:
- Specialized tools for Spring application development
- Enhanced code completion and navigation for Spring components
- Integrated support for Maven dependency management
- Built-in deployment to the embedded application server

### 2.8.2 Maven Build Tool

Maven manages the project's build process and dependencies:
- Declarative POM (Project Object Model) for project configuration
- Transitive dependency resolution
- Standardized build lifecycle
- Profile-based configuration for different environments

### 2.8.3 Git Version Control

The application's source code is managed using Git:
- Feature branch development workflow
- Commit history for tracking changes
- GitHub repository for code sharing and collaboration

### 2.8.4 Testing Tools

Development was supported by a suite of testing tools:
- JUnit 5 for unit testing
- Mockito for mocking dependencies
- Spring Test for integration testing
- Selenium for UI automation testing

### 2.8.5 Development and Production Environments

The application is designed to operate in different environments:
- Local development environment with H2 in-memory database for rapid iteration
- Testing environment with test Oracle instance
- Production environment with full Oracle database implementation

Each environment is configured using Spring profiles to activate the appropriate settings and dependencies. 

---

# Chapter 3: Architecture and Design

## 3.1 System Architecture

The ContactManager application follows a multi-layered architecture pattern that promotes separation of concerns and maintainability. This architectural approach organizes the application into distinct layers, each with specific responsibilities and well-defined interfaces for communication with other layers.

### 3.1.1 Architectural Layers

The application is structured into the following key layers:

1. **Presentation Layer**
   - Handles HTTP requests and responses
   - Renders views using Thymeleaf templates
   - Implements controllers for different functional areas
   - Manages user input validation and error handling

2. **Service Layer**
   - Implements business logic and rules
   - Coordinates transactions and cross-cutting concerns
   - Provides an abstraction layer between controllers and repositories
   - Handles security and validation logic

3. **Data Access Layer**
   - Manages database interactions through Spring Data JPA repositories
   - Implements custom queries and data retrieval logic
   - Handles mapping between entities and database tables
   - Manages transaction boundaries

4. **Domain Model Layer**
   - Defines entity classes that represent business concepts
   - Implements validation constraints on entity properties
   - Establishes relationships between entities
   - Encapsulates domain-specific behavior

### 3.1.2 Cross-Cutting Concerns

In addition to the primary architectural layers, the application addresses several cross-cutting concerns:

1. **Security**
   - Authentication and authorization through Spring Security
   - Session management and CSRF protection
   - Password encryption and secure storage
   - OAuth integration for Google authentication

2. **Exception Handling**
   - Global exception handling through `@ControllerAdvice`
   - Custom exception types for different error scenarios
   - Consistent error response format
   - User-friendly error messages and pages

3. **Logging**
   - Comprehensive logging using SLF4J and Logback
   - Different log levels for development and production
   - Contextual logging with request information
   - Performance monitoring through timing logs

4. **Configuration**
   - Externalized configuration in `application.properties`
   - Environment-specific settings through Spring profiles
   - Feature flags for controlled feature rollout
   - Runtime configuration management

### 3.1.3 Component Interaction

Figure 3.1 illustrates the high-level system architecture and the interaction between components.

**Figure 3.1: ContactManager System Architecture**
```
┌─────────────────────────────────────────────────────────────────────┐
│                           Client Browser                             │
└───────────────────────────────────┬─────────────────────────────────┘
                                    │ HTTP/HTTPS
                                    ▼
┌─────────────────────────────────────────────────────────────────────┐
│                        Spring Boot Application                       │
│                                                                     │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │                      Presentation Layer                          │ │
│ │                                                                 │ │
│ │ ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐  │ │
│ │ │  Home Controller │  │ User Controller  │  │Contact Controller│  │ │
│ │ └────────┬────────┘  └────────┬────────┘  └────────┬────────┘  │ │
│ └──────────┼─────────────────────┼─────────────────────┼──────────┘ │
│            │                     │                     │            │
│ ┌──────────┼─────────────────────┼─────────────────────┼──────────┐ │
│ │                         Service Layer                            │ │
│ │                                                                 │ │
│ │ ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐  │ │
│ │ │   User Service   │  │ Contact Service  │  │  Email Service   │  │ │
│ │ └────────┬────────┘  └────────┬────────┘  └────────┬────────┘  │ │
│ └──────────┼─────────────────────┼─────────────────────┼──────────┘ │
│            │                     │                     │            │
│ ┌──────────┼─────────────────────┼─────────────────────┼──────────┐ │
│ │                       Data Access Layer                          │ │
│ │                                                                 │ │
│ │ ┌─────────────────┐  ┌─────────────────┐                       │ │
│ │ │  User Repository │  │Contact Repository│                       │ │
│ │ └────────┬────────┘  └────────┬────────┘                       │ │
│ └──────────┼─────────────────────┼───────────────────────────────┘ │
│            │                     │                                  │
│ ┌──────────┼─────────────────────┼───────────────────────────────┐ │
│ │                       Domain Model Layer                        │ │
│ │                                                                 │ │
│ │ ┌─────────────────┐  ┌─────────────────┐                       │ │
│ │ │    User Entity   │  │  Contact Entity  │                       │ │
│ │ └─────────────────┘  └─────────────────┘                       │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│                                                                     │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │                     Cross-Cutting Concerns                       │ │
│ │                                                                 │ │
│ │   ┌─────────┐  ┌────────────┐  ┌─────────┐  ┌────────────┐     │ │
│ │   │ Security │  │ Exception  │  │ Logging │  │Configuration│     │ │
│ │   │         │  │  Handling  │  │         │  │            │     │ │
│ │   └─────────┘  └────────────┘  └─────────┘  └────────────┘     │ │
│ └─────────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────┬─────────────────────────────────┘
                                  │ JDBC
                                  ▼
┌─────────────────────────────────────────────────────────────────────┐
│                         Oracle SQL Database                          │
└─────────────────────────────────────────────────────────────────────┘
```

This architecture follows the principles of:
- **Separation of Concerns**: Each layer has a specific responsibility
- **Loose Coupling**: Components interact through well-defined interfaces
- **High Cohesion**: Related functionality is grouped together
- **Single Responsibility**: Each component has a focused purpose

## 3.2 Entity-Relationship Diagram

The data model of the ContactManager application is designed to efficiently store and retrieve user and contact information while maintaining the integrity of relationships between entities. The Entity-Relationship (ER) diagram illustrates the database schema and the relationships between entities.

### 3.2.1 ER Diagram

Figure 3.2 shows the Entity-Relationship diagram for the ContactManager application.

**Figure 3.2: Entity-Relationship Diagram**

![E-R Diagram](https://github.com/user-attachments/assets/803db8ec-d297-4e4b-b746-8d9cfbcc5efe)

### 3.2.2 Entity Descriptions

The ER diagram reveals the following key entities and their relationships:

1. **User Entity**
   - Contains user account information (username, email, password)
   - Stores profile details (name, profile image, date of birth, phone)
   - Tracks account status (enabled, role)
   - Includes verification tokens for email verification and password reset

2. **Contact Entity**
   - Stores contact information (name, email, phone, work, etc.)
   - Contains contact image data
   - Includes a favorite flag for marking contacts as favorites
   - Maintains a description field for additional notes

3. **Relationships**
   - A User has many Contacts (one-to-many relationship)
   - Each Contact belongs to exactly one User (many-to-one relationship)

### 3.2.3 Key Design Decisions

Several important design decisions are reflected in the ER diagram:

1. **User-Owned Contacts**: Contacts are always associated with a specific user, ensuring proper data isolation and security.

2. **Cascading Operations**: The relationship between User and Contact is configured with cascading operations, so when a user is deleted, their contacts are automatically removed.

3. **Contact Favoriting**: The favorite flag in the Contact entity allows for efficient filtering of favorite contacts without requiring a separate join table.

4. **Image Storage**: Both User and Contact entities include fields for storing profile images, allowing for personalization.

## 3.3 Class Diagrams

The class structure of the ContactManager application is designed to implement the layered architecture while promoting maintainability and extensibility. The following class diagrams illustrate the key components of the application and their relationships.

### 3.3.1 User Authentication Class Diagram

Figure 3.3 shows the classes involved in the user authentication and management functionality.

**Figure 3.3: Class Diagram - User Authentication**
```
┌─────────────────────┐     ┌──────────────────────┐
│    UserController   │     │  UserDetailsService  │
├─────────────────────┤     ├──────────────────────┤
│ +register()         │     │ +loadUserByUsername()│
│ +processRegister()  │────►│                      │
│ +login()            │     └──────────┬───────────┘
│ +forgotPassword()   │                │
│ +resetPassword()    │                │
└─────────┬───────────┘                │
          │                            │
          ▼                            ▼
┌─────────────────────┐     ┌──────────────────────┐
│     UserService     │     │  CustomUserDetails   │
├─────────────────────┤     ├──────────────────────┤
│ +registerUser()     │     │ -user: User          │
│ +checkEmailExists() │     │ +getAuthorities()    │
│ +findUserByEmail()  │◄────│ +getPassword()       │
│ +updateProfile()    │     │ +getUsername()       │
│ +saveUser()         │     │ +isAccountNonLocked()│
└─────────┬───────────┘     └──────────────────────┘
          │
          │
          ▼
┌─────────────────────┐     ┌──────────────────────┐
│   UserRepository    │     │        User          │
├─────────────────────┤     ├──────────────────────┤
│ +findByEmail()      │     │ -id: Long            │
│ +findByUsername()   │◄────│ -name: String        │
│ +save()             │     │ -email: String       │
│ +findById()         │     │ -password: String    │
└─────────────────────┘     │ -username: String    │
                            │ -role: String        │
                            │ -enabled: boolean    │
                            │ -imageUrl: String    │
                            │ -contacts: List      │
                            └──────────────────────┘
```

### 3.3.2 Contact Management Class Diagram

Figure 3.4 illustrates the classes involved in contact management functionality.

**Figure 3.4: Class Diagram - Contact Management**
```
┌─────────────────────┐     ┌──────────────────────┐
│  ContactController  │     │   SearchController   │
├─────────────────────┤     ├──────────────────────┤
│ +showContacts()     │     │ +search()            │
│ +addContactForm()   │     │ +processSearch()     │
│ +processContact()   │     └──────────┬───────────┘
│ +showContactDetail()│                │
│ +deleteContact()    │                │
│ +updateContact()    │                │
│ +favoriteContacts() │                │
└─────────┬───────────┘                │
          │                            │
          ▼                            ▼
┌─────────────────────┐     ┌──────────────────────┐
│   ContactService    │     │    SearchService     │
├─────────────────────┤     ├──────────────────────┤
│ +saveContact()      │     │ +searchContacts()    │
│ +findContactsByUser()│◄───│ +buildSpecification()│
│ +findById()         │     └──────────────────────┘
│ +deleteContact()    │
│ +findFavorites()    │
└─────────┬───────────┘
          │
          │
          ▼
┌─────────────────────┐     ┌──────────────────────┐
│ ContactRepository   │     │       Contact        │
├─────────────────────┤     ├──────────────────────┤
│ +findByUser()       │     │ -cId: Long           │
│ +findByUserAndId()  │◄────│ -name: String        │
│ +findById()         │     │ -secondName: String  │
│ +save()             │     │ -work: String        │
│ +delete()           │     │ -email: String       │
│ +findByUserAndFavorite() │ -phone: String        │
└─────────────────────┘     │ -image: String       │
                            │ -description: String │
                            │ -favorite: boolean   │
                            │ -user: User          │
                            └──────────────────────┘
```

### 3.3.3 Security Configuration Class Diagram

The security configuration is a critical component of the application, defining authentication providers, access rules, and secure communication requirements.

```
┌─────────────────────────┐      ┌─────────────────────────┐
│  SecurityConfiguration  │      │   WebMvcConfiguration   │
├─────────────────────────┤      ├─────────────────────────┤
│ +configure(HttpSecurity)│      │ +addViewControllers()   │
│ +configure(AuthManager) │      │ +addResourceHandlers()  │
│ +passwordEncoder()      │      └─────────────────────────┘
│ +authenticationProvider()│
└──────────────┬──────────┘
               │
               ▼
┌─────────────────────────┐      ┌─────────────────────────┐
│ UserDetailsServiceImpl  │      │ OAuth2UserServiceImpl   │
├─────────────────────────┤      ├─────────────────────────┤
│ +loadUserByUsername()   │      │ +loadUser()             │
│ -userRepository         │      │ +processOAuthUser()     │
└─────────────────────────┘      └─────────────────────────┘
```

## 3.4 Sequence Diagrams

Sequence diagrams illustrate the interaction between components over time, helping to understand the flow of operations for key processes in the ContactManager application.

### 3.4.1 User Registration Sequence

Figure 3.5 shows the sequence of operations during the user registration process.

**Figure 3.5: Sequence Diagram - User Registration**
```
┌──────┐      ┌────────────────┐      ┌──────────────┐      ┌────────────────┐      ┌───────────┐
│Client│      │UserController  │      │UserService   │      │UserRepository  │      │EmailService│
└──┬───┘      └────────┬───────┘      └───────┬──────┘      └───────┬────────┘      └─────┬─────┘
   │                   │                      │                      │                      │
   │  GET /signup      │                      │                      │                      │
   │──────────────────►│                      │                      │                      │
   │                   │                      │                      │
   │  Registration Form│                      │                      │
   │◄──────────────────│                      │                      │
   │                   │                      │                      │
   │  POST /signup     │                      │                      │
   │  (user data)      │                      │                      │
   │──────────────────►│                      │                      │
   │                   │                      │                      │
   │                   │  checkEmailExists()  │                      │
   │                   │─────────────────────►│                      │
   │                   │                      │                      │
   │                   │                      │  findByEmail()       │                      │
   │                   │                      │─────────────────────►│                      │
   │                   │                      │                      │
   │                   │                      │  Result              │                      │
   │                   │                      │◄─────────────────────│                      │
   │                   │                      │                      │
   │                   │  Result              │                      │
   │                   │◄─────────────────────│                      │
   │                   │                      │                      │
   │                   │  registerUser()      │                      │
   │                   │─────────────────────►│                      │
   │                   │                      │                      │
   │                   │                      │  Encode Password     │                      │
   │                   │                      │─────────────────────▶│                      │
   │                   │                      │                      │
   │                   │                      │  save()              │                      │
   │                   │                      │─────────────────────►│                      │
   │                   │                      │                      │
   │                   │                      │  User Saved          │                      │
   │                   │                      │◄─────────────────────│                      │
   │                   │                      │                      │
   │                   │                      │  sendVerificationEmail()                    │
   │                   │                      │───────────────────────────────────────────►│
   │                   │                      │                      │
   │                   │  Success             │                      │
   │                   │◄─────────────────────│                      │
   │                   │                      │                      │
   │  Redirect to Login│                      │                      │
   │◄──────────────────│                      │                      │
   │                   │                      │                      │
```

### 3.4.2 Contact Creation Sequence

Figure 3.6 illustrates the sequence of operations when a user creates a new contact.

**Figure 3.6: Sequence Diagram - Contact Creation**
```
┌──────┐    ┌─────────────────┐    ┌────────────────┐    ┌──────────────────┐    ┌──────────┐
│Client│    │ContactController│    │ContactService  │    │ContactRepository │    │FileService│
└──┬───┘    └────────┬────────┘    └───────┬────────┘    └────────┬─────────┘    └────┬─────┘
   │                 │                     │                       │                   │
   │ GET /user/contacts/add                │                       │                   │
   │─────────────────►                     │                       │                   │
   │                 │                     │                       │                   │
   │ Add Contact Form│                     │                       │                   │
   │◄─────────────────                     │                       │                   │
   │                 │                     │                       │                   │
   │ POST /user/contacts/process           │                       │                   │
   │ (contact data + image)                │                       │                   │
   │─────────────────►                     │                       │                   │
   │                 │                     │                       │                   │
   │                 │ Get Current User    │                       │                   │
   │                 │─────────────────────                       │                   │
   │                 │                     │                       │                   │
   │                 │                     │                       │                   │
   │                 │                     │                       │                   │
   │                 │ Process Image       │                       │                   │
   │                 │───────────────────────────────────────────────────────────────►│
   │                 │                     │                       │                   │
   │                 │                     │                       │                   │
   │                 │ Image URL           │                       │                   │
   │                 │◄───────────────────────────────────────────────────────────────│
   │                 │                     │                       │                   │
   │                 │ saveContact()       │                       │                   │
   │                 │────────────────────►                       │                   │
   │                 │                     │                       │                   │
   │                 │                     │ Set User Reference    │                   │
   │                 │                     │────────────────────►  │                   │
   │                 │                     │                       │                   │
   │                 │                     │ save()                │                   │
   │                 │                     │────────────────────►  │                   │
   │                 │                     │                       │                   │
   │                 │                     │ Contact Saved         │                   │
   │                 │                     │◄────────────────────  │                   │
   │                 │                     │                       │                   │
   │                 │ Success             │                       │                   │
   │                 │◄────────────────────                       │                   │
   │                 │                     │                       │                   │
   │ Redirect to Contacts List             │                       │                   │
   │◄─────────────────                     │                       │                   │
   │                 │                     │                       │                   │
```

## 3.5 Design Patterns Implementation

The ContactManager application implements several design patterns to improve code organization, maintainability, and adherence to best practices.

### 3.5.1 Model-View-Controller (MVC) Pattern

The application follows the MVC pattern through Spring MVC:
- **Model**: Entity classes (User, Contact) represent the data model
- **View**: Thymeleaf templates provide the presentation layer
- **Controller**: Controller classes handle user requests and coordinate responses

This separation enhances maintainability by segregating presentation logic from business logic and data access.

### 3.5.2 Repository Pattern

The Repository pattern is implemented through Spring Data JPA repositories:
- Abstracts data access logic from business services
- Provides a collection-like interface for working with domain objects
- Centralizes query definitions and data access methods

### 3.5.3 Service Layer Pattern

The Service Layer pattern is used to:
- Encapsulate business logic in service classes
- Coordinate operations that span multiple repositories
- Manage transaction boundaries
- Implement validation and business rules

### 3.5.4 Dependency Injection Pattern

Spring's Dependency Injection is used throughout the application to:
- Inject dependencies rather than having components create them
- Promote loose coupling between components
- Facilitate testing through mock implementations
- Simplify configuration management

### 3.5.5 Observer Pattern

The Observer pattern is implemented for event handling:
- Registration events trigger email notifications
- Password reset events generate tokens and emails
- Profile update events may trigger cache invalidation

### 3.5.6 Facade Pattern

The Service layer implements the Facade pattern by:
- Providing a simplified interface to complex subsystems
- Hiding implementation details from controllers
- Coordinating multiple repositories and services

### 3.5.7 Data Transfer Object (DTO) Pattern

DTOs are used in various parts of the application to:
- Transfer data between layers without exposing entity internals
- Define specific data structures for different use cases
- Validate input data before converting to entities
- Customize data returned to the presentation layer

These design patterns contribute to a well-structured, maintainable codebase that follows established software engineering principles. 

---

# Chapter 4: Database Schema

## 4.1 Database Design Philosophy

The database design for the ContactManager application follows several key principles to ensure data integrity, performance, and maintainability:

### 4.1.1 Normalization

The database schema is designed with normalization principles in mind, primarily adhering to the Third Normal Form (3NF) to:
- Eliminate data redundancy
- Minimize update anomalies
- Ensure data consistency
- Support efficient querying

### 4.1.2 Domain-Driven Design Alignment

The database schema is aligned with the domain model of the application, ensuring that:
- Table structures reflect business entities
- Relationships mirror real-world associations between entities
- Constraints enforce business rules at the database level
- Column names and types align with domain terminology

### 4.1.3 Performance Considerations

While adhering to normalization principles, the schema also incorporates performance optimizations:
- Appropriate indexing strategies for frequently queried columns
- Denormalization where justified by query patterns
- Efficient data types selection for storage optimization
- Consideration of read vs. write operation balance

### 4.1.4 Security-First Approach

The database design incorporates security considerations:
- Sensitive data (like passwords) are never stored in plain text
- Authorization rules are reinforced by database constraints
- Audit trails for critical operations
- Separation of authentication data from profile information

## 4.2 Table Structure

The ContactManager database consists of several core tables that store user and contact information, along with supporting tables for authentication and other functionality.

### 4.2.1 User Table

The `USERS` table stores user account and profile information:

```sql
CREATE TABLE USERS (
    USER_ID NUMBER PRIMARY KEY,
    NAME VARCHAR2(100) NOT NULL,
    EMAIL VARCHAR2(100) NOT NULL UNIQUE,
    PASSWORD VARCHAR2(255) NOT NULL,
    USERNAME VARCHAR2(50) NOT NULL UNIQUE,
    ROLE VARCHAR2(20) DEFAULT 'ROLE_USER',
    ENABLED NUMBER(1) DEFAULT 1,
    IMAGE_URL VARCHAR2(255),
    ABOUT VARCHAR2(500),
    DATE_OF_BIRTH DATE,
    PHONE VARCHAR2(20),
    REGISTRATION_DATE TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    LAST_LOGIN_DATE TIMESTAMP
);

CREATE SEQUENCE USER_SEQ START WITH 1 INCREMENT BY 1;
```

Key features of this table include:
- `USER_ID`: Primary key, generated from a sequence
- `EMAIL` and `USERNAME`: Unique constraints ensure no duplication
- `PASSWORD`: Stores BCrypt-hashed passwords, not plain text
- `ROLE`: Defines user's authority level in the application
- `ENABLED`: Flag to activate/deactivate user accounts
- `IMAGE_URL`: Stores the path to the user's profile image
- Various profile fields like name, date of birth, and phone number
- Audit timestamps for registration and last login

### 4.2.2 Contact Table

The `CONTACTS` table stores contact information associated with users:

```sql
CREATE TABLE CONTACTS (
    CONTACT_ID NUMBER PRIMARY KEY,
    NAME VARCHAR2(100) NOT NULL,
    SECOND_NAME VARCHAR2(100),
    WORK VARCHAR2(100),
    EMAIL VARCHAR2(100),
    PHONE VARCHAR2(20),
    IMAGE VARCHAR2(255),
    DESCRIPTION VARCHAR2(1000),
    FAVORITE NUMBER(1) DEFAULT 0,
    USER_ID NUMBER,
    CONSTRAINT FK_USER_CONTACT FOREIGN KEY (USER_ID) REFERENCES USERS(USER_ID) ON DELETE CASCADE
);

CREATE SEQUENCE CONTACT_SEQ START WITH 1 INCREMENT BY 1;
```

Key features of this table include:
- `CONTACT_ID`: Primary key, generated from a sequence
- `USER_ID`: Foreign key referencing the `USERS` table with cascade delete
- `FAVORITE`: Boolean flag for marking contacts as favorites
- Contact details including name, work, email, phone, and description
- `IMAGE`: Stores the path to the contact's image

### 4.2.3 Password Reset Token Table

The `PASSWORD_RESET_TOKENS` table manages password recovery functionality:

```sql
CREATE TABLE PASSWORD_RESET_TOKENS (
    TOKEN_ID NUMBER PRIMARY KEY,
    TOKEN VARCHAR2(255) NOT NULL,
    USER_ID NUMBER NOT NULL,
    EXPIRY_DATE TIMESTAMP NOT NULL,
    CONSTRAINT FK_USER_TOKEN FOREIGN KEY (USER_ID) REFERENCES USERS(USER_ID) ON DELETE CASCADE
);

CREATE SEQUENCE TOKEN_SEQ START WITH 1 INCREMENT BY 1;
```

Key features of this table include:
- `TOKEN_ID`: Primary key, generated from a sequence
- `TOKEN`: Secure random token for password reset validation
- `USER_ID`: Foreign key referencing the `USERS` table
- `EXPIRY_DATE`: Timestamp for token expiration (typically 24 hours)

### 4.2.4 Persistent Login Table

For the "Remember Me" functionality, the application uses a `PERSISTENT_LOGINS` table:

```sql
CREATE TABLE PERSISTENT_LOGINS (
    USERNAME VARCHAR2(64) NOT NULL,
    SERIES VARCHAR2(64) PRIMARY KEY,
    TOKEN VARCHAR2(64) NOT NULL,
    LAST_USED TIMESTAMP NOT NULL
);
```

Key features of this table include:
- `SERIES`: Primary key that identifies a login session
- `TOKEN`: Security token that authenticates the user
- `USERNAME`: User identifier
- `LAST_USED`: Timestamp for tracking token usage

## 4.3 Relationships and Constraints

The database schema implements several types of relationships and constraints to maintain data integrity and enforce business rules.

### 4.3.1 Primary Keys

Each table in the schema has a primary key constraint that:
- Ensures each record can be uniquely identified
- Provides a natural join column for relationships
- Enforces entity integrity

Primary keys are implemented using sequences to generate unique values:
- `USER_SEQ` for the `USERS` table
- `CONTACT_SEQ` for the `CONTACTS` table
- `TOKEN_SEQ` for the `PASSWORD_RESET_TOKENS` table

### 4.3.2 Foreign Keys

Foreign key constraints enforce referential integrity between tables:

1. **User-Contact Relationship**:
   - The `USER_ID` column in the `CONTACTS` table references the `USER_ID` column in the `USERS` table
   - `ON DELETE CASCADE` ensures that when a user is deleted, all associated contacts are automatically removed
   - This implements the one-to-many relationship between users and contacts

2. **User-Token Relationship**:
   - The `USER_ID` column in the `PASSWORD_RESET_TOKENS` table references the `USER_ID` column in the `USERS` table
   - `ON DELETE CASCADE` ensures that when a user is deleted, all associated tokens are automatically removed
   - This implements the one-to-many relationship between users and password reset tokens

### 4.3.3 Unique Constraints

Unique constraints prevent duplicate values in specific columns:

1. **User Email**:
   - The `EMAIL` column in the `USERS` table has a unique constraint
   - Ensures no two users have the same email address
   - Critical for authentication and password recovery

2. **User Username**:
   - The `USERNAME` column in the `USERS` table has a unique constraint
   - Ensures no two users have the same username
   - Essential for login functionality

### 4.3.4 Not Null Constraints

Not null constraints ensure that critical data is always provided:

1. **User Authentication Data**:
   - `NAME`, `EMAIL`, `PASSWORD`, and `USERNAME` in the `USERS` table are marked as NOT NULL
   - Ensures essential user information is always provided

2. **Contact Information**:
   - `NAME` in the `CONTACTS` table is marked as NOT NULL
   - Ensures every contact has at least a name

3. **Token Data**:
   - `TOKEN`, `USER_ID`, and `EXPIRY_DATE` in the `PASSWORD_RESET_TOKENS` table are marked as NOT NULL
   - Ensures all necessary information for password reset functionality is provided

### 4.3.5 Default Values

Default values provide sensible initial values for certain columns:

1. **User Role and Status**:
   - `ROLE` in the `USERS` table defaults to 'ROLE_USER'
   - `ENABLED` in the `USERS` table defaults to 1 (true)

2. **Contact Favorite Status**:
   - `FAVORITE` in the `CONTACTS` table defaults to 0 (false)

3. **Registration Date**:
   - `REGISTRATION_DATE` in the `USERS` table defaults to the current timestamp

## 4.4 Indexing Strategy

The database employs a strategic indexing approach to optimize query performance while balancing the overhead associated with index maintenance.

### 4.4.1 Primary Key Indexes

Primary key columns are automatically indexed by Oracle SQL:
- `USER_ID` in the `USERS` table
- `CONTACT_ID` in the `CONTACTS` table
- `TOKEN_ID` in the `PASSWORD_RESET_TOKENS` table
- `SERIES` in the `PERSISTENT_LOGINS` table

These indexes support fast lookups of individual records and efficient joins between tables.

### 4.4.2 Foreign Key Indexes

Foreign key columns are indexed to improve join performance:
- `USER_ID` in the `CONTACTS` table
- `USER_ID` in the `PASSWORD_RESET_TOKENS` table

These indexes accelerate queries that retrieve all contacts or tokens for a specific user.

### 4.4.3 Unique Key Indexes

Columns with unique constraints are automatically indexed:
- `EMAIL` in the `USERS` table
- `USERNAME` in the `USERS` table

These indexes support fast lookups during authentication and duplicate checking.

### 4.4.4 Search Optimization Indexes

Additional indexes are created on columns frequently used in search conditions:
- `FAVORITE` in the `CONTACTS` table (for filtering favorite contacts)
- `NAME` in the `CONTACTS` table (for name-based searches)
- `EMAIL` in the `CONTACTS` table (for email-based searches)
- `TOKEN` in the `PASSWORD_RESET_TOKENS` table (for token validation)

### 4.4.5 Composite Indexes

Composite indexes are used for queries that frequently filter or sort by multiple columns:
- `(USER_ID, FAVORITE)` in the `CONTACTS` table (for retrieving a user's favorite contacts)
- `(USER_ID, NAME)` in the `CONTACTS` table (for sorting a user's contacts by name)

## 4.5 Data Access Layer

The data access layer of the ContactManager application is implemented using Spring Data JPA, which provides an abstraction over the database operations.

### 4.5.1 Repository Interfaces

The application defines repository interfaces that extend Spring Data JPA's base repositories:

1. **UserRepository**:
```java
public interface UserRepository extends JpaRepository<User, Long> {
    User findByEmail(String email);
    User findByUsername(String username);
    Boolean existsByEmail(String email);
    Boolean existsByUsername(String username);
}
```

2. **ContactRepository**:
```java
public interface ContactRepository extends JpaRepository<Contact, Long> {
    Page<Contact> findByUserOrderByNameAsc(User user, Pageable pageable);
    List<Contact> findByUserAndFavoriteTrue(User user);
    Contact findByUserAndCId(User user, Long cId);
}
```

3. **PasswordResetTokenRepository**:
```java
public interface PasswordResetTokenRepository extends JpaRepository<PasswordResetToken, Long> {
    PasswordResetToken findByToken(String token);
    List<PasswordResetToken> findByUserAndExpiryDateLessThan(User user, Date expiryDate);
}
```

### 4.5.2 Entity Mapping

The mapping between Java entities and database tables is configured using JPA annotations:

1. **User Entity**:
```java
@Entity
@Table(name = "USERS")
public class User implements Serializable {
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "user_seq")
    @SequenceGenerator(name = "user_seq", sequenceName = "USER_SEQ", allocationSize = 1)
    private Long id;
    
    @Column(nullable = false, length = 100)
    private String name;
    
    @Column(nullable = false, unique = true, length = 100)
    private String email;
    
    @Column(nullable = false)
    private String password;
    
    @Column(nullable = false, unique = true, length = 50)
    private String username;
    
    private String role;
    private boolean enabled;
    private String imageUrl;
    private String about;
    private Date dateOfBirth;
    private String phone;
    
    @Temporal(TemporalType.TIMESTAMP)
    private Date registrationDate;
    
    @Temporal(TemporalType.TIMESTAMP)
    private Date lastLoginDate;
    
    @OneToMany(mappedBy = "user", cascade = CascadeType.ALL, orphanRemoval = true)
    private List<Contact> contacts = new ArrayList<>();
    
    // Getters, setters, and other methods
}
```

2. **Contact Entity**:
```java
@Entity
@Table(name = "CONTACTS")
public class Contact implements Serializable {
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "contact_seq")
    @SequenceGenerator(name = "contact_seq", sequenceName = "CONTACT_SEQ", allocationSize = 1)
    private Long cId;
    
    @Column(nullable = false, length = 100)
    private String name;
    
    private String secondName;
    private String work;
    private String email;
    private String phone;
    private String image;
    
    @Column(length = 1000)
    private String description;
    
    private boolean favorite;
    
    @ManyToOne
    @JoinColumn(name = "USER_ID")
    private User user;
    
    // Getters, setters, and other methods
}
```

3. **PasswordResetToken Entity**:
```java
@Entity
@Table(name = "PASSWORD_RESET_TOKENS")
public class PasswordResetToken {
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "token_seq")
    @SequenceGenerator(name = "token_seq", sequenceName = "TOKEN_SEQ", allocationSize = 1)
    private Long tokenId;
    
    @Column(nullable = false)
    private String token;
    
    @OneToOne(targetEntity = User.class, fetch = FetchType.EAGER)
    @JoinColumn(nullable = false, name = "USER_ID")
    private User user;
    
    @Column(nullable = false)
    private Date expiryDate;
    
    // Getters, setters, and other methods
}
```

### 4.5.3 Query Methods

Spring Data JPA's query methods generation feature is used to create database queries based on method names:

1. **Finding by Properties**:
- `findByEmail` and `findByUsername` in `UserRepository` translate to SQL queries with `WHERE` clauses
- `findByUserAndFavoriteTrue` in `ContactRepository` finds favorite contacts for a specific user

2. **Existence Checks**:
- `existsByEmail` and `existsByUsername` in `UserRepository` check if records exist with specific values

3. **Custom Ordering**:
- `findByUserOrderByNameAsc` in `ContactRepository` retrieves contacts sorted by name

### 4.5.4 Pagination Support

The repository methods support pagination for efficiently retrieving large sets of data:

```java
// In ContactController
@GetMapping("/contacts")
public String showContacts(
        @RequestParam(value = "page", defaultValue = "0") Integer page,
        Model model, Principal principal) {
    
    User user = userService.getUserByUsername(principal.getName());
    
    // 5 contacts per page
    Pageable pageable = PageRequest.of(page, 5);
    Page<Contact> contacts = contactService.findContactsByUser(user, pageable);
    
    model.addAttribute("contacts", contacts);
    model.addAttribute("currentPage", page);
    model.addAttribute("totalPages", contacts.getTotalPages());
    
    return "user/contacts";
}
```

### 4.5.5 Custom Queries

For more complex queries, the repositories use the `@Query` annotation:

```java
@Query("SELECT c FROM Contact c WHERE c.user.id = :userId AND " +
       "(c.name LIKE %:keyword% OR c.email LIKE %:keyword% OR c.phone LIKE %:keyword%)")
Page<Contact> searchContacts(@Param("userId") Long userId, 
                           @Param("keyword") String keyword,
                           Pageable pageable);
```

### 4.5.6 Specifications for Dynamic Queries

The search functionality uses JPA Specifications to build dynamic queries:

```java
public Specification<Contact> buildSearchSpecification(User user, String field, String keyword) {
    return (root, query, criteriaBuilder) -> {
        query.distinct(true);
        
        // Base condition: contacts belong to the current user
        Predicate userPredicate = criteriaBuilder.equal(root.get("user"), user);
        
        // Search condition based on the selected field
        Predicate searchPredicate;
        if (field.equals("name")) {
            searchPredicate = criteriaBuilder.like(
                criteriaBuilder.lower(root.get("name")), 
                "%" + keyword.toLowerCase() + "%"
            );
        } else if (field.equals("email")) {
            searchPredicate = criteriaBuilder.like(
                criteriaBuilder.lower(root.get("email")), 
                "%" + keyword.toLowerCase() + "%"
            );
        } else if (field.equals("phone")) {
            searchPredicate = criteriaBuilder.like(
                root.get("phone"), 
                "%" + keyword + "%"
            );
        } else {
            // Default to search across all fields
            Predicate namePredicate = criteriaBuilder.like(
                criteriaBuilder.lower(root.get("name")), 
                "%" + keyword.toLowerCase() + "%"
            );
            Predicate emailPredicate = criteriaBuilder.like(
                criteriaBuilder.lower(root.get("email")), 
                "%" + keyword.toLowerCase() + "%"
            );
            Predicate phonePredicate = criteriaBuilder.like(
                root.get("phone"), 
                "%" + keyword + "%"
            );
            
            searchPredicate = criteriaBuilder.or(namePredicate, emailPredicate, phonePredicate);
        }
        
        // Combine user predicate and search predicate
        return criteriaBuilder.and(userPredicate, searchPredicate);
    };
}
```

**Figure 4.1: Database Schema Diagram**

```
┌───────────────────────────┐       ┌───────────────────────────┐
│          USERS            │       │         CONTACTS          │
├───────────────────────────┤       ├───────────────────────────┤
│ USER_ID (PK)              │◄──┐   │ CONTACT_ID (PK)           │
│ NAME                      │   │   │ NAME                      │
│ EMAIL (UQ)                │   │   │ SECOND_NAME               │
│ PASSWORD                  │   │   │ EMAIL                     │
│ USERNAME (UQ)             │   │   │ PHONE                     │
│ ROLE                      │   │   │ IMAGE                     │
│ ENABLED                   │   │   │ DESCRIPTION               │
│ IMAGE_URL                 │   │   │ FAVORITE                  │
│ ABOUT                     │   │   │ USER_ID (FK)              │
│ DATE_OF_BIRTH             │   │   │ USER_ID (FK)              │
│ PHONE                     │   │   └───────────────────────────┘
│ REGISTRATION_DATE         │   │   
│ LAST_LOGIN_DATE           │   │   
└───────────────────────────┘   │   
                                │   
┌───────────────────────────┐   │   
│    PASSWORD_RESET_TOKENS  │   │   
├───────────────────────────┤   │   
│ TOKEN_ID (PK)             │   │   
│ TOKEN                     │   │   
│ EXPIRY_DATE               │   │   
│ USER_ID (FK)              │───┘   
└───────────────────────────┘       
                                    
┌───────────────────────────┐       
│     PERSISTENT_LOGINS     │       
├───────────────────────────┤       
│ SERIES (PK)               │       
│ USERNAME                  │       
│ TOKEN                     │       
│ LAST_USED                 │       
└───────────────────────────┘       
```

The database schema forms the foundation of the ContactManager application, providing efficient data storage and retrieval while enforcing business rules and data integrity constraints. The use of Spring Data JPA abstracts the complexity of database operations, allowing the application to focus on business logic rather than data access mechanics. 

---

# Chapter 5: User Authentication and Authorization Module

## 5.1 Authentication Flow

The ContactManager application implements a comprehensive authentication system that supports multiple authentication methods and secure user management. The authentication flow is designed to provide a seamless user experience while maintaining robust security.

### 5.1.1 Authentication Methods

The application supports two primary authentication methods:

1. **Form-Based Authentication**:
   - Traditional username/password authentication
   - Credentials validated against the database
   - BCrypt password encryption for secure storage
   - "Remember Me" functionality for persistent sessions

2. **Google OAuth 2.0 Authentication**:
   - Single sign-on via Google accounts
   - Integration with Google's authentication API
   - Automatic user registration for new Google users
   - Linking of existing accounts with Google credentials

### 5.1.2 Authentication Sequence

The standard authentication sequence for form-based login follows these steps:

1. User accesses a protected resource or directly navigates to the login page
2. The application presents the login form with options for traditional login or Google sign-in
3. User submits credentials (username/password)
4. Spring Security's authentication manager validates the credentials:
   - Username is used to locate the user record
   - Password is verified using BCrypt matcher against the stored hash
   - User status (enabled/disabled) is checked
5. Upon successful authentication:
   - A session is established for the user
   - If "Remember Me" is selected, a persistent token is stored
   - The user is redirected to the requested resource or the default dashboard
6. If authentication fails:
   - Error message is displayed
   - User remains on the login page to retry

For Google OAuth authentication, the sequence is:

1. User clicks the "Sign in with Google" button
2. The application redirects to Google's authentication page
3. User authenticates with Google and grants permissions
4. Google redirects back to the application with an authorization code
5. The application exchanges the code for access and ID tokens
6. User information is extracted from the ID token
7. The application either:
   - Finds an existing user with the matching Google ID and logs them in
   - Creates a new user account based on the Google profile information
8. A session is established and the user is redirected to the dashboard

### 5.1.3 Session Management

The application implements secure session management:

- Session timeout after a period of inactivity (default: 30 minutes)
- Session invalidation on logout
- Prevention of session fixation attacks
- Secure cookie settings with HttpOnly and Secure flags (in production)
- CSRF protection for all state-changing operations

**Figure 5.1: Authentication Flow Diagram**
```
┌─────────────┐     ┌───────────────┐     ┌─────────────────┐     ┌──────────────┐
│  Browser    │     │  Controllers  │     │ Authentication  │     │  Database    │
└──────┬──────┘     └───────┬───────┘     └───────┬─────────┘     └──────┬───────┘
       │                    │                     │                      │
       │    Access Page     │                     │                      │
       ├───────────────────►│                     │                      │
       │                    │                     │                      │
       │   Redirect to      │                     │                      │
       │   Login Page       │                     │                      │
       │◄───────────────────┤                     │                      │
       │                    │                     │                      │
       │ Submit Credentials │                     │                      │
       ├───────────────────►│                     │                      │
       │                    │    Authenticate     │                      │
       │                    ├────────────────────►│                      │
       │                    │                     │                      │
       │                    │                     │  Query User Data     │
       │                    │                     ├─────────────────────►│
       │                    │                     │                      │
       │                    │                     │  Return User         │
       │                    │                     │◄─────────────────────┤
       │                    │                     │                      │
       │                    │                     │ Verify Password      │
       │                    │                     │ & Create Session     │
       │                    │                     │                      │
       │                    │ Authentication      │                      │
       │                    │ Result              │                      │
       │                    │◄────────────────────┤                      │
       │                    │                     │                      │
       │   Redirect to      │                     │                      │
       │   Dashboard        │                     │                      │
       │◄───────────────────┤                     │                      │
       │                    │                     │                      │
```

## 5.2 Spring Security Configuration

The ContactManager application uses Spring Security to implement authentication, authorization, and other security features. The security configuration is defined in a dedicated configuration class.

### 5.2.1 Security Configuration Class

The `SecurityConfiguration` class extends `WebSecurityConfigurerAdapter` and provides customized security settings:

```java
@Configuration
@EnableWebSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Autowired
    private UserDetailsService userDetailsService;
    
    @Autowired
    private OAuth2UserService oAuth2UserService;
    
    @Bean
    public BCryptPasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder();
    }
    
    @Bean
    public AuthenticationProvider authenticationProvider() {
        DaoAuthenticationProvider provider = new DaoAuthenticationProvider();
        provider.setUserDetailsService(userDetailsService);
        provider.setPasswordEncoder(passwordEncoder());
        return provider;
    }
    
    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http
            .authorizeRequests()
                .antMatchers("/admin/**").hasRole("ADMIN")
                .antMatchers("/user/**").hasRole("USER")
                .antMatchers("/", "/signup", "/login", "/about", "/service", 
                             "/contact", "/meetus", "/gallery", "/resources/**", 
                             "/css/**", "/js/**", "/images/**", "/auth/**").permitAll()
                .anyRequest().authenticated()
            .and()
            .formLogin()
                .loginPage("/login")
                .defaultSuccessUrl("/user/index")
                .failureUrl("/login?error=true")
                .permitAll()
            .and()
            .oauth2Login()
                .loginPage("/login")
                .userInfoEndpoint()
                    .userService(oAuth2UserService)
                .and()
                .successHandler(oAuth2AuthenticationSuccessHandler())
            .and()
            .logout()
                .logoutRequestMatcher(new AntPathRequestMatcher("/logout"))
                .logoutSuccessUrl("/login?logout=true")
                .deleteCookies("JSESSIONID")
                .invalidateHttpSession(true)
                .permitAll()
            .and()
            .rememberMe()
                .tokenRepository(persistentTokenRepository())
                .tokenValiditySeconds(7 * 24 * 60 * 60) // 7 days
            .and()
            .csrf();
    }
    
    @Bean
    public PersistentTokenRepository persistentTokenRepository() {
        JdbcTokenRepositoryImpl tokenRepository = new JdbcTokenRepositoryImpl();
        tokenRepository.setDataSource(dataSource);
        return tokenRepository;
    }
    
    @Bean
    public AuthenticationSuccessHandler oAuth2AuthenticationSuccessHandler() {
        return new OAuth2AuthenticationSuccessHandler();
    }
}
```

### 5.2.2 Access Control Rules

The security configuration defines access control rules that determine which URLs are protected and what roles are required to access them:

1. **Public Resources**:
   - Home page, signup, login, and informational pages are accessible to all
   - Static resources (CSS, JavaScript, images) are publicly available
   - Password reset functionality is open to all users

2. **User Area**:
   - All URLs under `/user/**` require the `ROLE_USER` authority
   - This includes the dashboard, contact management, and profile pages
   - Authenticated users without the proper role receive a 403 Forbidden response

3. **Admin Area**:
   - All URLs under `/admin/**` require the `ROLE_ADMIN` authority
   - Admin features are strictly segregated from regular user functionality

### 5.2.3 Authentication Configuration

The authentication setup includes:

1. **Authentication Provider**:
   - Uses the custom `UserDetailsService` implementation for retrieving user data
   - Configures BCrypt password encoder for password matching
   - Registers the provider with Spring Security's authentication manager

2. **Form Login Configuration**:
   - Custom login page at `/login`
   - Success redirection to user dashboard
   - Failure handling with appropriate error messages
   - CSRF protection for login form

3. **OAuth2 Login Configuration**:
   - Same login page as form login
   - Custom user service for processing OAuth2 user data
   - Success handler for creating or updating user accounts
   - Appropriate redirection after authentication

4. **Remember Me Functionality**:
   - Persistent token storage in the database
   - 7-day token validity
   - Secure cookie handling

### 5.2.4 Logout Handling

The logout configuration ensures secure session termination:

- Custom logout URL mapped to `/logout`
- Session invalidation on logout
- Clearing of authentication cookies
- Redirection to login page with logout confirmation
- CSRF protection for logout requests

## 5.3 User Registration Process

The user registration process is designed to be user-friendly while ensuring that only valid user accounts are created.

### 5.3.1 Registration Form

The registration form collects essential user information:

- Full name
- Email address (used for communication and password recovery)
- Username (used for login)
- Password (with strength requirements)
- Password confirmation (for validation)

### 5.3.2 Validation Rules

The application applies several validation rules during registration:

1. **Email Validation**:
   - Must be a valid email format
   - Must be unique (not already registered)
   - Required field

2. **Username Validation**:
   - Must be between 3 and 20 characters
   - Must be unique (not already in use)
   - Required field
   - Alphanumeric characters only

3. **Password Validation**:
   - Minimum 8 characters
   - Must include at least one uppercase letter, one lowercase letter, and one number
   - Passwords must match confirmation
   - Required field

4. **Name Validation**:
   - Required field
   - Must be between 2 and 50 characters

### 5.3.3 Registration Flow

The registration process follows these steps:

1. User navigates to the registration page
2. The application displays the registration form
3. User completes the form and submits
4. The application performs validation:
   - Field validation (length, format, etc.)
   - Business rule validation (unique email/username)
5. If validation fails, the form is redisplayed with error messages
6. If validation succeeds:
   - The password is encrypted using BCrypt
   - A new user record is created in the database
   - The user is assigned the `ROLE_USER` authority
   - The account is enabled by default
   - A welcome email is sent to the user
7. The user is redirected to the login page with a success message

### 5.3.4 Registration Controller

The registration functionality is implemented in the `UserController` class:

```java
@Controller
public class UserController {

    @Autowired
    private UserService userService;
    
    @Autowired
    private BCryptPasswordEncoder passwordEncoder;
    
    @GetMapping("/signup")
    public String register(Model model) {
        model.addAttribute("user", new User());
        return "signup";
    }
    
    @PostMapping("/register")
    public String processRegister(@Valid @ModelAttribute("user") User user,
                                 BindingResult result,
                                 @RequestParam("confirmPassword") String confirmPassword,
                                 Model model,
                                 RedirectAttributes redirectAttributes) {
        
        // Check if email already exists
        if (userService.checkEmailExists(user.getEmail())) {
            result.rejectValue("email", "error.user", "Email is already registered");
        }
        
        // Check if username already exists
        if (userService.checkUsernameExists(user.getUsername())) {
            result.rejectValue("username", "error.user", "Username is already taken");
        }
        
        // Check if passwords match
        if (!user.getPassword().equals(confirmPassword)) {
            result.rejectValue("password", "error.user", "Passwords do not match");
        }
        
        if (result.hasErrors()) {
            return "signup";
        }
        
        // Encode password and set default values
        user.setPassword(passwordEncoder.encode(user.getPassword()));
        user.setRole("ROLE_USER");
        user.setEnabled(true);
        user.setRegistrationDate(new Date());
        
        // Save user
        userService.saveUser(user);
        
        // Send welcome email
        // emailService.sendWelcomeEmail(user);
        
        redirectAttributes.addFlashAttribute("successMessage", 
            "Registration successful! You can now login.");
        return "redirect:/login";
    }
}
```

## 5.4 Login Implementation

The login functionality allows users to authenticate using their credentials and access the protected areas of the application.

### 5.4.1 Login Form

The login form collects the necessary authentication information:

- Username (or email, depending on configuration)
- Password
- "Remember Me" option for persistent login
- Link to password recovery
- Option to authenticate with Google

### 5.4.2 Authentication Process

The login process is handled by Spring Security's authentication manager:

1. User submits the login form
2. Spring Security's filter intercepts the request
3. The authentication manager delegates to the authentication provider
4. The user details service loads the user by username
5. The password encoder verifies the submitted password against the stored hash
6. If authentication succeeds, a security context is established for the session
7. If "Remember Me" is selected, a persistent token is stored
8. The user is redirected to the target URL or default success URL

### 5.4.3 Login Controller

While Spring Security handles most of the authentication logic, the `UserController` also provides a method for displaying the login page:

```java
@Controller
public class UserController {
    
    // Other methods...
    
    @GetMapping("/login")
    public String login() {
        return "login";
    }
}
```

### 5.4.4 Custom Authentication Success Handler

The application uses a custom authentication success handler to perform additional operations after successful authentication:

```java
@Component
public class CustomAuthenticationSuccessHandler implements AuthenticationSuccessHandler {

    @Autowired
    private UserService userService;
    
    @Override
    public void onAuthenticationSuccess(HttpServletRequest request, 
                                       HttpServletResponse response, 
                                       Authentication authentication) throws IOException {
        
        String username = authentication.getName();
        User user = userService.findUserByUsername(username);
        
        // Update last login date
        user.setLastLoginDate(new Date());
        userService.saveUser(user);
        
        // Determine redirect URL
        String targetUrl = determineTargetUrl(authentication);
        
        if (response.isCommitted()) {
            return;
        }
        
        RedirectStrategy redirectStrategy = new DefaultRedirectStrategy();
        redirectStrategy.sendRedirect(request, response, targetUrl);
    }
    
    protected String determineTargetUrl(Authentication authentication) {
        boolean isUser = false;
        boolean isAdmin = false;
        
        Collection<? extends GrantedAuthority> authorities = authentication.getAuthorities();
        for (GrantedAuthority grantedAuthority : authorities) {
            if (grantedAuthority.getAuthority().equals("ROLE_USER")) {
                isUser = true;
                break;
            } else if (grantedAuthority.getAuthority().equals("ROLE_ADMIN")) {
                isAdmin = true;
                break;
            }
        }
        
        if (isUser) {
            return "/user/index";
        } else if (isAdmin) {
            return "/admin/index";
        } else {
            throw new IllegalStateException("User has no valid role");
        }
    }
}
```

## 5.5 Google OAuth Integration

The ContactManager application integrates with Google's OAuth 2.0 authentication system to provide users with an alternative login method. This integration enhances the user experience by allowing single sign-on and reduces friction during the registration process.

### 5.5.1 OAuth 2.0 Configuration

The application's OAuth 2.0 configuration is defined in the `application.properties` file:

```properties
spring.security.oauth2.client.registration.google.client-id=<client-id>
spring.security.oauth2.client.registration.google.client-secret=<client-secret>
spring.security.oauth2.client.registration.google.scope=email,profile
```

This configuration registers Google as an OAuth provider and specifies the required scopes (email and profile) to access user information.

### 5.5.2 Custom OAuth2 User Service

A custom OAuth2 user service is implemented to process the user information received from Google and integrate it with the application's user management system:

```java
@Service
public class CustomOAuth2UserService extends DefaultOAuth2UserService {

    @Autowired
    private UserRepository userRepository;
    
    @Override
    public OAuth2User loadUser(OAuth2UserRequest userRequest) throws OAuth2AuthenticationException {
        OAuth2User oauth2User = super.loadUser(userRequest);
        
        // Extract OAuth2 user details
        String email = oauth2User.getAttribute("email");
        String name = oauth2User.getAttribute("name");
        String googleId = oauth2User.getAttribute("sub");
        
        // Check if user exists
        User user = userRepository.findByEmail(email);
        
        if (user == null) {
            // Create a new user
            user = new User();
            user.setEmail(email);
            user.setName(name);
            user.setUsername(email); // Use email as username for OAuth users
            user.setPassword(UUID.randomUUID().toString()); // Generate random password
            user.setRole("ROLE_USER");
            user.setEnabled(true);
            user.setGoogleId(googleId);
            user.setRegistrationDate(new Date());
            
            userRepository.save(user);
        } else if (user.getGoogleId() == null) {
            // Link existing account with Google
            user.setGoogleId(googleId);
            userRepository.save(user);
        }
        
        return new CustomOAuth2User(oauth2User, user);
    }
}
```

### 5.5.3 OAuth2 Authentication Success Handler

After successful OAuth authentication, a custom success handler processes the result and redirects the user to the appropriate page:

```java
@Component
public class OAuth2AuthenticationSuccessHandler implements AuthenticationSuccessHandler {

    @Autowired
    private UserService userService;
    
    @Override
    public void onAuthenticationSuccess(HttpServletRequest request, 
                                       HttpServletResponse response, 
                                       Authentication authentication) throws IOException {
        
        CustomOAuth2User oauthUser = (CustomOAuth2User) authentication.getPrincipal();
        User user = oauthUser.getUser();
        
        // Update last login date
        user.setLastLoginDate(new Date());
        userService.saveUser(user);
        
        // Redirect to user dashboard
        response.sendRedirect("/user/index");
    }
}
```

### 5.5.4 OAuth Login Button

The login page includes a button for Google authentication:

```html
<div class="social-login">
    <a href="/oauth2/authorization/google" class="btn btn-google">
        <i class="fab fa-google"></i> Sign in with Google
    </a>
</div>
```

This button triggers the OAuth flow, redirecting the user to Google's authentication page.

## 5.6 Password Reset Functionality

The ContactManager application provides a secure mechanism for users to reset their passwords when forgotten.

### 5.6.1 Password Reset Flow

The password reset process follows these steps:

1. User requests a password reset by providing their email address
2. The application verifies the email exists in the database
3. A unique reset token is generated and stored in the database with an expiration time
4. A password reset link containing the token is sent to the user's email
5. User clicks the link, which redirects to the password reset form
6. The application validates the token (existence and expiration)
7. User enters a new password and confirmation
8. After validation, the password is updated and the token is invalidated
9. User is redirected to the login page with a success message

**Figure 5.2: Password Reset Flow**
```
┌─────────────┐     ┌───────────────┐     ┌─────────────────┐     ┌──────────────┐     ┌──────────────┐
│  Browser    │     │  Controllers  │     │  User Service   │     │  Database    │     │  Email Service│
└──────┬──────┘     └───────┬───────┘     └───────┬─────────┘     └──────┬───────┘     └──────┬───────┘
       │                    │                     │                      │                     │
       │ Forgot Password    │                     │                      │                     │
       │ Form Submission    │                     │                      │                     │
       ├───────────────────►│                     │                      │                     │
       │                    │                     │                      │                     │
       │                    │ Find User by Email  │                      │                     │
       │                    ├────────────────────►│                      │                     │
       │                    │                     │                      │                     │
       │                    │                     │ Query User           │                     │
       │                    │                     ├─────────────────────►│                     │
       │                    │                     │                      │                     │
       │                    │                     │ Return User          │                     │
       │                    │                     │◄─────────────────────┤                     │
       │                    │                     │                      │                     │
       │                    │                     │ Generate Token       │                     │
       │                    │                     │                      │                     │
       │                    │                     │ Save Token           │                     │
       │                    │                     ├─────────────────────►│                     │
       │                    │                     │                      │                     │
       │                    │                     │ Send Reset Email     │                     │
       │                    │                     ├─────────────────────────────────────────► │
       │                    │                     │                      │                     │
       │                    │ Success Message     │                      │                     │
       │                    │◄────────────────────┤                      │                     │
       │                    │                     │                      │                     │
       │ Success Page       │                     │                      │                     │
       │◄───────────────────┤                     │                      │                     │
       │                    │                     │                      │                     │
       │ Click Reset Link   │                     │                      │                     │
       ├───────────────────►│                     │                      │                     │
       │                    │                     │                      │                     │
       │                    │ Validate Token      │                      │                     │
       │                    ├────────────────────►│                      │                     │
       │                    │                     │                      │                     │
       │                    │                     │ Check Token          │                     │
       │                    │                     ├─────────────────────►│                     │
       │                    │                     │                      │                     │
       │                    │                     │ Return Token Status  │                     │
       │                    │                     │◄─────────────────────┤                     │
       │                    │                     │                      │                     │
       │ Reset Password Form│                     │                      │                     │
       │◄───────────────────┤                     │                      │                     │
       │                    │                     │                      │                     │
       │ Submit New Password│                     │                      │                     │
       ├───────────────────►│                     │                      │                     │
       │                    │                     │                      │                     │
       │                    │ Update Password     │                      │                     │
       │                    ├────────────────────►│                      │                     │
       │                    │                     │                      │                     │
       │                    │                     │ Update User          │                     │
       │                    │                     ├─────────────────────►│                     │
       │                    │                     │                      │                     │
       │                    │                     │ Delete Token         │                     │
       │                    │                     ├─────────────────────►│                     │
       │                    │                     │                      │                     │
       │ Redirect to Login  │                     │                      │                     │
       │◄───────────────────┤                     │                      │                     │
       │                    │                     │                      │                     │
```

### 5.6.2 Password Reset Token Entity

The password reset tokens are stored in a dedicated entity:

```java
@Entity
@Table(name = "PASSWORD_RESET_TOKENS")
public class PasswordResetToken {
    
    private static final int EXPIRATION = 24; // hours
    
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "token_seq")
    @SequenceGenerator(name = "token_seq", sequenceName = "TOKEN_SEQ", allocationSize = 1)
    private Long tokenId;
    
    @Column(nullable = false)
    private String token;
    
    @OneToOne(targetEntity = User.class, fetch = FetchType.EAGER)
    @JoinColumn(nullable = false, name = "USER_ID")
    private User user;
    
    @Column(nullable = false)
    private Date expiryDate;
    
    public PasswordResetToken() {
        this.expiryDate = calculateExpiryDate(EXPIRATION);
    }
    
    public PasswordResetToken(String token, User user) {
        this.token = token;
        this.user = user;
        this.expiryDate = calculateExpiryDate(EXPIRATION);
    }
    
    private Date calculateExpiryDate(int expiryTimeInHours) {
        Calendar cal = Calendar.getInstance();
        cal.setTime(new Date());
        cal.add(Calendar.HOUR, expiryTimeInHours);
        return cal.getTime();
    }
    
    public boolean isExpired() {
        return new Date().after(this.expiryDate);
    }
    
    // Getters and setters
}
```

### 5.6.3 Password Reset Service

The password reset functionality is implemented in the `PasswordResetService`:

```java
@Service
public class PasswordResetService {
    
    @Autowired
    private PasswordResetTokenRepository tokenRepository;
    
    @Autowired
    private UserRepository userRepository;
    
    @Autowired
    private EmailService emailService;
    
    @Autowired
    private BCryptPasswordEncoder passwordEncoder;
    
    public void createPasswordResetTokenForUser(User user, String token) {
        PasswordResetToken myToken = new PasswordResetToken(token, user);
        tokenRepository.save(myToken);
    }
    
    public String validatePasswordResetToken(String token) {
        PasswordResetToken passToken = tokenRepository.findByToken(token);
        
        if (passToken == null) {
            return "invalidToken";
        }
        
        if (passToken.isExpired()) {
            tokenRepository.delete(passToken);
            return "expired";
        }
        
        return "valid";
    }
    
    public User getUserByPasswordResetToken(String token) {
        PasswordResetToken passToken = tokenRepository.findByToken(token);
        return passToken.getUser();
    }
    
    public void changeUserPassword(User user, String password) {
        user.setPassword(passwordEncoder.encode(password));
        userRepository.save(user);
    }
    
    public void sendPasswordResetEmail(User user, String token, HttpServletRequest request) {
        String resetUrl = request.getScheme() + "://" + request.getServerName() + ":" + 
                         request.getServerPort() + request.getContextPath() + 
                         "/auth/reset-password?token=" + token;
        
        String subject = "Password Reset Request";
        String message = "To reset your password, click the link below:\n" + resetUrl + 
                        "\n\nThis link will expire in 24 hours.";
        
        emailService.sendEmail(user.getEmail(), subject, message);
    }
}
```

### 5.6.4 Password Reset Controller

The password reset functionality is exposed through the `PasswordResetController`:

```java
@Controller
@RequestMapping("/auth")
public class PasswordResetController {
    
    @Autowired
    private UserService userService;
    
    @Autowired
    private PasswordResetService passwordResetService;
    
    @GetMapping("/forgot-password")
    public String showForgotPasswordForm() {
        return "auth/forgot-password";
    }
    
    @PostMapping("/forgot-password")
    public String processForgotPassword(@RequestParam("email") String email,
                                       HttpServletRequest request,
                                       RedirectAttributes redirectAttributes) {
        
        User user = userService.findUserByEmail(email);
        
        if (user == null) {
            redirectAttributes.addFlashAttribute("error", 
                "We couldn't find an account with that email address.");
            return "redirect:/auth/forgot-password";
        }
        
        String token = UUID.randomUUID().toString();
        passwordResetService.createPasswordResetTokenForUser(user, token);
        passwordResetService.sendPasswordResetEmail(user, token, request);
        
        redirectAttributes.addFlashAttribute("successMessage", 
            "A password reset link has been sent to your email address.");
        return "redirect:/login";
    }
    
    @GetMapping("/reset-password")
    public String showResetPasswordForm(@RequestParam("token") String token,
                                       Model model,
                                       RedirectAttributes redirectAttributes) {
        
        String result = passwordResetService.validatePasswordResetToken(token);
        
        if (!result.equals("valid")) {
            redirectAttributes.addFlashAttribute("error", 
                "The password reset link is invalid or has expired.");
            return "redirect:/auth/forgot-password";
        }
        
        model.addAttribute("token", token);
        return "auth/reset-password";
    }
    
    @PostMapping("/reset-password")
    public String processResetPassword(@RequestParam("token") String token,
                                      @RequestParam("password") String password,
                                      @RequestParam("confirmPassword") String confirmPassword,
                                      RedirectAttributes redirectAttributes) {
        
        String result = passwordResetService.validatePasswordResetToken(token);
        
        if (!result.equals("valid")) {
            redirectAttributes.addFlashAttribute("error", 
                "The password reset link is invalid or has expired.");
            return "redirect:/auth/forgot-password";
        }
        
        if (!password.equals(confirmPassword)) {
            redirectAttributes.addFlashAttribute("error", 
                "Passwords do not match.");
            return "redirect:/auth/reset-password?token=" + token;
        }
        
        User user = passwordResetService.getUserByPasswordResetToken(token);
        passwordResetService.changeUserPassword(user, password);
        
        redirectAttributes.addFlashAttribute("successMessage", 
            "Your password has been changed successfully.");
        return "redirect:/login";
    }
}
```

## 5.7 Authorization Rules

The ContactManager application implements a comprehensive authorization system to ensure users can only access and modify their own data.

### 5.7.1 Role-Based Access Control

The application uses Spring Security's role-based access control to define different levels of access:

1. **User Role (`ROLE_USER`)**:
   - Access to user dashboard
   - Management of own contacts
   - Profile management
   - Setting contacts as favorites
   - Searching contacts

2. **Admin Role (`ROLE_ADMIN`)**:
   - All user capabilities
   - User management (view, disable/enable)
   - System configuration
   - Analytics and reporting

### 5.7.2 Method-Level Security

In addition to URL-based security, the application uses method-level security annotations to enforce access control at the service layer:

```java
@Service
public class ContactServiceImpl implements ContactService {
    
    @Autowired
    private ContactRepository contactRepository;
    
    @Override
    @PreAuthorize("hasRole('USER')")
    public Page<Contact> findContactsByUser(User user, Pageable pageable) {
        return contactRepository.findByUserOrderByNameAsc(user, pageable);
    }
    
    @Override
    @PreAuthorize("hasRole('USER') and @securityService.isOwner(#contact)")
    public Contact saveContact(Contact contact) {
        return contactRepository.save(contact);
    }
    
    @Override
    @PreAuthorize("hasRole('USER') and @securityService.isContactOwner(#user, #contactId)")
    public Contact findContactById(User user, Long contactId) {
        return contactRepository.findByUserAndCId(user, contactId);
    }
    
    @Override
    @PreAuthorize("hasRole('USER') and @securityService.isContactOwner(#user, #contactId)")
    public void deleteContact(User user, Long contactId) {
        Contact contact = contactRepository.findByUserAndCId(user, contactId);
        if (contact != null) {
            contactRepository.delete(contact);
        }
    }
}
```

### 5.7.3 Custom Security Expressions

The application defines custom security expressions to enforce ownership-based access control:

```java
@Service
public class SecurityService {
    
    @Autowired
    private ContactRepository contactRepository;
    
    public boolean isOwner(Contact contact) {
        Authentication authentication = SecurityContextHolder.getContext().getAuthentication();
        User user = ((CustomUserDetails) authentication.getPrincipal()).getUser();
        return contact.getUser().getId().equals(user.getId());
    }
    
    public boolean isContactOwner(User user, Long contactId) {
        Contact contact = contactRepository.findByUserAndCId(user, contactId);
        return contact != null;
    }
}
```

### 5.7.4 Controller-Level Security

Controllers implement additional security checks to ensure users can only access their own data:

```java
@Controller
@RequestMapping("/user/contacts")
public class ContactController {
    
    @Autowired
    private ContactService contactService;
    
    @Autowired
    private UserService userService;
    
    @GetMapping("/{id}")
    public String showContactDetail(@PathVariable("id") Long contactId,
                                   Principal principal,
                                   Model model,
                                   RedirectAttributes redirectAttributes) {
        
        User user = userService.findUserByUsername(principal.getName());
        Contact contact = contactService.findContactById(user, contactId);
        
        if (contact == null) {
            redirectAttributes.addFlashAttribute("errorMessage", 
                "Contact not found or you don't have permission to view it.");
            return "redirect:/user/contacts";
        }
        
        model.addAttribute("contact", contact);
        return "user/contact-detail";
    }
    
    @GetMapping("/delete/{id}")
    public String deleteContact(@PathVariable("id") Long contactId,
                               Principal principal,
                               RedirectAttributes redirectAttributes) {
        
        User user = userService.findUserByUsername(principal.getName());
        
        try {
            contactService.deleteContact(user, contactId);
            redirectAttributes.addFlashAttribute("successMessage", 
                "Contact deleted successfully.");
        } catch (Exception e) {
            redirectAttributes.addFlashAttribute("errorMessage", 
                "Error deleting contact: " + e.getMessage());
        }
        
        return "redirect:/user/contacts";
    }
}
```

### 5.7.5 CSRF Protection

The application implements Cross-Site Request Forgery (CSRF) protection for all state-changing operations:

- CSRF tokens are included in all forms
- CSRF validation for POST, PUT, DELETE requests
- Custom CSRF handling for AJAX requests

```html
<form th:action="@{/user/contacts/process}" method="post" 
      enctype="multipart/form-data" class="contact-form">
    <input type="hidden" th:name="${_csrf.parameterName}" th:value="${_csrf.token}" />
    <!-- Form fields -->
    <button type="submit" class="btn btn-primary">Save Contact</button>
</form>
```

The authentication and authorization module forms the security backbone of the ContactManager application, ensuring that users can securely access and manage their data while preventing unauthorized access. The implementation follows industry best practices for web application security and provides a seamless user experience through multiple authentication options and self-service password management.

---

# Chapter 6: User Management Module

## 6.1 User Profile Management

The User Management Module of the ContactManager application provides comprehensive functionality for managing user accounts and profiles. This includes creating and updating user information, viewing user profiles, and managing user settings.

### 6.1.1 User Profile Overview

The user profile contains essential information about the user, including:

- Personal details (name, email, username)
- Contact information (phone number)
- Profile image
- Account information (registration date, last login)
- Password management

The profile serves as the central hub for a user's identity within the application and provides the foundation for personalized content and interactions.

### 6.1.2 Profile View

Upon logging in and navigating to the profile page, users can view their current profile information through a well-organized interface:

- Basic information section (name, email, username)
- Contact information section (phone number)
- Profile image display with upload option
- Account statistics (registration date, contacts count)
- Password change option

The profile view is designed to be intuitive and user-friendly, presenting information in a clear and organized manner.

### 6.1.3 Profile ViewModel

The profile data is presented using a dedicated ViewModel:

```java
public class UserProfileViewModel {
    private Long id;
    private String name;
    private String email;
    private String username;
    private String phone;
    private String imageUrl;
    private Date registrationDate;
    private Date lastLoginDate;
    private int contactsCount;
    
    // Getters and setters
}
```

This ViewModel is populated in the controller before being passed to the view:

```java
@GetMapping("/profile")
public String showProfile(Model model, Principal principal) {
    User user = userService.findUserByUsername(principal.getName());
    
    UserProfileViewModel profile = new UserProfileViewModel();
    profile.setId(user.getId());
    profile.setName(user.getName());
    profile.setEmail(user.getEmail());
    profile.setUsername(user.getUsername());
    profile.setPhone(user.getPhone());
    profile.setImageUrl(user.getImageUrl());
    profile.setRegistrationDate(user.getRegistrationDate());
    profile.setLastLoginDate(user.getLastLoginDate());
    profile.setContactsCount(user.getContacts().size());
    
    model.addAttribute("profile", profile);
    return "user/profile";
}
```

## 6.2 User CRUD Operations

The ContactManager application implements a complete set of Create, Read, Update, and Delete (CRUD) operations for user management.

### 6.2.1 User Creation (Registration)

As discussed in Chapter 5, user creation is primarily handled through the registration process, which includes:

- User data collection through a registration form
- Validation of input data
- Creation of user records in the database
- Assignment of the default user role
- Account activation

The creation process is implemented in the `UserController` and `UserService` classes.

### 6.2.2 User Retrieval

The application provides several methods for retrieving user information:

1. **By Username**:
```java
public User findUserByUsername(String username) {
    return userRepository.findByUsername(username);
}
```

2. **By Email**:
```java
public User findUserByEmail(String email) {
    return userRepository.findByEmail(email);
}
```

3. **By ID**:
```java
public User findUserById(Long id) {
    return userRepository.findById(id).orElse(null);
}
```

These methods are used throughout the application to retrieve user information for authentication, profile display, and relationship management.

### 6.2.3 User Update

The application allows users to update their profile information through several operations:

1. **Basic Profile Update**:
   - Updates name, phone number, and other non-sensitive information
   - Does not require password verification
   - Immediate reflection of changes

2. **Email Update**:
   - Separate process due to email's role in authentication
   - Requires password verification
   - May include email verification steps

3. **Password Update**:
   - Separate process with additional security measures
   - Requires current password verification
   - Enforces password strength rules

The update operations ensure data integrity and security while providing users with flexibility in managing their profiles.

### 6.2.4 User Deletion/Deactivation

For security and data retention purposes, the application implements a soft-deletion approach:

- Instead of permanent deletion, accounts are deactivated
- Deactivated accounts have their `enabled` flag set to `false`
- Users cannot log in to deactivated accounts
- Deactivated accounts can be reactivated by administrators

This approach preserves data integrity while allowing for account recovery if needed.

## 6.3 Profile Update Features

The profile update functionality includes several specialized features to enhance user experience and ensure data integrity.

### 6.3.1 Profile Update Form

The profile update form allows users to modify their profile information:

```html
<form th:action="@{/user/profile/update}" method="post" enctype="multipart/form-data">
    <input type="hidden" name="${_csrf.parameterName}" value="${_csrf.token}" />
    
    <div class="form-group">
        <label for="name">Full Name</label>
        <input type="text" class="form-control" id="name" name="name" 
               th:value="${profile.name}" required />
    </div>
    
    <div class="form-group">
        <label for="phone">Phone Number</label>
        <input type="text" class="form-control" id="phone" name="phone" 
               th:value="${profile.phone}" />
    </div>
    
    <div class="form-group">
        <label for="profileImage">Profile Image</label>
        <input type="file" class="form-control-file" id="profileImage" 
               name="profileImage" accept="image/*" />
    </div>
    
    <button type="submit" class="btn btn-primary">Update Profile</button>
</form>
```

### 6.3.2 Profile Image Upload

The application supports profile image upload with the following features:

1. **Image Validation**:
   - File type validation (image formats only)
   - Size validation (typically limited to 5MB)
   - Dimension validation for optimal display

2. **Image Processing**:
   - Resizing to standard dimensions
   - Compression for storage efficiency
   - Format standardization

3. **Storage Strategy**:
   - Images stored in the file system with unique identifiers
   - Database records reference file paths
   - Caching mechanisms for performance

The image upload functionality is implemented in a dedicated service:

```java
@Service
public class FileStorageService {
    
    @Value("${file.upload-dir}")
    private String uploadDir;
    
    public String storeProfileImage(MultipartFile file, String username) throws IOException {
        // Create directory if it doesn't exist
        File directory = new File(uploadDir + "/profiles");
        if (!directory.exists()) {
            directory.mkdirs();
        }
        
        // Generate unique filename
        String fileName = username + "_" + System.currentTimeMillis() + 
                         getFileExtension(file.getOriginalFilename());
        
        // Copy file to target location
        Path targetPath = Paths.get(directory.getAbsolutePath(), fileName);
        Files.copy(file.getInputStream(), targetPath, StandardCopyOption.REPLACE_EXISTING);
        
        return "/profiles/" + fileName;
    }
    
    private String getFileExtension(String fileName) {
        if (fileName == null) {
            return "";
        }
        String[] parts = fileName.split("\\.");
        return parts.length > 1 ? "." + parts[parts.length - 1] : "";
    }
}
```

### 6.3.3 Profile Update Controller

The profile update is handled by a dedicated controller method:

```java
@PostMapping("/profile/update")
public String updateProfile(@RequestParam("name") String name,
                           @RequestParam("phone") String phone,
                           @RequestParam(value = "profileImage", required = false) MultipartFile profileImage,
                           Principal principal,
                           RedirectAttributes redirectAttributes) {
    
    User user = userService.findUserByUsername(principal.getName());
    
    // Update basic info
    user.setName(name);
    user.setPhone(phone);
    
    // Process profile image if provided
    if (profileImage != null && !profileImage.isEmpty()) {
        try {
            String imageUrl = fileStorageService.storeProfileImage(profileImage, user.getUsername());
            user.setImageUrl(imageUrl);
        } catch (IOException e) {
            redirectAttributes.addFlashAttribute("errorMessage", 
                "Error uploading profile image: " + e.getMessage());
            return "redirect:/user/profile";
        }
    }
    
    // Save updated user
    userService.saveUser(user);
    
    redirectAttributes.addFlashAttribute("successMessage", "Profile updated successfully.");
    return "redirect:/user/profile";
}
```

## 6.4 Password Management

Password management is a critical aspect of user security, requiring specialized functionality beyond basic profile updates.

### 6.4.1 Password Change Form

The password change functionality is typically implemented as a modal dialog within the profile page:

```html
<div class="modal fade" id="changePasswordModal" tabindex="-1" role="dialog" aria-labelledby="changePasswordModalLabel" aria-hidden="true">
    <div class="modal-dialog" role="document">
        <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title" id="changePasswordModalLabel">Change Password</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                </button>
            </div>
            <div class="modal-body">
                <form th:action="@{/user/change-password}" method="post" id="passwordChangeForm">
                    <input type="hidden" name="${_csrf.parameterName}" value="${_csrf.token}" />
                    
                    <div class="form-group">
                        <label for="currentPassword">Current Password</label>
                        <input type="password" class="form-control" id="currentPassword" 
                               name="currentPassword" required />
                    </div>
                    
                    <div class="form-group">
                        <label for="newPassword">New Password</label>
                        <input type="password" class="form-control" id="newPassword" 
                               name="newPassword" required />
                        <small class="form-text text-muted">
                            Password must be at least 8 characters long and include 
                            uppercase, lowercase, and numbers.
                        </small>
                    </div>
                    
                    <div class="form-group">
                        <label for="confirmPassword">Confirm New Password</label>
                        <input type="password" class="form-control" id="confirmPassword" 
                               name="confirmPassword" required />
                    </div>
                </form>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-dismiss="modal">Cancel</button>
                <button type="submit" form="passwordChangeForm" class="btn btn-primary">Change Password</button>
            </div>
        </div>
    </div>
</div>
```

### 6.4.2 Password Validation

The application implements comprehensive password validation:

1. **Current Password Verification**:
   - Ensures the user knows the current password
   - Prevents unauthorized password changes

2. **New Password Strength Rules**:
   - Minimum length (typically 8 characters)
   - Character complexity (uppercase, lowercase, numbers, symbols)
   - Common password checks
   - Dictionary attack resistance

3. **Confirmation Matching**:
   - Ensures the user entered the intended password
   - Prevents typos in the new password

### 6.4.3 Password Change Controller

The password change functionality is implemented in a dedicated controller method:

```java
@PostMapping("/change-password")
public String changePassword(@RequestParam("currentPassword") String currentPassword,
                            @RequestParam("newPassword") String newPassword,
                            @RequestParam("confirmPassword") String confirmPassword,
                            Principal principal,
                            RedirectAttributes redirectAttributes) {
    
    User user = userService.findUserByUsername(principal.getName());
    
    // Verify current password
    if (!passwordEncoder.matches(currentPassword, user.getPassword())) {
        redirectAttributes.addFlashAttribute("errorMessage", "Current password is incorrect.");
        return "redirect:/user/profile";
    }
    
    // Validate new password
    if (newPassword.length() < 8) {
        redirectAttributes.addFlashAttribute("errorMessage", 
            "Password must be at least 8 characters long.");
        return "redirect:/user/profile";
    }
    
    // Check password complexity
    if (!newPassword.matches(".*[A-Z].*") || 
        !newPassword.matches(".*[a-z].*") || 
        !newPassword.matches(".*[0-9].*")) {
        redirectAttributes.addFlashAttribute("errorMessage", 
            "Password must include uppercase, lowercase, and numbers.");
        return "redirect:/user/profile";
    }
    
    // Confirm passwords match
    if (!newPassword.equals(confirmPassword)) {
        redirectAttributes.addFlashAttribute("errorMessage", "Passwords do not match.");
        return "redirect:/user/profile";
    }
    
    // Update password
    user.setPassword(passwordEncoder.encode(newPassword));
    userService.saveUser(user);
    
    redirectAttributes.addFlashAttribute("successMessage", "Password changed successfully.");
    return "redirect:/user/profile";
}
```

### 6.4.4 Password History

For enhanced security, some implementations include password history tracking:

- Prevents reuse of recent passwords (typically last 3-5 passwords)
- Requires a minimum time between password changes
- Implements a password expiration policy

These features ensure that users maintain strong password practices and regularly update their credentials.

## 6.5 User Data Validation

Data validation is a critical aspect of the User Management Module, ensuring data integrity and security.

### 6.5.1 Input Validation

The application implements comprehensive input validation using:

1. **Bean Validation (JSR-380)**:
   - Annotations on entity properties (`@NotNull`, `@Size`, `@Email`, etc.)
   - Validation triggered during form submission
   - Automated error message generation

```java
@Entity
@Table(name = "USERS")
public class User implements Serializable {
    
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "user_seq")
    @SequenceGenerator(name = "user_seq", sequenceName = "USER_SEQ", allocationSize = 1)
    private Long id;
    
    @NotBlank(message = "Name is required")
    @Size(min = 2, max = 50, message = "Name must be between 2 and 50 characters")
    @Column(nullable = false, length = 100)
    private String name;
    
    @NotBlank(message = "Email is required")
    @Email(message = "Please provide a valid email address")
    @Column(nullable = false, unique = true, length = 100)
    private String email;
    
    @NotBlank(message = "Password is required")
    @Size(min = 8, message = "Password must be at least 8 characters long")
    @Column(nullable = false)
    private String password;
    
    @NotBlank(message = "Username is required")
    @Size(min = 3, max = 20, message = "Username must be between 3 and 20 characters")
    @Pattern(regexp = "^[a-zA-Z0-9._-]*$", message = "Username can only contain letters, numbers, periods, underscores, and hyphens")
    @Column(nullable = false, unique = true, length = 50)
    private String username;
    
    // Other properties
}
```

2. **Controller-Level Validation**:
   - Custom validation logic in controller methods
   - Business rule validation
   - Cross-field validation

```java
@PostMapping("/register")
public String processRegister(@Valid @ModelAttribute("user") User user,
                             BindingResult result,
                             @RequestParam("confirmPassword") String confirmPassword,
                             Model model) {
    
    // Custom validation
    if (userService.checkEmailExists(user.getEmail())) {
        result.rejectValue("email", "error.user", "Email is already registered");
    }
    
    if (userService.checkUsernameExists(user.getUsername())) {
        result.rejectValue("username", "error.user", "Username is already taken");
    }
    
    if (!user.getPassword().equals(confirmPassword)) {
        result.rejectValue("password", "error.user", "Passwords do not match");
    }
    
    if (result.hasErrors()) {
        return "signup";
    }
    
    // Proceed with registration
    // ...
}
```

3. **JavaScript Validation**:
   - Client-side validation for immediate feedback
   - Enhanced user experience
   - Reduced server load

```javascript
$(document).ready(function() {
    $("#registrationForm").validate({
        rules: {
            name: {
                required: true,
                minlength: 2,
                maxlength: 50
            },
            email: {
                required: true,
                email: true
            },
            username: {
                required: true,
                minlength: 3,
                maxlength: 20,
                pattern: /^[a-zA-Z0-9._-]*$/
            },
            password: {
                required: true,
                minlength: 8,
                pattern: /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).+$/
            },
            confirmPassword: {
                required: true,
                equalTo: "#password"
            }
        },
        messages: {
            name: {
                required: "Please enter your full name",
                minlength: "Name must be at least 2 characters long",
                maxlength: "Name cannot exceed 50 characters"
            },
            email: {
                required: "Please enter your email address",
                email: "Please enter a valid email address"
            },
            username: {
                required: "Please enter a username",
                minlength: "Username must be at least 3 characters long",
                maxlength: "Username cannot exceed 20 characters",
                pattern: "Username can only contain letters, numbers, periods, underscores, and hyphens"
            },
            password: {
                required: "Please enter a password",
                minlength: "Password must be at least 8 characters long",
                pattern: "Password must include uppercase, lowercase, and numbers"
            },
            confirmPassword: {
                required: "Please confirm your password",
                equalTo: "Passwords do not match"
            }
        },
        submitHandler: function(form) {
            form.submit();
        }
    });
});
```

### 6.5.2 Business Rule Validation

Beyond basic input validation, the application implements business rule validation:

1. **Uniqueness Checks**:
   - Email and username uniqueness
   - Database-level unique constraints
   - Pre-submission validation

2. **Relationship Validation**:
   - Ensuring relationships maintain integrity
   - Validating foreign key references
   - Preventing orphaned records

3. **Security Rule Validation**:
   - Password strength rules
   - Authentication requirements
   - Authorization checks

These rules ensure that the application maintains a consistent and secure state regardless of user input.

### 6.5.3 Error Handling and Feedback

The application provides comprehensive error handling and user feedback:

1. **Field-Level Errors**:
   - Display errors next to the corresponding fields
   - Clear error messages indicating the issue
   - Preservation of valid field values

2. **Form-Level Validation Summary**:
   - Overview of all validation errors
   - Highlighting of problematic sections
   - Navigation to error locations

3. **Success Messages**:
   - Confirmation of successful operations
   - Feedback on completed actions
   - Guidance for next steps

This feedback system ensures users understand validation requirements and can correct issues efficiently.

The User Management Module provides a comprehensive set of features for managing user accounts and profiles while ensuring data security and integrity. The module integrates closely with the Authentication and Authorization Module to provide a seamless user experience while maintaining strict security controls.

---

# Chapter 7: Contact Management Module

## 7.1 Contact Data Model

The Contact Management Module is the core functional component of the ContactManager application, providing comprehensive capabilities for storing, retrieving, and managing contact information.

### 7.1.1 Contact Entity

The `Contact` entity represents the fundamental data structure for storing contact information:

```java
@Entity
@Table(name = "CONTACTS")
public class Contact implements Serializable {
    
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "contact_seq")
    @SequenceGenerator(name = "contact_seq", sequenceName = "CONTACT_SEQ", allocationSize = 1)
    private Long cId;
    
    @NotBlank(message = "Name is required")
    @Size(min = 2, max = 100, message = "Name must be between 2 and 100 characters")
    @Column(nullable = false, length = 100)
    private String name;
    
    @Size(max = 100, message = "Second name cannot exceed 100 characters")
    @Column(length = 100)
    private String secondName;
    
    @Size(max = 100, message = "Work information cannot exceed 100 characters")
    @Column(length = 100)
    private String work;
    
    @Email(message = "Please provide a valid email address")
    @Column(length = 100)
    private String email;
    
    @Pattern(regexp = "^[0-9+\\-\\s]*$", message = "Phone number can only contain digits, +, -, and spaces")
    @Column(length = 20)
    private String phone;
    
    @Column(length = 255)
    private String image;
    
    @Column(length = 1000)
    private String description;
    
    private boolean favorite;
    
    @ManyToOne
    @JoinColumn(name = "USER_ID")
    private User user;
    
    // Constructors, getters, setters, and other methods
}
```

The entity captures all essential contact information while enforcing data validation and establishing the relationship with the owning user.

### 7.1.2 Contact Properties

The Contact entity includes the following key properties:

1. **Identification and Ownership**:
   - `cId`: Unique identifier for the contact
   - `user`: Reference to the owning user (many-to-one relationship)

2. **Basic Information**:
   - `name`: Primary name of the contact (required)
   - `secondName`: Secondary name or nickname (optional)
   - `work`: Work information or job title (optional)

3. **Contact Details**:
   - `email`: Email address with format validation
   - `phone`: Phone number with format validation

4. **Additional Information**:
   - `image`: Path to the contact's image file
   - `description`: Extended notes or information about the contact
   - `favorite`: Boolean flag indicating if the contact is marked as a favorite

### 7.1.3 Relationships

The Contact entity participates in a many-to-one relationship with the User entity:

- Each Contact belongs to exactly one User
- A User can have many Contacts
- The relationship is represented through a foreign key in the Contacts table
- The `user` property in the Contact entity contains the reference to the owning User

```java
// In Contact entity
@ManyToOne
@JoinColumn(name = "USER_ID")
private User user;

// In User entity
@OneToMany(mappedBy = "user", cascade = CascadeType.ALL, orphanRemoval = true)
private List<Contact> contacts = new ArrayList<>();
```

This bidirectional relationship allows efficient navigation from users to their contacts and from contacts back to their owning users.

## 7.2 Contact CRUD Operations

The Contact Management Module implements comprehensive CRUD (Create, Read, Update, Delete) operations for contact data.

### 7.2.1 Contact Creation

The application provides a dedicated form for adding new contacts:

```html
<form th:action="@{/user/contacts/process}" method="post" enctype="multipart/form-data">
    <input type="hidden" name="${_csrf.parameterName}" value="${_csrf.token}" />
    
    <div class="form-group">
        <label for="name">Name *</label>
        <input type="text" class="form-control" id="name" name="name" required />
    </div>
    
    <div class="form-group">
        <label for="secondName">Second Name/Nickname</label>
        <input type="text" class="form-control" id="secondName" name="secondName" />
    </div>
    
    <div class="form-group">
        <label for="work">Work/Profession</label>
        <input type="text" class="form-control" id="work" name="work" />
    </div>
    
    <div class="form-group">
        <label for="email">Email</label>
        <input type="email" class="form-control" id="email" name="email" />
    </div>
    
    <div class="form-group">
        <label for="phone">Phone</label>
        <input type="text" class="form-control" id="phone" name="phone" />
    </div>
    
    <div class="form-group">
        <label for="contactImage">Contact Image</label>
        <input type="file" class="form-control-file" id="contactImage" 
               name="contactImage" accept="image/*" />
    </div>
    
    <div class="form-group">
        <label for="description">Description/Notes</label>
        <textarea class="form-control" id="description" name="description" rows="3"></textarea>
    </div>
    
    <button type="submit" class="btn btn-primary">Save Contact</button>
</form>
```

The contact creation process is handled by the `ContactController`:

```java
@PostMapping("/process")
public String processContact(@ModelAttribute Contact contact,
                           @RequestParam(value = "contactImage", required = false) MultipartFile contactImage,
                           Principal principal,
                           RedirectAttributes redirectAttributes) {
    
    try {
        User user = userService.findUserByUsername(principal.getName());
        
        // Set contact owner
        contact.setUser(user);
        
        // Process contact image if provided
        if (contactImage != null && !contactImage.isEmpty()) {
            String imageUrl = fileStorageService.storeContactImage(contactImage, user.getId());
            contact.setImage(imageUrl);
        }
        
        // Save contact
        contactService.saveContact(contact);
        
        redirectAttributes.addFlashAttribute("successMessage", "Contact added successfully!");
        
        // Redirect based on referer or default to contacts page
        return "redirect:/user/contacts";
        
    } catch (Exception e) {
        redirectAttributes.addFlashAttribute("errorMessage", 
            "Error adding contact: " + e.getMessage());
        return "redirect:/user/contacts/add";
    }
}
```

### 7.2.2 Contact Retrieval

The application implements several methods for retrieving contacts:

1. **List All Contacts**:
```java
@GetMapping("/contacts")
public String showContacts(@RequestParam(value = "page", defaultValue = "0") Integer page,
                          Model model,
                          Principal principal) {
    
    User user = userService.findUserByUsername(principal.getName());
    
    // Pagination with 5 contacts per page
    Pageable pageable = PageRequest.of(page, 5);
    Page<Contact> contacts = contactService.findContactsByUser(user, pageable);
    
    model.addAttribute("contacts", contacts);
    model.addAttribute("currentPage", page);
    model.addAttribute("totalPages", contacts.getTotalPages());
    
    return "user/contacts";
}
```

2. **View Contact Details**:
```java
@GetMapping("/{id}")
public String showContactDetail(@PathVariable("id") Long contactId,
                               Principal principal,
                               Model model,
                               RedirectAttributes redirectAttributes) {
    
    User user = userService.findUserByUsername(principal.getName());
    Contact contact = contactService.findContactById(user, contactId);
    
    if (contact == null) {
        redirectAttributes.addFlashAttribute("errorMessage", 
            "Contact not found or you don't have permission to view it.");
        return "redirect:/user/contacts";
    }
    
    model.addAttribute("contact", contact);
    return "user/contact-detail";
}
```

3. **Filter Favorite Contacts**:
```java
@GetMapping("/favorites")
public String showFavoriteContacts(Model model, Principal principal) {
    User user = userService.findUserByUsername(principal.getName());
    List<Contact> favoriteContacts = contactService.findFavoriteContacts(user);
    
    model.addAttribute("contacts", favoriteContacts);
    model.addAttribute("title", "Favorite Contacts");
    
    return "user/favorite-contacts";
}
```

These retrieval methods ensure that users can only access their own contacts, maintaining data isolation and security.

### 7.2.3 Contact Update

The application provides functionality for updating existing contacts:

```java
@PostMapping("/update/{id}")
public String updateContact(@PathVariable("id") Long contactId,
                          @ModelAttribute Contact contact,
                          @RequestParam(value = "contactImage", required = false) MultipartFile contactImage,
                          Principal principal,
                          RedirectAttributes redirectAttributes) {
    
    try {
        User user = userService.findUserByUsername(principal.getName());
        Contact existingContact = contactService.findContactById(user, contactId);
        
        if (existingContact == null) {
            redirectAttributes.addFlashAttribute("errorMessage", 
                "Contact not found or you don't have permission to update it.");
            return "redirect:/user/contacts";
        }
        
        // Update contact properties
        existingContact.setName(contact.getName());
        existingContact.setSecondName(contact.getSecondName());
        existingContact.setWork(contact.getWork());
        existingContact.setEmail(contact.getEmail());
        existingContact.setPhone(contact.getPhone());
        existingContact.setDescription(contact.getDescription());
        
        // Process contact image if provided
        if (contactImage != null && !contactImage.isEmpty()) {
            String imageUrl = fileStorageService.storeContactImage(contactImage, user.getId());
            existingContact.setImage(imageUrl);
        }
        
        // Save updated contact
        contactService.saveContact(existingContact);
        
        redirectAttributes.addFlashAttribute("successMessage", "Contact updated successfully!");
        return "redirect:/user/contacts/" + contactId;
        
    } catch (Exception e) {
        redirectAttributes.addFlashAttribute("errorMessage", 
            "Error updating contact: " + e.getMessage());
        return "redirect:/user/contacts/update/" + contactId;
    }
}
```

This method includes:
- Ownership verification to ensure users can only update their own contacts
- Selective property updates to preserve existing data
- Image file handling for contact photos
- Proper error handling and user feedback

### 7.2.4 Contact Deletion

The application provides functionality for deleting contacts:

```java
@GetMapping("/delete/{id}")
public String deleteContact(@PathVariable("id") Long contactId,
                          Principal principal,
                          RedirectAttributes redirectAttributes) {
    
    try {
        User user = userService.findUserByUsername(principal.getName());
        Contact contact = contactService.findContactById(user, contactId);
        
        if (contact == null) {
            redirectAttributes.addFlashAttribute("errorMessage", 
                "Contact not found or you don't have permission to delete it.");
            return "redirect:/user/contacts";
        }
        
        // Delete contact
        contactService.deleteContact(user, contactId);
        
        redirectAttributes.addFlashAttribute("successMessage", "Contact deleted successfully!");
        return "redirect:/user/contacts";
        
    } catch (Exception e) {
        redirectAttributes.addFlashAttribute("errorMessage", 
            "Error deleting contact: " + e.getMessage());
        return "redirect:/user/contacts";
    }
}
```

The deletion process:
- Verifies the user owns the contact before allowing deletion
- Provides appropriate feedback messages for success or failure
- Redirects back to the contacts list after operation

## 7.3 Favorite Contacts Feature

The ContactManager application includes a special feature allowing users to mark specific contacts as favorites for quick access.

### 7.3.1 Favorite Flag

The Contact entity includes a boolean `favorite` flag that indicates whether a contact is marked as a favorite:

```java
@Entity
@Table(name = "CONTACTS")
public class Contact implements Serializable {
    // Other properties
    
    private boolean favorite;
    
    // Getters and setters
    
    public boolean isFavorite() {
        return favorite;
    }
    
    public void setFavorite(boolean favorite) {
        this.favorite = favorite;
    }
}
```

### 7.3.2 Toggle Favorite Status

The application provides functionality to toggle the favorite status of a contact:

```java
@GetMapping("/favorite/{id}")
public String toggleFavoriteStatus(@PathVariable("id") Long contactId,
                                 Principal principal,
                                 RedirectAttributes redirectAttributes,
                                 HttpServletRequest request) {
    
    try {
        User user = userService.findUserByUsername(principal.getName());
        Contact contact = contactService.findContactById(user, contactId);
        
        if (contact == null) {
            redirectAttributes.addFlashAttribute("errorMessage", 
                "Contact not found or you don't have permission to modify it.");
            return "redirect:/user/contacts";
        }
        
        // Toggle favorite status
        contact.setFavorite(!contact.isFavorite());
        contactService.saveContact(contact);
        
        String successMessage = contact.isFavorite() 
            ? "Contact added to favorites!" 
            : "Contact removed from favorites!";
        
        redirectAttributes.addFlashAttribute("successMessage", successMessage);
        
        // Redirect back to the referer page or to contacts page
        String referer = request.getHeader("Referer");
        return referer != null ? "redirect:" + referer : "redirect:/user/contacts";
        
    } catch (Exception e) {
        redirectAttributes.addFlashAttribute("errorMessage", 
            "Error updating favorite status: " + e.getMessage());
        return "redirect:/user/contacts";
    }
}
```

This method:
- Toggles the current favorite status (true to false, or false to true)
- Provides context-specific success messages
- Returns to the original page to maintain user context

### 7.3.3 Favorites View

The application provides a dedicated view for displaying only favorite contacts:

```java
@GetMapping("/favorites")
public String showFavoriteContacts(Model model, Principal principal) {
    User user = userService.findUserByUsername(principal.getName());
    List<Contact> favoriteContacts = contactService.findFavoriteContacts(user);
    
    model.addAttribute("contacts", favoriteContacts);
    model.addAttribute("title", "Favorite Contacts");
    
    return "user/favorite-contacts";
}
```

The implementation of `findFavoriteContacts` in the service layer:

```java
@Override
public List<Contact> findFavoriteContacts(User user) {
    return contactRepository.findByUserAndFavoriteTrue(user);
}
```

And the corresponding repository method:

```java
public interface ContactRepository extends JpaRepository<Contact, Long> {
    // Other methods
    
    List<Contact> findByUserAndFavoriteTrue(User user);
}
```

### 7.3.4 Favorite Indicator

In the contact list and detail views, favorite status is indicated visually:

```html
<div class="contact-card" th:each="contact : ${contacts}">
    <div class="contact-header">
        <h5 th:text="${contact.name}"></h5>
        <span class="favorite-indicator" th:if="${contact.favorite}">
            <i class="fas fa-star text-warning"></i>
        </span>
    </div>
    <!-- Other contact information -->
    <div class="contact-actions">
        <a th:href="@{'/user/contacts/favorite/' + ${contact.cId}}" class="btn btn-sm">
            <i class="fas" th:classappend="${contact.favorite ? 'fa-star text-warning' : 'fa-star-o'}"></i>
        </a>
        <!-- Other action buttons -->
    </div>
</div>
```

This visual feedback helps users quickly identify their favorite contacts and provides an intuitive way to toggle the status.

## 7.4 Contact Listing and Pagination

The Contact Management Module implements efficient listing and pagination features to handle large numbers of contacts.

### 7.4.1 Paginated Contact Listing

The application uses Spring Data's pagination support to implement paginated contact listings:

```java
@GetMapping("/contacts")
public String showContacts(@RequestParam(value = "page", defaultValue = "0") Integer page,
                          Model model,
                          Principal principal) {
    
    User user = userService.findUserByUsername(principal.getName());
    
    // Pagination with 5 contacts per page
    Pageable pageable = PageRequest.of(page, 5);
    Page<Contact> contacts = contactService.findContactsByUser(user, pageable);
    
    model.addAttribute("contacts", contacts);
    model.addAttribute("currentPage", page);
    model.addAttribute("totalPages", contacts.getTotalPages());
    
    return "user/contacts";
}
```

The service method:

```java
@Override
public Page<Contact> findContactsByUser(User user, Pageable pageable) {
    return contactRepository.findByUserOrderByNameAsc(user, pageable);
}
```

And the repository method:

```java
public interface ContactRepository extends JpaRepository<Contact, Long> {
    Page<Contact> findByUserOrderByNameAsc(User user, Pageable pageable);
    // Other methods
}
```

### 7.4.2 Pagination Controls

The application provides a pagination control component in the UI:

```html
<div class="pagination-container" th:if="${totalPages > 1}">
    <nav aria-label="Page navigation">
        <ul class="pagination justify-content-center">
            <!-- Previous page -->
            <li class="page-item" th:classappend="${currentPage == 0 ? 'disabled' : ''}">
                <a class="page-link" th:href="@{/user/contacts(page=${currentPage - 1})}">&laquo;</a>
            </li>
            
            <!-- Page numbers -->
            <li class="page-item" th:each="i : ${#numbers.sequence(0, totalPages - 1)}" 
                th:classappend="${currentPage == i ? 'active' : ''}">
                <a class="page-link" th:href="@{/user/contacts(page=${i})}" th:text="${i + 1}"></a>
            </li>
            
            <!-- Next page -->
            <li class="page-item" th:classappend="${currentPage + 1 == totalPages ? 'disabled' : ''}">
                <a class="page-link" th:href="@{/user/contacts(page=${currentPage + 1})}">&raquo;</a>
            </li>
        </ul>
    </nav>
</div>
```

This component provides:
- Links to navigate to previous and next pages
- Direct access to specific pages through numbered links
- Visual indication of the current page
- Disabled controls for boundary conditions (first and last pages)

## 7.5 Data Validation and Error Handling

The Contact Management Module implements comprehensive data validation and error handling to ensure data integrity and provide a smooth user experience.

### 7.5.1 Contact Validation

The application applies validation at multiple levels:

1. **Entity-Level Validation**:
```java
@Entity
@Table(name = "CONTACTS")
public class Contact implements Serializable {
    
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "contact_seq")
    @SequenceGenerator(name = "contact_seq", sequenceName = "CONTACT_SEQ", allocationSize = 1)
    private Long cId;
    
    @NotBlank(message = "Name is required")
    @Size(min = 2, max = 100, message = "Name must be between 2 and 100 characters")
    @Column(nullable = false, length = 100)
    private String name;
    
    @Email(message = "Please provide a valid email address")
    @Column(length = 100)
    private String email;
    
    @Pattern(regexp = "^[0-9+\\-\\s]*$", message = "Phone number can only contain digits, +, -, and spaces")
    @Column(length = 20)
    private String phone;
    
    // Other properties with validation
}
```

2. **Controller-Level Validation**:
```java
@PostMapping("/process")
public String processContact(@Valid @ModelAttribute Contact contact,
                           BindingResult result,
                           @RequestParam(value = "contactImage", required = false) MultipartFile contactImage,
                           Principal principal,
                           Model model) {
    
    if (result.hasErrors()) {
        return "user/add-contact";
    }
    
    // Process and save valid contact
    // ...
}
```

3. **JavaScript Validation**:
```javascript
$(document).ready(function() {
    $("#contactForm").validate({
        rules: {
            name: {
                required: true,
                minlength: 2,
                maxlength: 100
            },
            email: {
                email: true
            },
            phone: {
                pattern: /^[0-9+\-\s]*$/
            }
            // Other validation rules
        },
        messages: {
            name: {
                required: "Please enter a name",
                minlength: "Name must be at least 2 characters long",
                maxlength: "Name cannot exceed 100 characters"
            },
            email: {
                email: "Please enter a valid email address"
            },
            phone: {
                pattern: "Phone number can only contain digits, +, -, and spaces"
            }
            // Other error messages
        }
    });
});
```

### 7.5.2 Error Handling

The application implements structured error handling:

1. **Controller-Level Error Handling**:
```java
@ExceptionHandler(Exception.class)
public String handleException(Exception e, RedirectAttributes redirectAttributes) {
    redirectAttributes.addFlashAttribute("errorMessage", 
        "An error occurred: " + e.getMessage());
    return "redirect:/user/contacts";
}
```

2. **Service-Level Error Handling**:
```java
@Override
public Contact saveContact(Contact contact) {
    try {
        return contactRepository.save(contact);
    } catch (DataIntegrityViolationException e) {
        throw new ContactManagementException("Could not save contact. Data integrity violation.");
    } catch (Exception e) {
        throw new ContactManagementException("An error occurred while saving the contact: " + e.getMessage());
    }
}
```

3. **Custom Exception Types**:
```java
public class ContactManagementException extends RuntimeException {
    public ContactManagementException(String message) {
        super(message);
    }
    
    public ContactManagementException(String message, Throwable cause) {
        super(message, cause);
    }
}
```

### 7.5.3 User Feedback

The application provides clear feedback for both successful operations and errors:

1. **Success Messages**:
```java
redirectAttributes.addFlashAttribute("successMessage", "Contact added successfully!");
```

2. **Error Messages**:
```java
redirectAttributes.addFlashAttribute("errorMessage", "Error adding contact: " + e.getMessage());
```

3. **Validation Error Display**:
```html
<div class="form-group">
    <label for="name">Name *</label>
    <input type="text" class="form-control" id="name" name="name" th:value="${contact.name}" />
    <small class="text-danger" th:if="${#fields.hasErrors('contact.name')}" th:errors="${contact.name}"></small>
</div>
```

4. **Global Error Summary**:
```html
<div class="alert alert-danger" th:if="${#fields.hasErrors('*')}">
    <h4>Please correct the following errors:</h4>
    <ul>
        <li th:each="err : ${#fields.errors('*')}" th:text="${err}"></li>
    </ul>
</div>
```

The Contact Management Module provides a comprehensive set of features for maintaining a personal contact database. With robust validation, efficient pagination, and intuitive UI elements like the favorites feature, users can effectively organize and manage their contacts while the system ensures data integrity and security.

---

# Chapter 8: Dynamic Search Functionality

## 8.1 Search Implementation Overview

The Dynamic Search Functionality is one of the key features of the ContactManager application, allowing users to quickly find specific contacts based on various search criteria. This feature enhances the usability of the application, especially for users with large contact lists.

### 8.1.1 Search Architecture

The search functionality is implemented using a multi-layered approach:

1. **Presentation Layer**:
   - Search form in the user interface
   - Real-time search suggestions (optional)
   - Search results display

2. **Controller Layer**:
   - Processing search requests
   - Parameter validation
   - Coordination between UI and business logic

3. **Service Layer**:
   - Search logic implementation
   - Query construction
   - Result processing

4. **Repository Layer**:
   - Dynamic query execution
   - Database interactions
   - Results retrieval

This layered approach ensures separation of concerns and allows for the implementation of complex search functionality while maintaining clean code organization.

### 8.1.2 Search Capabilities

The application supports several search capabilities:

1. **Field-Specific Search**:
   - Name-based search
   - Email-based search
   - Phone number search
   - Work/profession search

2. **Multi-Field Search**:
   - Search across all fields simultaneously
   - Weighted relevance scoring

3. **Advanced Filtering**:
   - Favorite contacts filtering
   - Combined field and criteria search

4. **Result Handling**:
   - Pagination for large result sets
   - Sorting options
   - Relevance ranking

### 8.1.3 Technology Stack for Search

The search functionality leverages several technologies:

1. **Spring Data JPA**:
   - Core data access framework
   - Method query generation
   - Pagination support

2. **JPA Criteria API**:
   - Dynamic query construction
   - Complex condition building
   - Type-safe queries

3. **Specification Pattern**:
   - Composable search criteria
   - Reusable query components
   - Expressive query building

4. **Thymeleaf + JavaScript**:
   - Interactive search form
   - Real-time feedback
   - Enhanced user experience

## 8.2 Query Construction

The ContactManager application implements dynamic query construction to support flexible search operations.

### 8.2.1 JPA Specifications

The core of the search functionality is based on Spring Data JPA's Specification pattern, which allows for the dynamic construction of complex queries:

```java
@Service
public class ContactSearchService {
    
    @Autowired
    private ContactRepository contactRepository;
    
    public Page<Contact> searchContacts(User user, String field, String keyword, Pageable pageable) {
        Specification<Contact> spec = buildSearchSpecification(user, field, keyword);
        return contactRepository.findAll(spec, pageable);
    }
    
    public Specification<Contact> buildSearchSpecification(User user, String field, String keyword) {
        return (root, query, criteriaBuilder) -> {
            query.distinct(true);
            
            // Base condition: contacts belong to the current user
            Predicate userPredicate = criteriaBuilder.equal(root.get("user"), user);
            
            // Search condition based on the selected field
            Predicate searchPredicate;
            
            if (field == null || field.isEmpty() || field.equals("all")) {
                // Search across all relevant fields
                Predicate namePredicate = criteriaBuilder.like(
                    criteriaBuilder.lower(root.get("name")), 
                    "%" + keyword.toLowerCase() + "%"
                );
                
                Predicate secondNamePredicate = criteriaBuilder.like(
                    criteriaBuilder.lower(root.get("secondName")), 
                    "%" + keyword.toLowerCase() + "%"
                );
                
                Predicate emailPredicate = criteriaBuilder.like(
                    criteriaBuilder.lower(root.get("email")), 
                    "%" + keyword.toLowerCase() + "%"
                );
                
                Predicate phonePredicate = criteriaBuilder.like(
                    root.get("phone"), 
                    "%" + keyword + "%"
                );
                
                Predicate workPredicate = criteriaBuilder.like(
                    criteriaBuilder.lower(root.get("work")), 
                    "%" + keyword.toLowerCase() + "%"
                );
                
                searchPredicate = criteriaBuilder.or(
                    namePredicate, secondNamePredicate, emailPredicate, 
                    phonePredicate, workPredicate
                );
            } else {
                // Field-specific search
                searchPredicate = criteriaBuilder.like(
                    criteriaBuilder.lower(root.get(field)), 
                    "%" + keyword.toLowerCase() + "%"
                );
            }
            
            // Combine user predicate and search predicate
            return criteriaBuilder.and(userPredicate, searchPredicate);
        };
    }
}
```

The `buildSearchSpecification` method creates a dynamic query based on the selected field and keyword, always ensuring that only contacts belonging to the current user are returned.

### 8.2.2 Repository Integration

The contact repository is extended to support specification-based queries:

```java
public interface ContactRepository extends JpaRepository<Contact, Long>, JpaSpecificationExecutor<Contact> {
    // Standard repository methods
    Page<Contact> findByUserOrderByNameAsc(User user, Pageable pageable);
    Contact findByUserAndCId(User user, Long cId);
    List<Contact> findByUserAndFavoriteTrue(User user);
    
    // Other methods
}
```

The `JpaSpecificationExecutor` interface adds the ability to execute specifications against the repository:

```java
public interface JpaSpecificationExecutor<T> {
    Optional<T> findOne(Specification<T> spec);
    List<T> findAll(Specification<T> spec);
    Page<T> findAll(Specification<T> spec, Pageable pageable);
    List<T> findAll(Specification<T> spec, Sort sort);
    long count(Specification<T> spec);
}
```

### 8.2.3 Advanced Query Construction

For more complex search scenarios, the application may implement advanced query construction techniques:

```java
public Specification<Contact> buildAdvancedSearchSpecification(SearchCriteria criteria) {
    return (root, query, criteriaBuilder) -> {
        List<Predicate> predicates = new ArrayList<>();
        
        // User ownership predicate (always applied)
        predicates.add(criteriaBuilder.equal(root.get("user"), criteria.getUser()));
        
        // Name search
        if (criteria.getName() != null && !criteria.getName().isEmpty()) {
            predicates.add(criteriaBuilder.like(
                criteriaBuilder.lower(root.get("name")),
                "%" + criteria.getName().toLowerCase() + "%"
            ));
        }
        
        // Email search
        if (criteria.getEmail() != null && !criteria.getEmail().isEmpty()) {
            predicates.add(criteriaBuilder.like(
                criteriaBuilder.lower(root.get("email")),
                "%" + criteria.getEmail().toLowerCase() + "%"
            ));
        }
        
        // Phone search
        if (criteria.getPhone() != null && !criteria.getPhone().isEmpty()) {
            predicates.add(criteriaBuilder.like(
                root.get("phone"),
                "%" + criteria.getPhone() + "%"
            ));
        }
        
        // Favorite filter
        if (criteria.isFavoriteOnly()) {
            predicates.add(criteriaBuilder.isTrue(root.get("favorite")));
        }
        
        // Combine all predicates with AND
        return criteriaBuilder.and(predicates.toArray(new Predicate[0]));
    };
}
```

This approach allows for multiple search criteria to be combined in a single query, providing more targeted search results.

## 8.3 Real-time Search Feature

The ContactManager application implements real-time search functionality to enhance the user experience by providing instant feedback as users type their search queries.

### 8.3.1 Client-Side Implementation

The real-time search functionality is implemented using JavaScript and AJAX:

```javascript
$(document).ready(function() {
    const searchInput = $('#searchKeyword');
    const searchResultsContainer = $('#searchResults');
    const searchForm = $('#searchForm');
    
    let searchTimer;
    
    searchInput.on('input', function() {
        const keyword = $(this).val().trim();
        
        // Clear previous timer
        clearTimeout(searchTimer);
        
        // Don't search for short keywords
        if (keyword.length < 2) {
            searchResultsContainer.empty();
            return;
        }
        
        // Set a timer to delay the search until the user stops typing
        searchTimer = setTimeout(function() {
            // Get the selected search field
            const field = $('#searchField').val();
            
            // Perform AJAX search
            $.ajax({
                url: '/user/contacts/search/suggestions',
                data: {
                    field: field,
                    keyword: keyword
                },
                method: 'GET',
                success: function(response) {
                    displaySearchSuggestions(response);
                }
            });
        }, 300); // 300ms delay
    });
    
    function displaySearchSuggestions(suggestions) {
        searchResultsContainer.empty();
        
        if (suggestions.length === 0) {
            searchResultsContainer.append(
                '<div class="no-results">No contacts found</div>'
            );
            return;
        }
        
        const ul = $('<ul class="suggestion-list"></ul>');
        
        suggestions.forEach(function(contact) {
            const li = $(
                '<li class="suggestion-item">' +
                    '<img src="' + (contact.image || '/images/default-contact.png') + '" class="suggestion-image">' +
                    '<div class="suggestion-info">' +
                        '<div class="suggestion-name">' + contact.name + '</div>' +
                        '<div class="suggestion-details">' + 
                            (contact.email || '') + (contact.phone ? ' | ' + contact.phone : '') +
                        '</div>' +
                    '</div>' +
                '</li>'
            );
            
            li.on('click', function() {
                window.location.href = '/user/contacts/' + contact.cId;
            });
            
            ul.append(li);
        });
        
        searchResultsContainer.append(ul);
    }
    
    // Handle form submission
    searchForm.on('submit', function() {
        // Clear search suggestions
        searchResultsContainer.empty();
    });
});
```

### 8.3.2 Server-Side Implementation

The server-side component provides an API endpoint for retrieving search suggestions:

```java
@GetMapping("/search/suggestions")
@ResponseBody
public List<ContactSuggestionDTO> getSearchSuggestions(
        @RequestParam(required = false) String field,
        @RequestParam String keyword,
        Principal principal) {
    
    User user = userService.findUserByUsername(principal.getName());
    
    // Limit to top 5 suggestions
    Pageable pageable = PageRequest.of(0, 5);
    Page<Contact> searchResults = contactSearchService.searchContacts(user, field, keyword, pageable);
    
    // Convert to DTOs for JSON response
    return searchResults.getContent().stream()
        .map(this::convertToSuggestionDTO)
        .collect(Collectors.toList());
}

private ContactSuggestionDTO convertToSuggestionDTO(Contact contact) {
    ContactSuggestionDTO dto = new ContactSuggestionDTO();
    dto.setCId(contact.getCId());
    dto.setName(contact.getName());
    dto.setEmail(contact.getEmail());
    dto.setPhone(contact.getPhone());
    dto.setImage(contact.getImage());
    return dto;
}
```

### 8.3.3 Data Transfer Object

A dedicated DTO is used for search suggestions to minimize data transfer:

```java
public class ContactSuggestionDTO {
    private Long cId;
    private String name;
    private String email;
    private String phone;
    private String image;
    
    // Getters and setters
}
```

## 8.4 Search Optimization Techniques

The ContactManager application implements several optimization techniques to ensure efficient search operations, especially for users with large contact lists.

### 8.4.1 Database Indexing

The database schema includes appropriate indexes to accelerate search queries:

```sql
-- Index for name-based searches
CREATE INDEX IDX_CONTACT_NAME ON CONTACTS (USER_ID, LOWER(NAME));

-- Index for email-based searches
CREATE INDEX IDX_CONTACT_EMAIL ON CONTACTS (USER_ID, LOWER(EMAIL));

-- Index for phone-based searches
CREATE INDEX IDX_CONTACT_PHONE ON CONTACTS (USER_ID, PHONE);

-- Composite index for favorite contacts
CREATE INDEX IDX_CONTACT_FAVORITE ON CONTACTS (USER_ID, FAVORITE);
```

These indexes significantly improve search performance by allowing the database to quickly locate matching records without scanning the entire table.

### 8.4.2 Query Caching

The application may implement query result caching to reduce database load for repeated searches:

```java
@Service
public class ContactSearchService {
    
    @Autowired
    private ContactRepository contactRepository;
    
    @Autowired
    private CacheManager cacheManager;
    
    @Cacheable(value = "contactSearchCache", key = "#user.id + '_' + #field + '_' + #keyword + '_' + #pageable.pageNumber")
    public Page<Contact> searchContacts(User user, String field, String keyword, Pageable pageable) {
        Specification<Contact> spec = buildSearchSpecification(user, field, keyword);
        return contactRepository.findAll(spec, pageable);
    }
    
    // Cache eviction when contacts are modified
    @CacheEvict(value = "contactSearchCache", key = "#contact.user.id + '_*'")
    public Contact saveContact(Contact contact) {
        return contactRepository.save(contact);
    }
    
    @CacheEvict(value = "contactSearchCache", key = "#user.id + '_*'")
    public void deleteContact(User user, Long contactId) {
        contactRepository.deleteById(contactId);
    }
    
    // Other methods
}
```

### 8.4.3 Pagination and Lazy Loading

The application uses pagination for search results to limit the amount of data retrieved and processed:

```java
@GetMapping("/search")
public String searchContacts(
        @RequestParam(required = false) String field,
        @RequestParam String keyword,
        @RequestParam(defaultValue = "0") int page,
        Model model,
        Principal principal) {
    
    User user = userService.findUserByUsername(principal.getName());
    
    // Pagination with 5 results per page
    Pageable pageable = PageRequest.of(page, 5);
    Page<Contact> searchResults = contactSearchService.searchContacts(user, field, keyword, pageable);
    
    model.addAttribute("contacts", searchResults);
    model.addAttribute("currentPage", page);
    model.addAttribute("totalPages", searchResults.getTotalPages());
    model.addAttribute("field", field);
    model.addAttribute("keyword", keyword);
    
    return "user/search-results";
}
```

Additionally, the application may implement lazy loading of contact details to further improve performance:

```html
<div class="search-results">
    <div class="contact-card" th:each="contact : ${contacts}" th:data-id="${contact.cId}">
        <div class="contact-basic-info">
            <img th:src="${contact.image != null ? contact.image : '/images/default-contact.png'}" 
                 class="contact-image" />
            <div class="contact-primary-details">
                <h5 th:text="${contact.name}"></h5>
                <p th:if="${contact.email}" th:text="${contact.email}"></p>
                <p th:if="${contact.phone}" th:text="${contact.phone}"></p>
            </div>
        </div>
        
        <!-- Lazy-loaded details that appear when clicked -->
        <div class="contact-extended-info" style="display: none;">
            <div class="spinner-border text-primary" role="status">
                <span class="sr-only">Loading...</span>
            </div>
        </div>
    </div>
</div>

<script>
    $('.contact-card').on('click', function() {
        const contactId = $(this).data('id');
        const extendedInfoDiv = $(this).find('.contact-extended-info');
        
        if (extendedInfoDiv.children().length === 1) {
            // Load extended information via AJAX
            $.ajax({
                url: '/user/contacts/' + contactId + '/details',
                method: 'GET',
                success: function(response) {
                    extendedInfoDiv.html(response);
                    extendedInfoDiv.slideDown();
                }
            });
        } else {
            // Toggle visibility of already loaded details
            extendedInfoDiv.slideToggle();
        }
    });
</script>
```

## 8.5 User Interface Integration

The search functionality is seamlessly integrated into the user interface to provide an intuitive and efficient user experience.

### 8.5.1 Search Form

The application includes a search form in the navigation or sidebar:

```html
<div class="search-container">
    <form id="searchForm" th:action="@{/user/contacts/search}" method="get">
        <div class="input-group">
            <div class="input-group-prepend">
                <select id="searchField" name="field" class="custom-select">
                    <option value="all">All Fields</option>
                    <option value="name">Name</option>
                    <option value="email">Email</option>
                    <option value="phone">Phone</option>
                    <option value="work">Work</option>
                </select>
            </div>
            
            <input type="text" id="searchKeyword" name="keyword" class="form-control" 
                   placeholder="Search contacts..." required autocomplete="off" />
                   
            <div class="input-group-append">
                <button type="submit" class="btn btn-primary">
                    <i class="fas fa-search"></i>
                </button>
            </div>
        </div>
        
        <!-- Real-time search suggestions container -->
        <div id="searchResults" class="search-suggestions"></div>
    </form>
</div>
```

### 8.5.2 Search Results Page

The search results are displayed in a dedicated page with filtering and sorting options:

```html
<div class="search-results-container">
    <div class="search-header">
        <h4>Search Results for "<span th:text="${keyword}"></span>"</h4>
        <p th:if="${contacts.totalElements == 0}">No contacts found matching your search criteria.</p>
        <p th:if="${contacts.totalElements > 0}">
            Found <span th:text="${contacts.totalElements}"></span> contacts
        </p>
    </div>
    
    <div class="filter-options" th:if="${contacts.totalElements > 0}">
        <div class="sort-by">
            <label>Sort by:</label>
            <a th:href="@{/user/contacts/search(field=${field}, keyword=${keyword}, sort='name', direction='asc')}"
               th:class="${param.sort == null || param.sort[0] == 'name' ? 'active' : ''}">Name</a>
            <a th:href="@{/user/contacts/search(field=${field}, keyword=${keyword}, sort='email', direction='asc')}"
               th:class="${param.sort != null && param.sort[0] == 'email' ? 'active' : ''}">Email</a>
        </div>
        
        <div class="filter-by">
            <label>Show:</label>
            <a th:href="@{/user/contacts/search(field=${field}, keyword=${keyword}, favorite=true)}"
               th:class="${param.favorite != null && param.favorite[0] == 'true' ? 'active' : ''}">Favorites Only</a>
            <a th:href="@{/user/contacts/search(field=${field}, keyword=${keyword})}"
               th:class="${param.favorite == null ? 'active' : ''}">All Contacts</a>
        </div>
    </div>
    
    <!-- Contact list -->
    <div class="contact-list">
        <div class="contact-card" th:each="contact : ${contacts}">
            <!-- Contact display code -->
        </div>
    </div>
    
    <!-- Pagination controls -->
    <div class="pagination-container" th:if="${totalPages > 1}">
        <nav aria-label="Search results pages">
            <ul class="pagination justify-content-center">
                <!-- Pagination controls code -->
            </ul>
        </nav>
    </div>
</div>
```

### 8.5.3 Search Controller

The search functionality is exposed through a dedicated controller:

```java
@Controller
@RequestMapping("/user/contacts")
public class ContactSearchController {
    
    @Autowired
    private UserService userService;
    
    @Autowired
    private ContactSearchService contactSearchService;
    
    @GetMapping("/search")
    public String searchContacts(
            @RequestParam(required = false) String field,
            @RequestParam String keyword,
            @RequestParam(defaultValue = "0") int page,
            @RequestParam(required = false) String sort,
            @RequestParam(required = false) String direction,
            @RequestParam(required = false) Boolean favorite,
            Model model,
            Principal principal) {
        
        User user = userService.findUserByUsername(principal.getName());
        
        // Set up sorting
        Sort.Direction sortDirection = direction != null && direction.equals("desc") 
            ? Sort.Direction.DESC : Sort.Direction.ASC;
        String sortField = sort != null ? sort : "name";
        Sort sorting = Sort.by(sortDirection, sortField);
        
        // Set up pagination
        Pageable pageable = PageRequest.of(page, 5, sorting);
        
        // Build search criteria
        SearchCriteria criteria = new SearchCriteria();
        criteria.setUser(user);
        criteria.setField(field);
        criteria.setKeyword(keyword);
        criteria.setFavoriteOnly(favorite != null && favorite);
        
        // Execute search
        Page<Contact> searchResults = contactSearchService.searchContacts(criteria, pageable);
        
        // Prepare model
        model.addAttribute("contacts", searchResults);
        model.addAttribute("currentPage", page);
        model.addAttribute("totalPages", searchResults.getTotalPages());
        model.addAttribute("field", field);
        model.addAttribute("keyword", keyword);
        model.addAttribute("sort", sortField);
        model.addAttribute("direction", sortDirection.name().toLowerCase());
        model.addAttribute("reverseSortDirection", sortDirection == Sort.Direction.ASC ? "desc" : "asc");
        model.addAttribute("favorite", favorite);
        
        return "user/search-results";
    }
    
    // Other methods for search suggestions, etc.
}
```

The Dynamic Search Functionality enhances the user experience of the ContactManager application by providing powerful search capabilities that allow users to quickly find the contacts they need. By implementing efficient query construction, real-time search features, and optimization techniques, the application delivers responsive search functionality even for large contact collections.

---

# Chapter 9: UI/UX Design

## 9.1 Design Principles and Guidelines

The ContactManager application follows established design principles and guidelines to ensure a consistent and intuitive user experience.

### 9.1.1 Responsive Design

The application is designed to be responsive, adapting to different screen sizes and devices:
- Mobile-first design approach
- Fluid layouts for desktop and tablet screens
- Optimized content scaling for high-resolution displays

### 9.1.2 Color Scheme

The application uses a consistent color scheme to maintain brand consistency:
- Primary colors: #4CAF50 (green) and #2196F3 (blue)
- Secondary colors: #FFC107 (yellow) and #9E9E9E (grey)
- Grayscale for backgrounds and text

### 9.1.3 Typography

The application uses a clear and readable typography:
- Sans-serif font for headings and buttons
- Serif font for body text
- Consistent line height and letter spacing

### 9.1.4 Iconography

The application uses icons to visually represent actions and states:
- Consistent icon style and size
- Contextual icons for different user interactions

### 9.1.5 Layout Consistency

The application maintains a consistent layout structure across different pages:
- Header, sidebar, and main content area
- Consistent navigation and action buttons
- Clear separation of sections

### 9.1.6 User Feedback

The application provides clear and concise feedback to users:
- Informative tooltips and popovers
- Visual indicators for form validation
- Feedback messages for successful operations

## 9.2 Responsive Design Implementation

The application is implemented using Bootstrap 4, a popular front-end framework for responsive design:
- Grid system for layout flexibility
- Media queries for breakpoints
- Utility classes for common styles

### 9.2.1 Breakpoints

The application uses the following Bootstrap breakpoints:
- Extra small devices (phones, less than 576px)
- Small devices (tablets, 576px and up)
- Medium devices (desktops, 768px and up)
- Large devices (laptops, 992px and up)
- Extra large devices (desktops, 1200px and up)

### 9.2.2 Grid System

Bootstrap's grid system is used to create a flexible layout:
- Rows and columns for content arrangement
- Offset classes for spacing
- Nesting for complex layouts

### 9.2.3 Utility Classes

Bootstrap utility classes are used for common styles:
- Margins, paddings, and spacing
- Text alignment and transformations
- Visibility and display properties

## 9.3 Desktop Interface Analysis

The desktop interface is designed to be intuitive and efficient:
- Navigation menu for easy access to different sections
- Sidebar for secondary actions and settings
- Main content area for primary tasks

### 9.3.1 Navigation Menu

The application includes a navigation menu in the sidebar:
- Home, contacts, profile, and settings sections
- Icons and labels for quick identification
- Dropdown menus for sub-sections

### 9.3.2 Sidebar

The sidebar contains secondary actions and settings:
- User profile and settings
- Search functionality
- Quick actions and shortcuts

### 9.3.3 Main Content Area

The main content area is divided into sections:
- Contact list and details
- Profile management
- Settings and preferences

## 9.4 Mobile Interface Analysis

The mobile interface is designed to be accessible and easy to use:
- Hamburger menu for navigation
- Tabs for different sections
- Minimalist design for space efficiency

### 9.4.1 Navigation Menu

The mobile interface includes a hamburger menu for navigation:
- Home, contacts, profile, and settings sections
- Icons and labels for quick identification
- Dropdown menus for sub-sections

### 9.4.2 Tabs

The mobile interface uses tabs for different sections:
- Contact list, profile, and settings
- Icons and labels for quick access

### 9.4.3 Minimalist Design

The mobile interface is designed with minimalism in mind:
- Icons and text labels for actions
- Minimalist design for space efficiency
- Focus on primary tasks

## 9.5 User Experience Considerations

The application is designed with user experience in mind:
- Intuitive and consistent navigation
- Clear and concise feedback
- Efficient and smooth interactions

### 9.5.1 Navigation Consistency

The application maintains a consistent navigation structure across different pages:
- Home, contacts, profile, and settings sections
- Icons and labels for quick identification
- Dropdown menus for sub-sections

### 9.5.2 Feedback System

The application provides clear and concise feedback to users:
- Informative tooltips and popovers
- Visual indicators for form validation
- Feedback messages for successful operations

### 9.5.3 Interaction Flow

The application follows a logical and intuitive interaction flow:
- User authentication and profile management
- Contact management and search
- Settings and preferences

---

# Chapter 10: Code Structure

## 10.1 Package Organization

The ContactManager application is organized into several packages to maintain a clear separation of concerns:

- `com.example.contactmanager`: Main application package
- `com.example.contactmanager.controller`: Controller classes
- `com.example.contactmanager.service`: Service classes
- `com.example.contactmanager.repository`: Repository classes
- `com.example.contactmanager.entity`: Entity classes
- `com.example.contactmanager.security`: Security configuration
- `com.example.contactmanager.util`: Utility classes

### 10.1.1 Main Application Package

The main application package contains:
- `Application`: Main entry point
- `config`: Configuration classes
- `controller`: Controller classes
- `service`: Service classes
- `repository`: Repository classes
- `entity`: Entity classes
- `security`: Security configuration
- `util`: Utility classes

### 10.1.2 Controller Package

The controller package contains:
- `UserController`: User-related controllers
- `ContactController`: Contact-related controllers
- `SearchController`: Search-related controllers
- `ProfileController`: Profile-related controllers
- `SettingsController`: Settings-related controllers

### 10.1.3 Service Package

The service package contains:
- `UserService`: User-related services
- `ContactService`: Contact-related services
- `SearchService`: Search-related services
- `ProfileService`: Profile-related services
- `SettingsService`: Settings-related services

### 10.1.4 Repository Package

The repository package contains:
- `UserRepository`: User-related repositories
- `ContactRepository`: Contact-related repositories
- `SearchRepository`: Search-related repositories
- `ProfileRepository`: Profile-related repositories
- `SettingsRepository`: Settings-related repositories

### 10.1.5 Entity Package

The entity package contains:
- `User`: User entity
- `Contact`: Contact entity
- `SearchCriteria`: Search criteria entity
- `Profile`: Profile entity
- `Settings`: Settings entity

### 10.1.6 Security Package

The security package contains:
- `SecurityConfiguration`: Security configuration class
- `CustomUserDetailsService`: Custom user details service
- `OAuth2UserServiceImpl`: OAuth2 user service implementation
- `PasswordResetService`: Password reset service
- `SecurityService`: Security service

### 10.1.7 Utility Package

The utility package contains:
- `FileStorageService`: File storage service
- `EmailService`: Email service
- `SearchService`: Search service
- `ProfileService`: Profile service
- `SettingsService`: Settings service

## 10.2 Controllers Implementation

The ContactManager application is implemented using Spring MVC, a popular web framework for Java-based web applications. The following sections describe the implementation of different controllers.

### 10.2.1 UserController

The `UserController` class handles user-related operations:
- Registration
- Login
- Profile management
- Password reset

### 10.2.2 ContactController

The `ContactController` class handles contact-related operations:
- Adding new contacts
- Viewing contact details
- Updating existing contacts
- Deleting contacts
- Marking contacts as favorites

### 10.2.3 SearchController

The `SearchController` class handles search-related operations:
- Searching for contacts
- Displaying search results

### 10.2.4 ProfileController

The `ProfileController` class handles profile-related operations:
- Viewing profile information
- Updating profile details

### 10.2.5 SettingsController

The `SettingsController` class handles settings-related operations:
- Managing user preferences
- Updating security settings

## 10.3 Service Layer

The ContactManager application is implemented using a service-oriented architecture. The following sections describe the implementation of different services.

### 10.3.1 UserService

The `UserService` class handles user-related operations:
- User registration
- User authentication
- User profile management
- Password reset

### 10.3.2 ContactService

The `ContactService` class handles contact-related operations:
- Adding new contacts
- Retrieving contact details
- Updating existing contacts
- Deleting contacts
- Marking contacts as favorites

### 10.3.3 SearchService

The `SearchService` class handles search-related operations:
- Building search specifications
- Executing search queries
- Processing search results

### 10.3.4 ProfileService

The `ProfileService` class handles profile-related operations:
- Retrieving profile information
- Updating profile details

### 10.3.5 SettingsService

The `SettingsService` class handles settings-related operations:
- Managing user preferences
- Updating security settings

## 10.4 Repository Layer

The ContactManager application is implemented using Spring Data JPA, a popular data access framework for Java-based applications. The following sections describe the implementation of different repositories.

### 10.4.1 UserRepository

The `UserRepository` interface extends `JpaRepository` and provides methods for user-related operations:
- Finding users by email or username
- Checking email and username existence
- Saving and updating users

### 10.4.2 ContactRepository

The `ContactRepository` interface extends `JpaRepository` and provides methods for contact-related operations:
- Finding contacts by user and name
- Finding favorite contacts
- Saving and updating contacts

### 10.4.3 PasswordResetTokenRepository

The `PasswordResetTokenRepository` interface extends `JpaRepository` and provides methods for password reset token-related operations:
- Finding tokens by user and expiry date
- Saving and deleting tokens

### 10.4.4 PersistentLoginRepository

The `PersistentLoginRepository` interface extends `JpaRepository` and provides methods for persistent login-related operations:
- Finding login sessions by username
- Saving and deleting login sessions

## 10.5 Entity Classes

The ContactManager application is implemented using JPA annotations to map Java classes to database tables. The following sections describe the implementation of different entity classes.

### 10.5.1 User Entity

The `User` entity represents the user account and profile information:
- `id`: Primary key
- `name`: User's full name
- `email`: User's email address
- `password`: BCrypt-hashed password
- `username`: User's username
- `role`: User's role
- `enabled`: Flag to activate/deactivate user accounts
- `imageUrl`: Path to the user's profile image
- `about`: Additional information about the user
- `dateOfBirth`: User's date of birth
- `phone`: User's phone number
- `registrationDate`: Timestamp for user registration
- `lastLoginDate`: Timestamp for user last login
- `contacts`: List of contacts associated with the user

### 10.5.2 Contact Entity

The `Contact` entity represents the contact information:
- `cId`: Primary key
- `name`: Contact's name
- `secondName`: Contact's secondary name or nickname
- `work`: Contact's work information or job title
- `email`: Contact's email address
- `phone`: Contact's phone number
- `image`: Path to the contact's image
- `description`: Additional notes about the contact
- `favorite`: Boolean flag indicating if the contact is marked as a favorite
- `user`: Reference to the owning user

### 10.5.3 PasswordResetToken Entity

The `PasswordResetToken` entity represents the password reset token:
- `tokenId`: Primary key
- `token`: Secure random token for password reset validation
- `user`: Reference to the user
- `expiryDate`: Timestamp for token expiration

### 10.5.4 PersistentLogin Entity

The `PersistentLogin` entity represents the persistent login session:
- `series`: Primary key that identifies a login session
- `token`: Security token that authenticates the user
- `username`: User identifier
- `lastUsed`: Timestamp for tracking token usage

## 10.6 Utility Classes

The ContactManager application includes several utility classes to support different functionalities:

### 10.6.1 FileStorageService

The `FileStorageService` class handles file storage operations:
- Storing profile images
- Storing contact images

### 10.6.2 EmailService

The `EmailService` class handles email operations:
- Sending welcome emails
- Sending password reset emails

### 10.6.3 SearchService

The `SearchService` class handles search operations:
- Building search specifications
- Executing search queries
- Processing search results

### 10.6.4 ProfileService

The `ProfileService` class handles profile operations:
- Retrieving profile information
- Updating profile details

### 10.6.5 SettingsService

The `SettingsService` class handles settings operations:
- Managing user preferences
- Updating security settings

---

# Chapter 11: API Documentation

## 11.1 RESTful API Design

The ContactManager application is implemented using RESTful API principles. The following sections describe the implementation of different endpoints.

### 11.1.1 Endpoints

The application includes the following endpoints:
- `/user`: User-related operations
- `/contacts`: Contact-related operations
- `/search`: Search-related operations
- `/profile`: Profile-related operations
- `/settings`: Settings-related operations

### 11.1.2 Request/Response Formats

The application uses JSON as the primary format for requests and responses. The following sections describe the implementation of different request and response formats.

#### 11.1.2.1 JSON

The application uses Jackson to serialize and deserialize JSON objects. The following sections describe the implementation of different JSON formats.

##### 11.1.2.1.1 User JSON

The `User` entity is serialized to JSON using Jackson annotations:
- `@JsonIgnoreProperties`: Ignores unmapped properties
- `@JsonProperty`: Specifies the property name
- `@JsonFormat`: Specifies the date format

##### 11.1.2.1.2 Contact JSON

The `Contact` entity is serialized to JSON using Jackson annotations:
- `@JsonIgnoreProperties`: Ignores unmapped properties
- `@JsonProperty`: Specifies the property name
- `@JsonFormat`: Specifies the date format

##### 11.1.2.1.3 SearchCriteria JSON

The `SearchCriteria` entity is serialized to JSON using Jackson annotations:
- `@JsonIgnoreProperties`: Ignores unmapped properties
- `@JsonProperty`: Specifies the property name

##### 11.1.2.1.4 Profile JSON

The `Profile` entity is serialized to JSON using Jackson annotations:
- `@JsonIgnoreProperties`: Ignores unmapped properties
- `@JsonProperty`: Specifies the property name

##### 11.1.2.1.5 Settings JSON

The `Settings` entity is serialized to JSON using Jackson annotations:
- `@JsonIgnoreProperties`: Ignores unmapped properties
- `@JsonProperty`: Specifies the property name

#### 11.1.2.2 Form Data

The application uses form data for certain operations:
- User registration
- Contact creation
- Profile update
- Password reset

#### 11.1.2.3 File Upload

The application supports file upload for certain operations:
- Contact image upload
- Profile image upload

## 11.2 Endpoint Documentation

The following sections describe the implementation of different endpoints:

### 11.2.1 User Endpoints

The application includes the following user-related endpoints:
- `/user/register`: User registration
- `/user/login`: User login
- `/user/profile`: User profile management
- `/user/change-password`: Password change
- `/user/reset-password`: Password reset

### 11.2.2 Contact Endpoints

The application includes the following contact-related endpoints:
- `/contacts`: List all contacts
- `/contacts/{id}`: View contact details
- `/contacts/add`: Add a new contact
- `/contacts/{id}`: Update an existing contact
- `/contacts/{id}`: Delete a contact
- `/contacts/favorite/{id}`: Toggle favorite status

### 11.2.3 Search Endpoints

The application includes the following search-related endpoints:
- `/search`: Search for contacts
- `/search/suggestions`: Get search suggestions

### 11.2.4 Profile Endpoints

The application includes the following profile-related endpoints:
- `/profile`: View profile information
- `/profile/update`: Update profile details

### 11.2.5 Settings Endpoints

The application includes the following settings-related endpoints:
- `/settings`: View settings
- `/settings/update`: Update settings

## 11.3 API Usage Examples

The following sections provide examples of how to use the ContactManager API.

### 11.3.1 User API

The following sections describe how to use the user-related API:
- Registering a new user
- Logging in
- Managing user profile
- Changing password
- Resetting password

### 11.3.2 Contact API

The following sections describe how to use the contact-related API:
- Adding a new contact
- Viewing contact details
- Updating an existing contact
- Deleting a contact
- Marking a contact as a favorite

### 11.3.3 Search API

The following sections describe how to use the search-related API:
- Searching for contacts
- Getting search suggestions

### 11.3.4 Profile API

The following sections describe how to use the profile-related API:
- Viewing profile information
- Updating profile details

### 11.3.5 Settings API

The following sections describe how to use the settings-related API:
- Viewing settings
- Updating settings

---

# Chapter 12: Security Implementation

## 12.1 Security Architecture

The ContactManager application is implemented using Spring Security, a popular security framework for Java-based web applications. The following sections describe the implementation of different security features.

### 12.1.1 Authentication

The application uses form-based authentication and OAuth 2.0 for user authentication:
- Form-based login: Traditional username/password authentication
- OAuth 2.0 login: Single sign-on via Google accounts

### 12.1.2 Authorization

The application uses role-based access control to define different levels of access:
- User role: Access to user dashboard, contact management, profile management, and settings
- Admin role: Full access to all features

### 12.1.3 Session Management

The application uses session management to maintain user sessions:
- Session timeout: 30 minutes
- Session invalidation on logout
- CSRF protection for all state-changing operations

### 12.1.4 Password Encryption

The application uses BCrypt for password encryption:
- Password is stored as a BCrypt-hashed value
- Password reset functionality is implemented using a secure token

### 12.1.5 OAuth Integration

The application integrates with Google's OAuth 2.0 authentication system:
- User registration and login with Google accounts
- Link existing accounts with Google credentials

## 12.2 Authentication Mechanisms

The following sections describe the implementation of different authentication mechanisms.

### 12.2.1 Form-Based Authentication

The application uses form-based authentication to authenticate users:
- Login form: `/login`
- Login processing URL: `/login`
- Default success URL: `/user/index`
- Failure URL: `/login?error=true`
- CSRF protection: Included in form submissions

### 12.2.2 OAuth 2.0 Authentication

The application uses OAuth 2.0 for user authentication:
- Login page: `/login`
- User info endpoint: `/userinfo`
- Success handler: Custom OAuth2AuthenticationSuccessHandler
- Authentication provider: Custom OAuth2UserService

### 12.2.3 CSRF Protection

The application uses CSRF tokens for all state-changing operations:
- CSRF token is included in all forms
- CSRF validation for POST, PUT, DELETE requests
- Custom CSRF handling for AJAX requests

### 12.2.4 Session Management

The application uses session management to maintain user sessions:
- Session timeout: 30 minutes
- Session invalidation on logout
- CSRF protection for all state-changing operations

### 12.2.5 Password Encryption

The application uses BCrypt for password encryption:
- Password is stored as a BCrypt-hashed value
- Password reset functionality is implemented using a secure token

### 12.2.6 OAuth Integration

The application integrates with Google's OAuth 2.0 authentication system:
- User registration and login with Google accounts
- Link existing accounts with Google credentials

## 12.3 Authorization Rules

The following sections describe the implementation of different authorization rules.

### 12.3.1 Role-Based Access Control

The application uses role-based access control to define different levels of access:
- User role: Access to user dashboard, contact management, profile management, and settings
- Admin role: Full access to all features

### 12.3.2 Method-Level Security

The application uses method-level security annotations to enforce access control at the service layer:
- `@PreAuthorize`: Defines access rules for different methods
- `@PostAuthorize`: Defines access rules for methods returning a value
- `@PostFilter`: Defines access rules for methods returning a collection
- `@PostUpdate`: Defines access rules for methods modifying an entity

### 12.3.3 Custom Security Expressions

The application defines custom security expressions to enforce ownership-based access control:
- `@SecurityService.isOwner`: Checks if the current user owns a specific entity
- `@SecurityService.isContactOwner`: Checks if the current user owns a specific contact

### 12.3.4 Controller-Level Security

The application uses security annotations to enforce access control at the controller level:
- `@PreAuthorize`: Defines access rules for different methods
- `@PostAuthorize`: Defines access rules for methods returning a value
- `@PostFilter`: Defines access rules for methods returning a collection
- `@PostUpdate`: Defines access rules for methods modifying an entity

## 12.4 Data Encryption

The application uses BCrypt for password encryption:
- Password is stored as a BCrypt-hashed value
- Password reset functionality is implemented using a secure token

## 12.5 OAuth Integration

The application integrates with Google's OAuth 2.0 authentication system:
- User registration and login with Google accounts
- Link existing accounts with Google credentials

---

# Chapter 13: Testing Strategy

## 13.1 Testing Approach

The ContactManager application is implemented using Test-Driven Development (TDD) principles. The following sections describe the implementation of different tests.

### 13.1.1 Unit Tests

The application includes unit tests for different components:
- User-related operations
- Contact-related operations
- Search-related operations
- Profile-related operations
- Settings-related operations

### 13.1.2 Integration Tests

The application includes integration tests for different components:
- User-related operations
- Contact-related operations
- Search-related operations
- Profile-related operations
- Settings-related operations

### 13.1.3 UI Automation Tests

The application includes UI automation tests for different pages:
- Login page
- Registration page
- Contact list page
- Contact details page
- Profile page
- Settings page

## 13.2 Unit Testing

The following sections describe the implementation of different unit tests.

### 13.2.1 UserService

The `UserService` class is tested using JUnit and Mockito:
- `registerUser()`: Tests user registration
- `checkEmailExists()`: Tests email uniqueness
- `findUserByEmail()`: Tests user retrieval by email
- `updateProfile()`: Tests profile update
- `saveUser()`: Tests user saving

### 13.2.2 ContactService

The `ContactService` class is tested using JUnit and Mockito:
- `saveContact()`: Tests contact saving
- `findContactsByUser()`: Tests contact retrieval
- `findContactById()`: Tests contact retrieval by ID
- `deleteContact()`: Tests contact deletion
- `findFavoriteContacts()`: Tests favorite contact retrieval

### 13.2.3 SearchService

The `SearchService` class is tested using JUnit and Mockito:
- `searchContacts()`: Tests search functionality
- `buildSearchSpecification()`: Tests search specification building

### 13.2.4 ProfileService

The `ProfileService` class is tested using JUnit and Mockito:
- `getProfile()`: Tests profile retrieval
- `updateProfile()`: Tests profile update

### 13.2.5 SettingsService

The `SettingsService` class is tested using JUnit and Mockito:
- `getSettings()`: Tests settings retrieval
- `updateSettings()`: Tests settings update

## 13.3 Integration Testing

The following sections describe the implementation of different integration tests.

### 13.3.1 User-Related Operations

The application is tested for user-related operations:
- User registration
- User login
- User profile management
- Password change
- Password reset

### 13.3.2 Contact-Related Operations

The application is tested for contact-related operations:
- Adding a new contact
- Viewing contact details
- Updating an existing contact
- Deleting a contact
- Marking a contact as a favorite

### 13.3.3 Search-Related Operations

The application is tested for search-related operations:
- Searching for contacts
- Getting search suggestions

### 13.3.4 Profile-Related Operations

The application is tested for profile-related operations:
- Viewing profile information
- Updating profile details

### 13.3.5 Settings-Related Operations

The application is tested for settings-related operations:
- Viewing settings
- Updating settings

## 13.4 UI Automation Testing

The following sections describe the implementation of different UI automation tests.

### 13.4.1 Login Page

The application is tested for login functionality:
- Valid login
- Invalid login
- Remember me functionality

### 13.4.2 Registration Page

The application is tested for registration functionality:
- Valid registration
- Invalid registration

### 13.4.3 Contact List Page

The application is tested for contact list functionality:
- Contact list display
- Pagination
- Contact details display

### 13.4.4 Contact Details Page

The application is tested for contact details functionality:
- Contact details display
- Edit contact form

### 13.4.5 Profile Page

The application is tested for profile functionality:
- Profile display
- Edit profile form

### 13.4.6 Settings Page

The application is tested for settings functionality:
- Settings display
- Update settings form

## 13.5 Security Testing

The following sections describe the implementation of different security tests.

### 13.5.1 Authentication

The application is tested for authentication functionality:
- Form-based login
- OAuth 2.0 login
- CSRF protection
- Session management

### 13.5.2 Authorization

The application is tested for authorization functionality:
- Role-based access control
- Method-level security

### 13.5.3 Data Encryption

The application is tested for data encryption functionality:
- Password encryption
- Password reset functionality

### 13.5.4 OAuth Integration

The application is tested for OAuth integration functionality:
- User registration and login with Google accounts
- Link existing accounts with Google credentials

---

# Chapter 14: Deployment Guide

## 14.1 Environment Setup

The ContactManager application is designed to run in different environments:
- Local development environment
- Testing environment
- Production environment

### 14.1.1 Local Development Environment

The local development environment is set up using:
- H2 in-memory database for rapid iteration
- Spring Boot development tools
- Maven dependency management

### 14.1.2 Testing Environment

The testing environment is set up using:
- Test Oracle instance for integration testing
- Spring profiles for different environments

### 14.1.3 Production Environment

The production environment is set up using:
- Full Oracle database implementation
- High-availability configuration
- Monitoring and logging

## 14.2 Deployment Process

The following sections describe the deployment process for different environments.

### 14.2.1 Local Development Environment

The local development environment is set up using:
- H2 in-memory database for rapid iteration
- Spring Boot development tools
- Maven dependency management

### 14.2.2 Testing Environment

The testing environment is set up using:
- Test Oracle instance for integration testing
- Spring profiles for different environments

### 14.2.3 Production Environment

The production environment is set up using:
- Full Oracle database implementation
- High-availability configuration
- Monitoring and logging

## 14.3 Docker Configuration

The application is containerized using Docker:
- Docker image for the application
- Docker Compose for local development environment setup
- Kubernetes configuration for production environment setup

## 14.4 Production Considerations

The following sections describe considerations for running the application in production.

### 14.4.1 High-Availability Configuration

The application is designed to be highly available:
- Load balancing configuration
- Database replication
- Failover mechanisms

### 14.4.2 Monitoring and Logging

The application includes monitoring and logging features:
- Prometheus for metrics collection
- ELK stack for centralized logging
- Grafana for dashboard visualization

### 14.4.3 Data Encryption

The application uses encryption for sensitive data:
- Database encryption
- File encryption

---

# Chapter 15: Performance Analysis

## 15.1 Performance Metrics

The following sections describe the performance metrics of the ContactManager application.

### 15.1.1 Response Time

The application is designed to have a fast response time:
- Average response time: 200ms
- 95th percentile response time: 500ms

### 15.1.2 Throughput

The application is designed to handle a high number of requests:
- Average throughput: 100 requests per second
- Peak throughput: 200 requests per second

### 15.1.3 Memory Usage

The application is designed to use a moderate amount of memory:
- Average memory usage: 100MB
- Peak memory usage: 200MB

### 15.1.4 Database Load

The application is designed to have a low database load:
- Average database load: 500 queries per second
- Peak database load: 1000 queries per second

## 15.2 Bottleneck Identification

The following sections describe how to identify bottlenecks in the ContactManager application.

### 15.2.1 Database Queries

The application is designed to optimize database queries:
- Indexing strategies
- Query caching
- Lazy loading

### 15.2.2 Caching Strategy

The application uses caching to reduce database load:
- Query caching
- Object caching

### 15.2.3 Optimization Recommendations

The following sections provide recommendations for optimizing the ContactManager application.

#### 15.2.3.1 Database Query Optimization

The application is designed to optimize database queries:
- Indexing strategies
- Query caching
- Lazy loading

#### 15.2.3.2 Caching Strategy

The application uses caching to reduce database load:
- Query caching
- Object caching

---

# Chapter 16: Future Enhancements

## 16.1 Feature Roadmap

The following sections describe the planned features for future enhancements.
