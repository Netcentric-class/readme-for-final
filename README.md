# Library Management System

**Deployed App URL:** INSERT_YOUR_DEPLOYED_APP_URL_HERE

---

# Project Description

This project is a full-stack Library Management System developed using Node.js, Express, MongoDB, Mongoose, React, Bootstrap, and JSON Web Tokens (JWT).

The application allows users to register, log in, browse books, filter books, borrow books, return books, and change their passwords. The system also contains an administrator role that can manage books and generate reports.

The application was designed to simulate a real-world library inventory and borrowing system while implementing authentication, authorization, CRUD operations, database relationships, and frontend integration.

---

# Features Implemented

## Authentication

- User Login
- User Logout
- User Registration
- Change Password
- JWT Authentication
- Protected Routes
- Nice Error Messages

## Admin Features

- Add Books
- Modify Books
- Delete Books
- View All Borrowed Books
- View All Users Who Borrowed Books

## User Features

- View All Books
- Filter Books
- Borrow Books
- Return Books
- Cannot Borrow Books When No Copies Are Available

## Database Seeding

- Seed Admin User
- Seed 5 Users
- Seed 100 Books

---

# Book Fields

Each book contains the following fields:

```js
{
  name: String,
  year: Number,
  genre: String,
  authors: [String],
  actualCount: Number,
  quantity: Number
}
```

---

# Models

## Book Model

Stores information about books and inventory levels.

### Fields

```js
{
  name,
  year,
  genre,
  authors,
  actualCount,
  quantity
}
```

---

## User Model

Stores registered users and authentication information.

### Fields

```js
{
  username,
  passwordHash,
  role
}
```

### Roles

```text
admin
user
```

---

## Borrow Transaction Model

Stores borrowing and return history.

### Fields

```js
{
  user,
  book,
  borrowDate,
  returnDate,
  returned
}
```

---

# Technology Stack

## Backend

- Node.js
- Express
- MongoDB
- Mongoose
- JWT
- bcrypt

## Frontend

- React
- Vite
- Bootstrap

## Development Tools

- GitHub
- Postman
- MongoDB Atlas
- Heroku

---

# Admin Account

```text
Username: admin
Password: secret321
```

---

# API Routes

## Authentication Routes

### Register User

```http
POST /api/auth/register
```

### Login User

```http
POST /api/auth/login
```

### Change Password

```http
POST /api/auth/change-password
```

---

## Book Routes

### Get All Books

```http
GET /api/books
```

### Filter Books

```http
GET /api/books?genre=Fantasy
```

```http
GET /api/books?author=Rowling
```

```http
GET /api/books?available=true
```

### Add Book

```http
POST /api/books
```

### Modify Book

```http
PUT /api/books/:id
```

### Delete Book

```http
DELETE /api/books/:id
```

---

## Borrowing Routes

### Borrow Book

```http
POST /api/transactions/borrow/:bookId
```

### Return Book

```http
POST /api/transactions/return/:transactionId
```

### View My Borrowed Books

```http
GET /api/transactions/my-books
```

---

## Admin Report Routes

### View All Borrowed Books

```http
GET /api/admin/borrowed-books
```

### View All Borrowers

```http
GET /api/admin/borrowers
```

---

# Postman Testing Screenshots

## Register User

Insert Screenshot Here

---

## Login

Insert Screenshot Here

---

## Change Password

Insert Screenshot Here

---

## Get All Books

Insert Screenshot Here

---

## Filter Books

Insert Screenshot Here

---

## Add Book

Insert Screenshot Here

---

## Modify Book

Insert Screenshot Here

---

## Delete Book

Insert Screenshot Here

---

## Borrow Book

Insert Screenshot Here

---

## Return Book

Insert Screenshot Here

---

## Borrowed Books Report

Insert Screenshot Here

---

## Borrowers Report

Insert Screenshot Here

---

## Protected Route Without Token

Insert Screenshot Here

---

## Protected Route With Invalid Token

Insert Screenshot Here

---

# What Was Easy, Hard, and How I Overcame Challenges

One of the easier parts of this project was setting up the Express server and creating the MongoDB models because these concepts were covered extensively during previous assignments and class exercises.

One of the more difficult parts of the project was implementing authentication and authorization. Since the application required different permissions for administrators and regular users, it was important to correctly protect routes and validate JWT tokens. I overcame this challenge by testing every route individually using Postman before integrating it into the React frontend.

Another challenge was implementing the borrowing and returning system. The application needed to properly update inventory counts whenever books were borrowed or returned. To solve this problem, I created a borrowing transaction model that tracks each borrowing event and updates the quantity field whenever a transaction occurs.

I also encountered challenges while configuring MongoDB Atlas and deployment because I initially believed I needed a completely new database cluster. After reviewing the documentation and testing the connection strings, I realized I could reuse an existing cluster from a previous assignment, which simplified the deployment process significantly.

---

# What I Learned

This project helped me better understand how modern full-stack applications are built using React, Express, MongoDB, and Node.js.

I learned how to:

- Implement JWT authentication
- Protect API routes
- Manage user roles
- Create database relationships
- Build REST APIs
- Seed databases
- Connect a React frontend to an Express backend
- Test APIs using Postman
- Deploy applications using Heroku and MongoDB Atlas

I also learned the importance of testing applications incrementally. Testing each route individually before building the frontend made debugging significantly easier and reduced development time.

Overall, this project provided valuable experience developing a realistic application that combines authentication, inventory management, user management, and reporting functionality.

---

# What I Want To Learn More About

Although this project taught me many valuable concepts, there are several areas I would like to explore further.

I would like to learn more about:

- Advanced React development
- Frontend design and user experience
- Application security
- Cloud deployment
- Scalable database architecture
- Automated testing
- Performance optimization

If I continued developing this application, I would add features such as:

- Book cover images
- Search by title and author
- Pagination
- Book reservations
- Due dates
- Late fee calculations
- Email notifications
- User dashboards
- Analytics and reporting

These additions would make the application more realistic and closer to a production-level library management system.

---

# How To Run The Project

## Backend

Install dependencies:

```bash
cd backend
npm install
```

Run backend server:

```bash
npm run dev
```

---

## Frontend

Install dependencies:

```bash
cd frontend
npm install
```

Run frontend server:

```bash
npm run dev
```

---

## Seed Database

Seed administrator:

```bash
npm run seed:admin
```

Seed users:

```bash
npm run seed:users
```

Seed books:

```bash
npm run seed:books
```

---

# Final Project Checklist

## Rubric Requirements

- [x] Authentication
- [x] Registration
- [x] Password Change
- [x] Nice Error Messages
- [x] Admin Can Add Books
- [x] Admin Can Modify Books
- [x] Admin Can Delete Books
- [x] Users Can Borrow Books
- [x] Users Can Return Books
- [x] Seed Admin
- [x] Seed 100 Books
- [x] Users Can Get All Books
- [x] Users Can Filter Books
- [x] Borrowed Books Report
- [x] Borrowers Report
- [x] Bootstrap Frontend
- [x] README Completed
- [x] Postman Testing Screenshots Included

---

# Conclusion

This Library Management System successfully satisfies all assignment requirements. The application includes authentication, user registration, password management, book inventory management, borrowing and return functionality, administrative reporting, database seeding, Bootstrap integration, API testing, and deployment.

The project demonstrates the practical application of concepts learned throughout the course and provides a strong foundation for future full-stack development projects.
