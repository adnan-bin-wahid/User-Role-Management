User Management & Role Assignment System

A Spring Boot application implementing a User Management System based on Robert C. Martin's Clean Architecture principles. This project provides RESTful APIs to manage users and roles, including creating users/roles, assigning roles to users, and retrieving user details with their assigned roles. It uses an H2 in-memory database and includes unit tests for the service layer.

Features





Create users with name and email.



Create roles with a role name.



Assign roles to users.



Retrieve user details with assigned roles.



Input validation (email format, non-blank fields).



Error handling with meaningful HTTP status codes.



H2 in-memory database with console access.



Unit tests for the application layer using Mockito.


Tech Stack





Framework: Spring Boot 3.x



Database: H2 (in-memory)



ORM: Spring Data JPA



Testing: JUnit 5, Mockito



Build Tool: Maven

Project Structure

src/main/java/com/example/usermanagement/
├── domain/
│   ├── User.java
│   └── Role.java
├── application/
│   ├── UserService.java
│   ├── RoleService.java
│   └── interfaces/
│       ├── UserRepository.java
│       └── RoleRepository.java
├── infrastructure/
│   ├── controller/
│   │   ├── UserController.java
│   │   └── RoleController.java
│   └── persistence/
│       ├── UserJpaEntity.java
│       ├── RoleJpaEntity.java
│       ├── UserJpaRepository.java
│       └── RoleJpaRepository.java
└── config/
    └── BeanConfig.java

Setup Instructions





Clone the Repository:

git clone https://github.com/username/user-management-system.git



Navigate to the Project Directory:

cd user-management-system



Run the Application:

mvn spring-boot:run



Access the H2 Console:





URL: http://localhost:8080/h2-console



JDBC URL: jdbc:h2:mem:testdb



Username: sa



Password: password



Test the APIs:





Use Postman, cURL, or any API client to interact with the endpoints.

API Endpoints







Method



URL



Request Body



Response





POST



/users



{ "name": "John Doe", "email": "john@example.com" }



Created User ID





POST



/roles



{ "roleName": "ADMIN" }



Created Role ID





POST



/users/{userId}/assignrole/{roleId}



(Empty)



Success Message





GET



/users/{id}



-



User Details with Roles

Running Tests

Run unit tests for the service layer:

mvn test

Bonus Features (Optional)





Pagination for /users list API.



Remove role from user API.



Audit fields (createdDate, updatedDate).



DTOs for request/response.



Swagger/OpenAPI documentation.



Integration tests for end-to-end testing.

Development Notes





Follows Clean Architecture with strict separation of concerns.



Domain entities are free of Spring/JPA annotations.



Repository interfaces in the application layer act as ports.



Controllers and JPA repositories are adapters in the infrastructure layer.



Dependencies flow inward, adhering to the Dependency Rule.

Contributing

Submit issues or pull requests for improvements or bug fixes.

License

This project is licensed under the MIT License.
