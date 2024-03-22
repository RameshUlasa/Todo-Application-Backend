# Todo Application

This application implements APIs to perform operations on a 'todo' table in an SQLite database. The table has the following schema:

## Todo Table

| Column   | Type    |
| -------- | ------- |
| id       | INTEGER |
| todo     | TEXT    |
| priority | TEXT    |
| status   | TEXT    |

### APIs Overview

1. **List Todos**: GET `/todos/`

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

2. **Get Todo by ID**: GET `/todos/:todoId/`

   - **Description**: Returns a specific todo based on the todo ID

3. **Create Todo**: POST `/todos/`

   - **Request**:
     ```json
     {
       "id": 10,
       "todo": "Finalize event theme",
       "priority": "LOW",
       "status": "TO DO"
     }
     ```
   - **Response**: `Todo Successfully Added`

4. **Update Todo**: PUT `/todos/:todoId/`

   - **Scenario 1**: Update status
     - **Request**: `{"status": "DONE"}`
     - **Response**: `Status Updated`
   - **Scenario 2**: Update priority
     - **Request**: `{"priority": "HIGH"}`
     - **Response**: `Priority Updated`
   - **Scenario 3**: Update todo text
     - **Request**: `{"todo": "Some task"}`
     - **Response**: `Todo Updated`

5. **Delete Todo**: DELETE `/todos/:todoId/`

   - **Description**: Deletes a todo based on the todo ID
   - **Response**: `Todo Deleted`

### Notes

- Replace spaces in URL parameters with `%20`.
- Priority values: `HIGH`, `MEDIUM`, `LOW`
- Status values: `TO DO`, `IN PROGRESS`, `DONE`

### Setup

1. Install dependencies:
