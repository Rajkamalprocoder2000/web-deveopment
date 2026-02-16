# API Documentation

## Authentication

### Login
- **Endpoint:** `/api/auth/login`
- **Method:** POST
- **Request Body:**  
  ```json
  {
      "email": "user@example.com",
      "password": "string"
  }
  ```
- **Responses:**  
  - **200 OK:**  
    ```json
    {
        "token": "JWT_TOKEN",
        "user": { ... }
    }
    ```
  - **401 Unauthorized:** Invalid credentials.

### Register
- **Endpoint:** `/api/auth/register`
- **Method:** POST
- **Request Body:** 
  ```json
  {
      "name": "string",
      "email": "user@example.com",
      "password": "string"
  }
  ```
- **Responses:**  
  - **201 Created:** User registered successfully.


## Courses

### Get All Courses
- **Endpoint:** `/api/courses`
- **Method:** GET
- **Responses:**  
  - **200 OK:** List of courses.

### Get Course By ID
- **Endpoint:** `/api/courses/{id}`
- **Method:** GET
- **Responses:**  
  - **200 OK:** Course details.
  - **404 Not Found:** Course not found.

### Create Course
- **Endpoint:** `/api/courses`
- **Method:** POST
- **Request Body:** 
  ```json
  {
      "title": "string",
      "description": "string",
      "instructor": "string"
  }
  ```
- **Responses:**  
  - **201 Created:** Course created successfully.


## Enrollments

### Enroll in Course
- **Endpoint:** `/api/enroll`
- **Method:** POST
- **Request Body:** 
  ```json
  {
      "courseId": "string",
      "userId": "string"
  }
  ```
- **Responses:**  
  - **201 Created:** Enrollment successful.

### Get User Enrollments
- **Endpoint:** `/api/enrollments/{userId}`
- **Method:** GET
- **Responses:**  
  - **200 OK:** List of enrolled courses.


## Reviews

### Create Review
- **Endpoint:** `/api/reviews`
- **Method:** POST
- **Request Body:** 
  ```json
  {
      "courseId": "string",
      "userId": "string",
      "rating": "number",
      "comment": "string"
  }
  ```
- **Responses:**  
  - **201 Created:** Review created.

### Get Reviews for Course
- **Endpoint:** `/api/reviews/{courseId}`
- **Method:** GET
- **Responses:**  
  - **200 OK:** List of reviews for the course.