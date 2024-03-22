# Todo Application

This project implements APIs to perform CRUD operations on a 'todo' table in an SQLite database. The table has the following schema:

## Todo Table

| Column   | Type    |
| -------- | ------- |
| id       | INTEGER |
| todo     | TEXT    |
| priority | TEXT    |
| status   | TEXT    |

### API Endpoints

The project provides the following API endpoints for managing todos:

### 1. List Todos

- **Path:** `/todos/`
- **Method:** `GET`

   - **Scenario 1**: Get todos by status
     - **Sample API**: `/todos/?status=TO%20DO`
     - **Description**: Returns a list of todos with status 'TO DO'
   - **Scenario 2**: Get todos by priority
     - **Sample API**: `/todos/?priority=HIGH`
     - **Description**: Returns a list of todos with priority 'HIGH'
   - **Scenario 3**: Get todos by priority and status
     - **Sample API**: `/todos/?priority=HIGH&status=IN%20PROGRESS`
     - **Description**: Returns todos with priority 'HIGH' and status 'IN PROGRESS'
   - **Scenario 4**: Search todos
     - **Sample API**: `/todos/?search_q=Play`
     - **Description**: Returns todos containing 'Play' in todo text

### 2. Get Todo by ID

- **Path:** `/todos/:todoId/`
- **Method:** `GET`
- **Description**: Returns a specific todo based on the todo ID

### 3. Create Todo

- **Path:** `/todos/`
- **Method:** `POST`
- **Description**: Creates a new todo in the todo table

### 4. Update Todo

- **Path:** `/todos/:todoId/`
- **Method:** `PUT`
- **Description**: Updates the details of a specific todo based on the todo ID

### 5. Delete Todo

- **Path:** `/todos/:todoId/`
- **Method:** `DELETE`
- **Description**: Deletes a todo from the todo table based on the todo ID

### API Usage

- Replace spaces in URL parameters with `%20`.
- Priority values: `HIGH`, `MEDIUM`, `LOW`
- Status values: `TO DO`, `IN PROGRESS`, `DONE`

### Deployment

The project is deployed at [https://todo-application-backend-s1sp.onrender.com/](https://todo-application-backend-s1sp.onrender.com/).

### Getting Started

1. Install dependencies: npm install
2. Getting started: nodemon app.js
