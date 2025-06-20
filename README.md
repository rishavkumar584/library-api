# Library API

A RESTful API for managing a collection of books using **Node.js**, **Express.js**, and **MongoDB**. This project demonstrates how to build custom API endpoints, perform CRUD operations, and integrate a database.

## Features

-  Create a new book entry
-  Retrieve all books
-  Update a book’s information
-  Delete a book
-  Tested with `curl` and shell script
-  `.env` configuration for MongoDB URI

---

## Project Structure

library-api/
│
├── models/
│ └── Book.js # Mongoose schema for books
│
├── routes/
│ └── books.js # Express router with CRUD APIs
│
├── .env.example # Template for environment variables
├── .gitignore # Ignores node_modules and sensitive files
├── package.json # Project metadata and dependencies
├── server.js # Entry point for the Express server
└── test_book_api.sh # Shell script to test the API (optional)


---

## 🔧 Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/rishavkumar584/library-api.git
   cd library-api

2. **Install dependencies**
   npm install

3.**Configure environment variables**
    Create a .env file in the root directory based on .env.example:
     MONGODB_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/<dbname>?retryWrites=true&w=majority
     PORT=3000

4.**Run the server**
    npm start
*The server will run at http://localhost:3000/


**API Endpoints**

| Method | Endpoint     | Description            |
| ------ | ------------ | ---------------------- |
| POST   | `/books`     | Create a new book      |
| GET    | `/books`     | Retrieve all books     |
| PUT    | `/books/:id` | Update a specific book |
| DELETE | `/books/:id` | Delete a specific book |


**Testing the API (via curl)**
# Create a book
curl -X POST http://localhost:3000/books \
-H "Content-Type: application/json" \
-d '{"title":"1984", "author":"George Orwell", "publishedYear":1949, "genre":"Dystopian", "available":true}'

# Get all books
curl http://localhost:3000/books

# Update a book
curl -X PUT http://localhost:3000/books/<BOOK_ID> \
-H "Content-Type: application/json" \
-d '{"available": false}'

# Delete a book
curl -X DELETE http://localhost:3000/books/<BOOK_ID>


**Optional**
 If you'd like to test using a bash script:
   chmod +x test_book_api.sh
  ./test_book_api.sh
  
*(Ensure jq is installed for JSON parsing)

# Tech Stack
- Backend: Node.js, Express.js
- Database: MongoDB Atlas
- ODM: Mongoose
- Environment Config: dotenv

Enjoyed making it!!!
