# 🛠️ Task Runner API with Spring Boot + MongoDB

This is a simple Spring Boot REST API that allows users to manage and run shell command tasks. The tasks are stored in MongoDB, and each task records its execution details like output and timestamps.

---

## 📦 Features

- ✅ Create, read, and delete shell command tasks
- ✅ Execute a task and store its output
- ✅ Search tasks by name
- ✅ All data is stored in MongoDB
- ✅ Tested with Postman

---

## 🧪 API Endpoints

### 🔍 Get All Tasks
```
GET http://localhost:8080/tasks
```
**Response:** List of all stored tasks

---

### 🔎 Get Task by ID
```
GET http://localhost:8080/tasks?id={taskId}
```

---

### 🔎 Search Task by Name
```
GET http://localhost:8080/tasks/search?name=List
```

---

### ➕ Create a Task
```
POST http://localhost:8080/tasks
```
**Body:**
```json
{
  "name": "List current directory",
  "owner": "vicky",
  "command": "ls"
}
```

---

### 🗑️ Delete a Task
```
DELETE http://localhost:8080/tasks/{id}
```

---

### ▶️ Execute a Task
```
PUT http://localhost:8080/tasks/{id}/execute
```
**Runs the shell command, stores the output and timestamps.**

---

## 📋 Example Tasks

Here are some sample tasks from our testing:

### Task 1: List Current Directory
```json
{
  "name": "List current directory",
  "owner": "vicky",
  "command": "ls"
}
```

### Task 2: Change Directory (example)
```json
{
  "name": "Change directory",
  "owner": "vicky",
  "command": "cd"
}
```

### Task 3: Directory Listing with Output
Executed via Postman:
```
PUT /tasks/{id}/execute
```
**Response:**
```json
{
  "startTime": "...",
  "endTime": "...",
  "output": "Directory listing result here..."
}
```

> ✅ Outputs and executions are stored under the `taskExecutions` field in the task document.

---

## 🏃‍♂️ How to Run

1. Clone the repo
2. Make sure MongoDB is running (default port: `27017`)
3. Run the Spring Boot app:
```
mvn spring-boot:run
```
4. Test using Postman: `http://localhost:8080`

---

## 🧼 Command Validation

To prevent abuse, only safe commands are allowed. The app blocks potentially harmful commands like `rm`, `reboot`, `shutdown`, `kill`, etc.

---

## 💾 Tech Stack

- Java
- Spring Boot
- MongoDB
- Postman (for testing)

---

## 📸 Screenshots

| Create Task | Execute Task | Get Tasks |
|-------------|--------------|-----------|
| ![Task Post](2.JPG) | ![Task Execution](3.JPG) | ![All Tasks](Capture.JPG) |

---

## 📬 Author

Developed by Vignesh & team for learning REST API + Shell Execution + MongoDB integration.