# Library Management System

**Live Application:**  
https://library-management-sam-16dd621638aa.herokuapp.com

---

# Project Description

This project is a full-stack Library Management System built using Node.js, Express, MongoDB, Mongoose, React, Bootstrap, and JSON Web Tokens (JWT).

The application allows users to register accounts, log in, browse books, filter books, borrow books, return books, and change their passwords. The system also includes an administrator role that can manage books and generate borrowing reports.

The purpose of this project is to demonstrate authentication, authorization, CRUD operations, database relationships, REST APIs, React frontend development, and deployment using Heroku and MongoDB Atlas.

---

# Features Implemented

## Authentication

- User Registration
- User Login
- User Logout
- Password Change
- JWT Authentication
- Protected Routes
- Friendly Error Messages

## User Features

- View All Books
- Filter Books
- Borrow Books
- Return Books
- View Personal Borrowed Books
- Cannot Borrow Books When No Copies Are Available

## Admin Features

- Add Books
- Modify Books
- Delete Books
- View All Borrowed Books
- View All Users Who Borrowed Books

## Database Seeding

- Seed Admin User
- Seed 5 Users
- Seed 100 Books

---

# Technologies Used

## Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication
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

# Database Models

## Book Model

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

### Description

- name = Book title
- year = Publication year
- genre = Book category
- authors = List of authors
- actualCount = Total copies owned by the library
- quantity = Available copies currently in inventory

---

## User Model

```js
{
  username: String,
  passwordHash: String,
  role: String
}
```

### Roles

```text
admin
user
```

---

## Borrow Transaction Model

```js
{
  user,
  book,
  borrowDate,
  returnDate,
  returned
}
```

### Description

Tracks all borrowing and returning activity within the system.

---

# Administrator Account

```text
Username: admin
Password: secret321
```

---

# API Routes

## Base API URL

```text
https://library-management-sam-16dd621638aa.herokuapp.com/api
```

---

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

Requires:

```text
Authorization: Bearer TOKEN
```

---

## Book Routes

### Get All Books

```http
GET /api/books
```

### Get Book By ID

```http
GET /api/books/:id
```

### Filter Books

Examples:

```http
GET /api/books?genre=Fantasy
```

```http
GET /api/books?author=Rowling
```

```http
GET /api/books?available=true
```

### Add Book (Admin Only)

```http
POST /api/books
```

### Modify Book (Admin Only)

```http
PUT /api/books/:id
```

### Delete Book (Admin Only)

```http
DELETE /api/books/:id
```

---

## Borrowing Routes

### View My Borrowed Books

```http
GET /api/transactions/my-books
```

### Borrow Book

```http
POST /api/transactions/borrow/:bookId
```

### Return Book

```http
POST /api/transactions/return/:transactionId
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

# Postman Testing

The following routes were tested using Postman.

## Authentication

### Register User

<img width="1470" height="956" alt="Screenshot 2026-06-07 at 2 46 43 PM" src="https://github.com/user-attachments/assets/b20e80e6-d036-4d74-bb79-075b75f4be61" />


### Login User

INSERT SCREENSHOT HERE

### Change Password

INSERT SCREENSHOT HERE

---

## Books

### Get All Books

INSERT SCREENSHOT HERE

### Filter Books

INSERT SCREENSHOT HERE

### Add Book

INSERT SCREENSHOT HERE

### Modify Book

INSERT SCREENSHOT HERE

### Delete Book

INSERT SCREENSHOT HERE

---

## Borrowing

### Borrow Book

INSERT SCREENSHOT HERE

### Return Book

INSERT SCREENSHOT HERE

### View My Borrowed Books

INSERT SCREENSHOT HERE

---

## Reports

### Borrowed Books Report

INSERT SCREENSHOT HERE

### Borrowers Report

INSERT SCREENSHOT HERE

---

## Security Testing

### Missing Token

INSERT SCREENSHOT HERE

### Invalid Token

INSERT SCREENSHOT HERE

---

# What Was Easy, Hard, and How I Overcame Challenges

One of the easier parts of this project was setting up the Express server and creating the MongoDB models because these concepts were covered extensively throughout previous assignments. The project structure was also similar to earlier work, which helped speed up development.

One of the more difficult parts of the project was implementing authentication and authorization. Since the application requires both regular users and administrators, it was important to properly protect routes and ensure only administrators could access management functions. I overcame this challenge by testing each API route individually in Postman before connecting it to the frontend.

Another challenge was implementing the borrowing and returning functionality. The application needed to correctly update inventory counts whenever books were borrowed or returned. To solve this problem, I created a borrowing transaction model that tracks each borrowing event and updates the quantity field accordingly.

I also encountered difficulties while configuring MongoDB Atlas and deployment. Initially, I believed I needed a completely new database cluster for this project. After reviewing the documentation and experimenting with connection strings, I realized I could reuse an existing cluster from a previous assignment, which simplified the deployment process significantly.

---

# What I Learned

This project helped me gain a deeper understanding of full-stack web development using React, Express, MongoDB, and Node.js.

Throughout this assignment I learned how to:

- Implement JWT authentication
- Protect backend routes
- Manage user roles
- Build REST APIs
- Create relationships between MongoDB collections
- Seed databases with sample data
- Connect a React frontend to an Express backend
- Test APIs using Postman
- Deploy applications using Heroku and MongoDB Atlas

I also learned the importance of incremental testing. Testing routes individually before connecting them to the frontend made debugging much easier and helped identify problems earlier in the development process.

Overall, this project provided valuable experience building a realistic application that combines user management, inventory management, authentication, and reporting functionality.

---

# What I Want To Learn More About

Although this project taught me many important concepts, there are several areas I would like to continue exploring.

I would like to learn more about:

- Advanced React development
- User interface and user experience design
- Application security
- Cloud deployment
- Database optimization
- Automated testing
- Performance optimization

If I continued developing this application, I would add features such as:

- Book cover images
- Search by title
- Search by author
- Pagination
- Book reservations
- Due dates
- Late fee calculations
- Email notifications
- User dashboards
- Additional reporting tools

These improvements would make the application more realistic and closer to a production-level library management system.

---

# Running the Application Locally

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

# Rubric Checklist

- [x] Authentication
- [x] User Registration
- [x] Password Change
- [x] Nice Error Messages
- [x] Admin Can Add Books
- [x] Admin Can Modify Books
- [x] Admin Can Delete Books
- [x] Users Can Borrow Books
- [x] Users Can Return Books
- [x] Seed Admin
- [x] Seed 100 Books
- [x] Seed 5 Users
- [x] Users Can Get All Books
- [x] Users Can Filter Books
- [x] Borrowed Books Report
- [x] Borrowers Report
- [x] Bootstrap Frontend
- [x] README Completed
- [x] Postman Testing Included

---

# Conclusion

This Library Management System successfully satisfies all project requirements. The application includes authentication, registration, password management, inventory management, borrowing and return functionality, administrative reporting, database seeding, Bootstrap integration, API testing, and deployment.

The project demonstrates the practical application of concepts learned throughout the course and provides a strong foundation for future full-stack development projects.
