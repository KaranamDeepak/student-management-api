# Student Management REST API

A RESTful API built with Spring Boot and MySQL to manage student records.

## 🛠️ Tech Stack
- Java 21
- Spring Boot 3.5
- Spring Data JPA
- MySQL 8.0
- Maven

## 🚀 Features
- Add a new student
- Get all students
- Get student by ID
- Update student details
- Delete a student

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /students | Get all students |
| GET | /students/{id} | Get student by ID |
| POST | /students | Add new student |
| PUT | /students/{id} | Update student |
| DELETE | /students/{id} | Delete student |

## 📦 Sample Request

POST /students
```json
{
  "name": "Deepak",
  "email": "deepak@gmail.com",
  "branch": "CSE",
  "year": 3
}
```

## ⚙️ How to Run
1. Clone the repository
2. Create MySQL database: `CREATE DATABASE studentdb;`
3. Update `application.properties` with your MySQL password
4. Run: `./mvnw spring-boot:run`
5. API runs on `http://localhost:8080`

## 👨‍💻 Author
Karanam Deepak Sharath Chandra  
[LinkedIn](#) | [GitHub](https://github.com/KaranamDeepak)
