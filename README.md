# Engagement Portal Server

This project is a **backend application** built with Spring Boot designed to facilitate collaboration, feedback exchange, and interaction between employees or customers. It can be used as an internal platform (e.g., Employee Engagement Portal) or an external one (e.g., Customer Support Portal).

## Features

- User authentication and role-based access control (e.g., admin, user).
- Create, read, update, and delete (CRUD) functionality for posts and comments.
- Interaction and collaboration through posts and comments.
- Integration with PostgreSQL for data persistence.

## Prerequisites

To run this project, ensure you have the following installed:

- **Java 17** or higher
- **Maven** (or use Maven Wrapper included in the project)
- **PostgreSQL**

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-repository/engagement-portal-server.git
cd engagement-portal-server
```

### 2. Configure the Database
1. Create a PostgreSQL database:
   ```sql
   CREATE DATABASE engagement_portal;
   ```

2. Update the `application.properties` file in `src/main/resources`:
   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/engagement_portal
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   spring.datasource.driver-class-name=org.postgresql.Driver

   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
   ```

### 3. Build and Run the Application
#### Using Maven
```bash
mvn clean install
mvn spring-boot:run
```

#### Using Maven Wrapper
```bash
./mvnw clean install
./mvnw spring-boot:run
```

The application will start on [http://localhost:8080](http://localhost:8080).

### 4. API Endpoints

#### Authentication
- `POST /api/users/register`: Register a new user.
- `POST /api/users/login`: Authenticate and retrieve a token.

#### Posts
- `GET /api/posts`: Retrieve all posts.
- `POST /api/posts`: Create a new post.

#### Comments
- `POST /api/comments`: Add a comment to a post.

### 5. Running Tests
To run the tests:
```bash
mvn test
```

### 6. Docker Setup (Optional)
If you want to use Docker to run PostgreSQL:
```bash
docker run --name postgres -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=your_password -e POSTGRES_DB=engagement_portal -p 5432:5432 -d postgres
```

Update the `spring.datasource.url` in `application.properties` to:
```properties
spring.datasource.url=jdbc:postgresql://host.docker.internal:5432/engagement_portal
```

## Project Structure

```plaintext
src/main/java/com/project/engagementportal/
├── config/        # Configuration classes (e.g., security)
├── controller/    # REST controllers
├── dto/           # Data transfer objects
├── entity/        # JPA entities
├── exception/     # Custom exception handling
├── repository/    # JPA repositories
├── service/       # Business logic
└── util/          # Utility classes
```

## Technologies Used

- **Spring Boot 3.4.1**
- **PostgreSQL**
- **Spring Security**
- **Hibernate (JPA)**
- **Lombok**
- **Maven**

## License

This project is licensed under the [MIT License](LICENSE).

## Contributing

Contributions are welcome! Please fork the repository and create a pull request.

## Contact

For any questions, feel free to reach out:

- **Email**: mateusviniciusdasilva@outlook.com
- **GitHub**: [Suetam94](https://github.com/Suetam94)
