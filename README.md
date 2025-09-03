# Task Manager Backend

## Features

- User sign-up/login (JWT authentication)
- Add, edit, delete tasks (MongoDB Atlas)
- Task list view with status toggle (pending/completed)
- Backend deployed on Render

## API Endpoints

### Auth

- `POST /api/auth/signup`

  - Create a new user
  - Body: `{ "name": "...", "email": "...", "password": "..." }`

- `POST /api/auth/login`
  - Login and get JWT token
  - Body: `{ "email": "...", "password": "..." }`
  - Response: `{ "token": "..." }`

### Tasks (require JWT in `Authorization: Bearer <token>`)

- `POST /api/tasks`

  - Create a task
  - Body: `{ "title": "...", "description": "..." }`

- `GET /api/tasks`

  - Get all tasks for the logged-in user
  - Response: Array of tasks

- `PUT /api/tasks/:id`

  - Update a task
  - Body: `{ "title": "...", "description": "...", "status": "pending|completed" }`

- `DELETE /api/tasks/:id`

  - Delete a task

- `PATCH /api/tasks/:id/toggle`
  - Toggle status (pending/completed)

## Setup

1. Clone the repo:
   ```
   git clone <your-repo-url>
   ```
2. Install dependencies:
   ```
   npm install
   ```
3. Add `.env` file with your MongoDB URI and JWT secret:
   ```
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=yourSecretKey
   ```
4. Start server:
   ```
   node server.js
   ```

## Deployment

- Hosted on Render: [https://assignment-9wv7.onrender.com](https://assignment-9wv7.onrender.com)

## Demo

- [Add your demo video link here]

## Task List View

- Use `GET /api/tasks` to fetch all tasks for the logged-in user.
- Each task includes: `_id`, `title`, `description`, `status`, `user`, `createdAt`.
- Example response:
  ```json
  [
    {
      "_id": "...",
      "title": "First Task",
      "description": "This is my first task",
      "status": "pending",
      "user": "...",
      "createdAt": "..."
    }
  ]
  ```

---

For any questions, contact the repository owner.
