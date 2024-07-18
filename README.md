# Microservice Project

This project consists of four Maven projects: `question-service`, `quiz-service`, `api-gateway`, and `service-registry`. It is written in Java (version 17) using Spring Boot (version 3.3.1). The database used is PostgreSQL (version 15.2).

## Prerequisites

- Java 17
- Maven
- PostgreSQL 15.2

## Setup Instructions

1. Clone the repository:
    ```bash
    git clone [<repository-url>](https://github.com/atuldas/quizapp-microservice-poc.git)
    cd <repository-directory>
    ```

2. Adjust the datasource properties in `application.properties` file for `question-service` and `quiz-service`:
    ```properties
    spring.datasource.url=jdbc:postgresql://<your-database-url>:<port>/<database-name>
    spring.datasource.username=<your-database-username>
    spring.datasource.password=<your-database-password>
    ```

3. Run the services:

    - Start `service-registry`:
        ```bash
        cd service-registry
        mvn spring-boot:run
        ```

    - Start `question-service`:
        ```bash
        cd question-service
        mvn spring-boot:run
        ```

    - Start `quiz-service`:
        ```bash
        cd quiz-service
        mvn spring-boot:run
        ```

    - Start `api-gateway`:
        ```bash
        cd api-gateway
        mvn spring-boot:run
        ```

## Project Structure

- `question-service`: Handles CRUD operations for questions.
- `quiz-service`: Manages quizzes, including creation, updates, and retrieval.
- `api-gateway`: Serves as the entry point for the microservices, handling routing and forwarding requests to the appropriate services.
- `service-registry`: Manages service discovery, allowing microservices to find and communicate with each other.

## APIs

The APIs for `question-service` and `quiz-service` are self-explanatory and can be found in the respective project directories.

## Database Schema

Ensure your PostgreSQL database is set up with the appropriate schemas and tables as expected by the application. Refer to the entity classes in `question-service` and `quiz-service` for details on the required schema.

## Dependencies

The project relies on the following dependencies (among others):
- Spring Boot
- Spring Cloud
- PostgreSQL Driver

## Contact

For any issues or questions, please contact [atul.das02@gmail.com].
