## Books Management API
This is a RESTful API for managing books, built with Node.js, Express.js, and MongoDB. The API allows users to view a list of all books and perform CRUD (Create, Read, Update, Delete) operations on books, provided they are logged in.

## Features
  ## View All Books: Get a list of all books.
  Add a New Book: Logged-in users can add a new book.
  Update a Book: Logged-in users can update a book by its ID.
  Delete a Book: Logged-in users can delete a book by its ID.
  Get a Book by ID: Retrieve detailed information of a book by its ID.
## Prerequisites
Node.js and npm installed
MongoDB installed and running locally or a MongoDB Atlas account

## Installation
  ##Clone the repository:
  git clone https://github.com/DakshChawla12/Books-Management-API.git
  cd books-management-api

## Install dependencies: 
  npm install

## Start the server:
  npm run dev

## API Endpoints
  ## Public Routes
  GET /books: Get a list of all books.
  Protected Routes (Require Authentication)
  POST /books: Add a new book.

## Body Parameters:
  title (string, required): Title of the book.
  author (string, required): Author of the book.
  genre (string): Genre of the book.
  publication (number): Year of publication.
  image_url (string): URL of the book cover image.
  ISBN (number, unique): International Standard Book Number.
  description (string): Description of the book.
  GET /books/
  : Get a book by its ID.
  
  PUT /books/
  : Update a book by its ID.
  
  Body Parameters: Same as the POST request.
  DELETE /books/
  : Delete a book by its ID.

## Authentication
The API uses JWT (JSON Web Tokens) for authentication. You need to provide a token in the Authorization header (in the format Bearer <token>) to access protected routes. The token can be obtained by logging in.

## Error Handling
The API returns standard HTTP response codes for errors:

400 Bad Request: Invalid input data.
401 Unauthorized: Authentication failed.
404 Not Found: Resource not found.
500 Internal Server Error: Server error.

## Get All Books
  GET /books
## Add a New Book (Requires Authentication)
  POST /books
  Content-Type: application/json
  Authorization: Bearer <token>
  
  {
    "title": "To Kill a Mockingbird",
    "author": "Harper Lee",
    "genre": "Fiction",
    "publication": 1960,
    "image_url": "http://example.com/image.jpg",
    "ISBN": 1234567890123,
    "description": "A novel about the injustices of the American South."
  }
## Update a Book (Requires Authentication)
  PUT /books/:id
  Content-Type: application/json
  Authorization: Bearer <token>

{
  "title": "To Kill a Mockingbird - Updated Edition",
  "author": "Harper Lee",
  "genre": "Classic Fiction",
  "publication": 1960,
  "image_url": "http://example.com/image-updated.jpg",
  "ISBN": 1234567890123,
  "description": "Updated description for the novel."
}
## Delete a Book (Requires Authentication)
DELETE /books/:id
Authorization: Bearer <token>


