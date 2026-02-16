# Database Schema

## Users Table
- **user_id**: INT (Primary Key)
- **username**: VARCHAR(50) (Unique)
- **password**: VARCHAR(255)
- **email**: VARCHAR(100) (Unique)
- **created_at**: TIMESTAMP
- **updated_at**: TIMESTAMP

## Categories Table
- **category_id**: INT (Primary Key)
- **category_name**: VARCHAR(100) (Unique)
- **created_at**: TIMESTAMP
- **updated_at**: TIMESTAMP

## Courses Table
- **course_id**: INT (Primary Key)
- **title**: VARCHAR(100)
- **description**: TEXT
- **category_id**: INT (Foreign Key)
- **instructor_id**: INT (Foreign Key)
- **created_at**: TIMESTAMP
- **updated_at**: TIMESTAMP

## Enrollments Table
- **enrollment_id**: INT (Primary Key)
- **user_id**: INT (Foreign Key)
- **course_id**: INT (Foreign Key)
- **enrolled_at**: TIMESTAMP

## Reviews Table
- **review_id**: INT (Primary Key)
- **course_id**: INT (Foreign Key)
- **user_id**: INT (Foreign Key)
- **rating**: INT (CHECK rating BETWEEN 1 AND 5)
- **comment**: TEXT
- **created_at**: TIMESTAMP

## Payments Table
- **payment_id**: INT (Primary Key)
- **user_id**: INT (Foreign Key)
- **course_id**: INT (Foreign Key)
- **amount**: DECIMAL(10, 2)
- **payment_date**: TIMESTAMP
- **status**: ENUM('Pending', 'Completed', 'Failed')

---

### Notes
- Foreign keys reference the primary keys of their respective tables.
- Timestamps should default to the current time when a record is created or updated.