Django Book API
Description:

This repository provides a complete RESTful API for managing books in Django. The API allows you to:

Create, read, update, and delete books.
Filter and search books by title, author, ISBN, and other fields.
Order books by different criteria.
Access details of a specific book.
Create and manage authors.
Features:

Authentication and access token: The API uses token authentication to protect its endpoints.
Data validation: The API validates data input to ensure data integrity.
Complete documentation: The API includes complete documentation using the OpenAPI standard.
Automated tests: The API has automated tests to ensure code quality.
Requirements:

Python 3.7 or higher
Django 3.2 or higher
Django REST Framework 3.12 or higher
Installation:

Clone the repository:
```
git clone https://github.com/Gustamv/Django-Book-API.git
```
Create a virtual environment and activate it:
```
python -m venv venv

source venv/bin/activate
```
Install the dependencies:
```
pip install -r requirements.txt
```
Create the database:
```
python manage.py makemigrations

python manage.py migrate
```
Run the server:
```
python manage.py runserver
```
Models

Book:
id: Unique identifier for the book (UUIDField)
title: Book title (CharField)
author: Book author (CharField)
isbn: ISBN number (CharField)
published_date: Publication date (DateField)
description: Book description (TextField, optional)
created_at: Date the book was created (DateTimeField, auto_now_add=True)
updated_at: Date the book was last updated (DateTimeField, auto_now=True)

API Usage:

The API can be accessed through RESTful endpoints. The complete API documentation is available at https://www.merriam-webster.com/dictionary/removed.

Usage examples:

Create a book:
```
curl -X POST \
  -H "Content-Type: application/json" \
  -H "Authorization: Token <token>" \
  -d '{
    "title": "Animal Farm",
    "author": "George Orwell",
    "isbn": "978-85-7522-470-6"
  }' \
  "http://localhost:8000/api/books/"
```
Get a book:
```
curl -X GET \
  -H "Authorization: Token <token>" \
  "http://localhost:8000/api/books/1/"
```
Update a book:
```
curl -X PUT \
  -H "Content-Type: application/json" \
  -H "Authorization: Token <token>" \
  -d '{
    "title": "Animal Farm",
    "author": "George Orwell",
    "isbn": "978-85-7522-470-6",
    "published_date": "2023-08-17"
  }' \
  "http://localhost:8000/api/books/1/"
```
Delete a book:
```
curl -X DELETE \
  -H "Authorization: Token <token>" \
  "http://localhost:8000/api/books/1/"
```
