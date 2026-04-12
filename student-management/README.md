# Student Management API

A Spring Boot REST API for managing student information. This application provides endpoints to perform CRUD operations on student records with a MySQL database backend.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Features

- ✅ Get all students
- ✅ Get student by ID
- ✅ Create a new student
- ✅ Update student information
- ✅ Delete a student
- ✅ RESTful API design
- ✅ MySQL database integration

## Prerequisites

Before you begin, ensure you have the following installed:

- **Java 17** or higher
- **Maven 3.6+** or use the included Maven wrapper (`mvnw`)
- **MySQL 8.0+** (or MariaDB)
- **Git**

## Technologies Used

- **Spring Boot 3.5.13** - Framework for building REST APIs
- **Spring Data JPA** - Data access layer
- **MySQL Connector** - Database driver
- **Maven** - Build and dependency management
- **Java 17** - Programming language

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/student-management-api.git
   cd student-management-api
   ```

2. **Navigate to the project directory:**
   ```bash
   cd student-management
   ```

## Configuration

1. **Setup MySQL Database:**
   ```sql
   CREATE DATABASE student_management;
   ```

2. **Update database configuration** in `src/main/resources/application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/student_management
   spring.datasource.username=root
   spring.datasource.password=your_password
   spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
   
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
   ```

3. **Update your credentials** as per your MySQL setup.

## Running the Application

### Using Maven Wrapper (Recommended)

```bash
# On Windows
mvnw.cmd spring-boot:run

# On Linux/macOS
./mvnw spring-boot:run
```

### Using Maven (if installed globally)

```bash
mvn spring-boot:run
```

### Using IDE

1. Import the project into your IDE (IntelliJ IDEA, Eclipse, VS Code with extensions)
2. Run the `StudentManagementApplication` class as a Spring Boot application

The application will start on `http://localhost:8080`

## API Endpoints

### Base URL
```
http://localhost:8080/students
```

### Endpoints

#### 1. Get All Students
```
GET /students
```
**Response:** List of all students
```json
[
  {
    "id": 1,
    "name": "John Doe",
    "email": "john@example.com",
    "branch": "Computer Science",
    "year": 3
  }
]
```

#### 2. Get Student by ID
```
GET /students/{id}
```
**Example:** `GET /students/1`

**Response:**
```json
{
  "id": 1,
  "name": "John Doe",
  "email": "john@example.com",
  "branch": "Computer Science",
  "year": 3
}
```

#### 3. Create a New Student
```
POST /students
```
**Request Body:**
```json
{
  "name": "Jane Smith",
  "email": "jane@example.com",
  "branch": "Information Technology",
  "year": 2
}
```

**Response:** Created student object with generated ID

#### 4. Update Student Information
```
PUT /students/{id}
```
**Example:** `PUT /students/1`

**Request Body:**
```json
{
  "name": "John Updated",
  "email": "john.updated@example.com",
  "branch": "Computer Science",
  "year": 4
}
```

**Response:** Updated student object

#### 5. Delete a Student
```
DELETE /students/{id}
```
**Example:** `DELETE /students/1`

**Response:** `"Student deleted successfully!"`

## Project Structure

```
student-management/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/deepak/student_management/
│   │   │       ├── Student.java                 # Student entity
│   │   │       ├── StudentController.java       # REST controller
│   │   │       ├── StudentRepository.java       # Data access layer
│   │   │       └── StudentManagementApplication.java  # Main application class
│   │   └── resources/
│   │       └── application.properties           # Configuration file
│   └── test/
│       └── java/
│           └── com/deepak/student_management/
│               └── StudentManagementApplicationTests.java
├── pom.xml                                      # Maven configuration
├── mvnw & mvnw.cmd                             # Maven wrapper scripts
└── README.md                                    # This file
```

## Student Entity Fields

| Field  | Type    | Description              |
|--------|---------|--------------------------|
| id     | Long    | Unique identifier (Auto-generated) |
| name   | String  | Student's full name      |
| email  | String  | Student's email address  |
| branch | String  | Academic branch/program  |
| year   | Integer | Current academic year    |

## Testing

Run the tests using Maven:
```bash
mvn test
```

## Troubleshooting

### Database Connection Issues
- Ensure MySQL is running
- Verify database credentials in `application.properties`
- Check that the database URL is correct

### Port Already in Use
- The application uses port 8080 by default. If it's already in use, change it in `application.properties`:
  ```properties
  server.port=8081
  ```

### Maven Build Issues
- Clear Maven cache: `mvn clean`
- Rebuild: `mvn clean install`

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

## Author

**Deepak** - Initial work

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

**Note:** This is a sample student management API. For production use, consider adding:
- Input validation and error handling
- Authentication and authorization
- Logging
- Pagination for large datasets
- API documentation (Swagger/SpringDoc)
- Environment-specific configuration
