
# Task Management API

A Node.js RESTful API for managing tasks, built using Express, MongoDB, and JWT authentication. Users can register, log in, and perform CRUD operations on tasks.

---

## Features

* User registration and login with JWT authentication
* Create, read, update, and delete personal tasks
* Secure access: tasks are user-specific
* Persistent storage with MongoDB
* Tested and validated using Postman

---

## Tech Stack

* **Backend:** Node.js, Express
* **Database:** MongoDB with Mongoose
* **Authentication:** JSON Web Tokens (JWT), bcrypt for password hashing
* **Dependencies:**

  * `express`
  * `mongoose`
  * `jsonwebtoken`
  * `bcryptjs`
  * `cors`
  * `dotenv`

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/task-management-api.git
cd task-management-api
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Environment Configuration

Create a `.env` file in the root directory and add:

```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
PORT=3000
```

> Example local MongoDB URI:
> `mongodb://localhost:27017/task-manager`

### 4. Run the Server

```bash
npm start
```

The API will be accessible at: `http://localhost:3000`

---

## API Endpoints

### Authentication

| Method | Endpoint        | Description         | Auth Required |
| ------ | --------------- | ------------------- | ------------- |
| POST   | `/api/register` | Register a new user | ❌             |
| POST   | `/api/login`    | Log in user         | ❌             |

### Tasks

| Method | Endpoint         | Description   | Auth Required |
| ------ | ---------------- | ------------- | ------------- |
| POST   | `/api/tasks`     | Create a task | ✅ (JWT)       |
| GET    | `/api/tasks`     | Get all tasks | ✅ (JWT)       |
| PUT    | `/api/tasks/:id` | Update a task | ✅ (JWT)       |
| DELETE | `/api/tasks/:id` | Delete a task | ✅ (JWT)       |

---

## Testing with Postman

### Setup

1. Create a new collection: **Task Management API**
2. Set an environment variable:
   `base_url = http://localhost:3000`

### Usage

* First, call `POST /api/register` and `POST /api/login` to create a user and retrieve a JWT token.
* For all task endpoints, add a header:
  `Authorization: Bearer {{jwt_token}}`

---

## Screenshots

Below are screenshots of Postman requests:

![register](https://github.com/user-attachments/assets/7283e841-3679-4981-8639-a97abf93ddff)

![login](https://github.com/user-attachments/assets/ee68fb52-73bb-4629-a3b0-e75a7c967a72)

![add task](https://github.com/user-attachments/assets/83e55123-fa7c-416d-a1af-968bbd0303af)

![see all task](https://github.com/user-attachments/assets/331787b0-67bd-455d-8354-418c3010fedb)

![updatee](https://github.com/user-attachments/assets/c7b62edb-b0e0-405b-bd9d-79c6254dc6ad)

![delete](https://github.com/user-attachments/assets/3987139f-d93c-4aa9-ae8e-88ba563a60aa)


License

MIT License

Contact

For questions or contributions, open an issue or contact the repository owner.
