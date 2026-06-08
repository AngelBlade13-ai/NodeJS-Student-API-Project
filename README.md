# NodeJS Student API Project

A Node.js and Express REST API for managing student records. The API connects to MongoDB, exposes CRUD routes for students, and includes simple authentication routes for registration, login, logout, and protected-route practice.

This was built as a school API project to practice Express routing, controllers, MongoDB models, and REST request testing.

## Features

- Express API server
- MongoDB connection module
- Student model with required fields
- CRUD routes for student records
- Authentication routes for register, login, logout, and protected route practice
- CORS enabled for frontend/API testing
- REST Client request examples in `routes.rest`
- Swagger-related dependencies included for API documentation practice

## Tech Stack

- Node.js
- Express
- MongoDB
- Mongoose
- bcryptjs
- JSON Web Tokens
- CORS
- dotenv
- nodemon
- REST Client request file

## Project Structure

```text
server.js
routes.rest
controllers/
  index.js
  authController.js
db/
  connect.js
middleware/
models/
  Student.js
  User.js
routes/
  index.js
  students.js
  auth.js
```

## Student Data Model

```js
{
  firstName: String,
  lastName: String,
  email: String,
  age: Number,
  currentCollege: String
}
```

All fields are required by the Mongoose schema.

## Environment Variables

Create a `.env` file in the project root. The database connection module should be configured with your MongoDB connection string. Check `db/connect.js` for the exact variable name expected by the current code.

Common setup:

```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
PORT=3000
```

## How To Run

Install dependencies:

```bash
npm install
```

Start the server:

```bash
npm start
```

Open or test against:

```text
http://localhost:3000
```

## Main Routes

```text
GET    /                 Root route
GET    /ttech            Tooele Tech sample route
GET    /students         Get all students
GET    /students/:id     Get one student
POST   /students         Create a student
PUT    /students/:id     Update a student
DELETE /students/:id     Delete a student

GET    /auth/home        Auth home/test route
GET    /auth/protected   Protected route practice
POST   /auth/register    Register user
POST   /auth/login       Log in user
POST   /auth/logout      Log out user
```

## Testing Requests

The `routes.rest` file includes sample requests for the student routes. It can be used with the REST Client extension in VS Code.

Example create request:

```http
POST http://localhost:3000/students
Content-Type: application/json

{
  "firstName": "Phil",
  "lastName": "Reeves",
  "email": "phil@example.com",
  "age": 34,
  "currentCollege": "Tooele Technical College"
}
```

## Notes

- This is an API-only project; it does not include a browser frontend.
- A working MongoDB connection is required before the server starts listening.
- The included auth routes are coursework/practice routes and should be hardened before production use.

## What I Practiced

- Structuring an Express app with routes, controllers, and models
- Connecting Express to MongoDB
- Creating RESTful CRUD endpoints
- Testing endpoints with a `.rest` file
- Building basic authentication route patterns
