# Library Management System

## Introduction

This is a Library Management System backend built using Django and Django REST Framework. It includes models for books and library users, demonstrating various relationships. The provided APIs allow interaction with these models.

## Project Structure

- `library/`: Django app containing models, serializers, views, and URLs.
- `manage.py`: Django management script.
- `requirements.txt`: List of project dependencies.
- `README.md`: Project documentation.

## Setup Instructions

1. **Clone the Repository:**

    ```bash
    git clone https://github.com/iaryangoyal/Library.git
    cd library
    ```

2. **Create Virtual Environment:**

    ```bash
    python -m venv venv
    ```

3. **Activate Virtual Environment:**

    - On Windows:

      ```bash
      venv\Scripts\activate
      ```

    - On macOS/Linux:

      ```bash
      source venv/bin/activate
      ```

4. **Install Dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

5. **Run Migrations:**

    ```bash
    python manage.py migrate
    ```

6. **Create Superuser (Optional):**

    ```bash
    python manage.py createsuperuser
    ```

7. **Run Development Server:**

    ```bash
    python manage.py runserver
    ```

    Access the Django admin site at [http://localhost:8000/admin](http://localhost:8000/admin).

## API Documentation

### User APIs

1. **Create a New User:**

    - Endpoint: `/api/users/`
    - Method: POST
    - Request Payload Example:

      ```json
      {
        "name": "John Doe",
        "email": "john@example.com",
        "membership_date": "2024-01-30"
      }
      ```

2. **List All Users:**

    - Endpoint: `/api/users/`
    - Method: GET

3. **Get User by ID:**

    - Endpoint: `/api/users/{user_id}/`
    - Method: GET

### Book APIs

1. **Add a New Book:**

    - Endpoint: `/api/books/`
    - Method: POST
    - Request Payload Example:

      ```json
      {
        "title": "The Great Gatsby",
        "ISBN": "978-3-16-148410-0",
        "published_date": "2022-01-30",
        "genre": "Fiction",
        "details": {
          "number_of_pages": 300,
          "publisher": "Penguin Books",
          "language": "English"
        }
      }
      ```

2. **List All Books:**

    - Endpoint: `/api/books/`
    - Method: GET

3. **Get Book by ID:**

    - Endpoint: `/api/books/{book_id}/`
    - Method: GET

4. **Assign/Update Book Details:**

    - Endpoint: `/api/books/{book_id}/`
    - Method: PUT
    - Request Payload Example:

      ```json
      {
        "details": {
          "number_of_pages": 350,
          "publisher": "Updated Publisher",
          "language": "Updated Language"
        }
      }
      ```

### BorrowedBooks APIs

1. **Borrow a Book:**

    - Endpoint: `/api/borrowedbooks/create/`
    - Method: POST
    - Request Payload Example:

      ```json
      {
        "user_id": 1,
        "book_id": 2
      }
      ```

2. **Return a Book:**

    - Endpoint: `/api/borrowedbooks/return/{borrowed_book_id}/`
    - Method: PUT

3. **List All Borrowed Books:**

    - Endpoint: `/api/borrowedbooks/`
    - Method: GET

