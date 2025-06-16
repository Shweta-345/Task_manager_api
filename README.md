Task Management API
A Node.js RESTful API for managing tasks, built with Express, MongoDB, and JWT authentication. Users can register, log in, and perform CRUD operations on tasks.
Features

User registration and login with JWT authentication
Create, read, update, and delete tasks
Secure task access based on user ownership
MongoDB for persistent storage
Tested with Postman for API validation

Tech Stack

Backend: Node.js, Express
Database: MongoDB (Mongoose)
Authentication: JSON Web Tokens (JWT), bcrypt for password hashing
Dependencies: express, mongoose, jsonwebtoken, bcryptjs, cors, dotenv

Installation

Clone or Download the Repository:

Download the ZIP from GitHub or clone:git clone https://github.com/your-username/task-management-api.git




Install Dependencies:

Navigate to the project folder:cd task-management-api
npm install




Set Up Environment Variables:

Create a .env file in the root directory with:MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
PORT=3000


Example MONGO_URI for local MongoDB: mongodb://localhost:27017/task-manager.


Run the Server:
npm start


The API runs at http://localhost:3000.



API Endpoints



Method
Endpoint
Description
Authentication



POST
/api/register
Register a new user
None


POST
/api/login
Log in and get JWT token
None


POST
/api/tasks
Create a task
JWT


GET
/api/tasks
List user’s tasks
JWT


PUT
/api/tasks/:id
Update a task
JWT


DELETE
/api/tasks/:id
Delete a task
JWT


Example Requests

Register User:
POST /api/register
{
  "email": "sampleuser@example.com",
  "password": "samplepass123",
  "name": "Sample User"
}
![register](https://github.com/user-attachments/assets/7283e841-3679-4981-8639-a97abf93ddff)

Response:
{ "message": "User registered successfully" }

Login:
![login](https://github.com/user-attachments/assets/ee68fb52-73bb-4629-a3b0-e75a7c967a72)

![add task](https://github.com/user-attachments/assets/83e55123-fa7c-416d-a1af-968bbd0303af)

![see all task](https://github.com/user-attachments/assets/331787b0-67bd-455d-8354-418c3010fedb)



Update Task:
PUT /api/tasks/68505471750ffcd1f52f26f8
Headers: { "Authorization": "Bearer <jwt_token>" }
{
  "title": "Updated Test Task",
  "completed": true
}

Response:
{
  "message": "Task updated successfully",
  "task": {
    "_id": "68505471750ffcd1f52f26f8",
    "title": "Updated Test Task",
    "completed": true,
    ...
  }
}
![updatee](https://github.com/user-attachments/assets/c7b62edb-b0e0-405b-bd9d-79c6254dc6ad)
![delete](https://github.com/user-attachments/assets/3987139f-d93c-4aa9-ae8e-88ba563a60aa)




Testing with Postman

Set Up Postman:

Create a collection named Task Management API.
Set variable base_url=http://localhost:3000.


Test Endpoints:

Import the Postman collection (if provided in the repository).
Run POST /api/register and POST /api/login to get a JWT.
Use the JWT in headers (Authorization: Bearer {{jwt_token}}) for task endpoints.


Screenshots:

Below are screenshots of Postman requests:

User Registration:
Update Task:


Project Structure
task-management-api/
├── controllers/
│   └── taskController.js
├── middleware/
│   └── auth.js
├── models/
│   ├── task.js
│   └── user.js
├── routes/
│   ├── auth.js
│   └── tasks.js
├── screenshots/
│   ├── register-postman.png
│   ├── update-task.png
├── .gitignore
├── README.md
├── package.json
├── server.js

License
MIT License
Contact
For questions or contributions, open an issue or contact the repository owner.
