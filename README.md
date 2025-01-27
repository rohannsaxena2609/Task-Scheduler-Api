# Task-Scheduler-Api
This project implements a lightweight, command-line-based Task Scheduler using C++. It allows users to schedule tasks to run at specific times, list all scheduled tasks, and delete tasks when needed. The system leverages multithreading for task execution, ensuring scheduled tasks run concurrently without blocking the main application.
# Task Scheduler API

A Flask-based Task Scheduler API for scheduling, retrieving, and deleting tasks with a persistent job store.

## Features
- Schedule tasks to run at a specific time.
- List all scheduled tasks.
- Delete tasks by ID.

## Tech Stack
- C++ 
- APScheduler
- SQLite (Persistent job storage)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/rohannsaxena/task-scheduler-api.git
   cd task-scheduler-api
Create a virtual environment and activate it:

bash
Copy
Edit
python3 -m venv venv
source venv/bin/activate  # For Windows: venv\\Scripts\\activate
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Run the application:

bash
Copy
Edit
python run.py
API Endpoints
1. Schedule Task
POST /schedule
Request Body:

json
Copy
Edit
{
  "task_id": "unique_task_id",
  "message": "Task message",
  "time": "YYYY-MM-DD HH:MM:SS"
}
2. Get All Tasks
GET /tasks

3. Delete Task
DELETE /delete/<task_id>

Example Usage
Schedule a task:

bash
Copy
Edit
curl -X POST -H "Content-Type: application/json" -d '{
  "task_id": "task123",
  "message": "Hello World",
  "time": "2025-01-27 15:30:00"
}' http://127.0.0.1:5000/schedule
Retrieve tasks:

bash
Copy
Edit
curl -X GET http://127.0.0.1:5000/tasks
Delete a task:

bash
Copy
Edit
curl -X DELETE http://127.0.0.1:5000/delete/task123

