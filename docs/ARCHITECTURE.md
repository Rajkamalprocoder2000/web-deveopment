# SkillSpring Platform Architecture

## System Architecture
The SkillSpring platform follows a microservices architecture, allowing for scalability, flexibility, and independent deployment of various components.

### Key Components:
- **Frontend**: A React-based web application that communicates with the backend through RESTful APIs.
- **Backend**: A set of microservices built using Node.js and Express.js that handle business logic and communications with databases.
- **Database**: MongoDB is used for data storage, with separate databases for user data, course content, and analytics.
- **Messaging Queue**: RabbitMQ facilitates communication between microservices, handling asynchronous tasks like notifications and data processing.

## Folder Structure
```
SkillSpring/
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
├── backend/
│   ├── services/
│   ├── config/
│   └── package.json
├── docker-compose.yml
└── README.md
```

## Component Descriptions
1. **Frontend**: Contains all UI components, styles, and the main application logic.
2. **Backend**: 
   - **Services**: Each service corresponds to a specific business function such as user management, course management, etc.
   - **Config**: Configuration files for environment variables and service settings.
3. **docker-compose.yml**: Used to manage and configure multi-container Docker applications for local development.
4. **README.md**: Overview of the project, installation instructions, and usage guidelines.
