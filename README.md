

---

# FastAPI User Management Application

This is a FastAPI-based application for managing user resources. It provides REST API endpoints for performing CRUD (Create, Read, Update, Delete) operations on a `User` resource. The application uses PostgreSQL as the database.

## Features
- Create, read, update, and delete users.
- RESTful API endpoints for user management.
- PostgreSQL database integration.
- Asynchronous database operations for improved performance.

## Prerequisites
Before running the application, ensure you have the following installed:
1. **Python 3.8+**
2. **PostgreSQL** (installed and running)
3. **pip** (Python package manager)

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-repo/fastapi-user-app.git
cd fastapi-user-app
```

### 2. Set Up a Virtual Environment
```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows:
venv\Scripts\activate

# On macOS/Linux:
source venv/bin/activate
```

### 3. Install Dependencies
Install the required Python packages using the `requirements.txt` file:
```bash
pip install -r requirements.txt
```

### 4. Set Up PostgreSQL Database
1. Create a PostgreSQL database:
   ```sql
   CREATE DATABASE userdb;
   ```
2. Create a user and grant privileges:
   ```sql
   CREATE USER fastapi_user WITH PASSWORD 'password';
   GRANT ALL PRIVILEGES ON DATABASE userdb TO fastapi_user;
   ```

3. Update the database connection URL in the `main.py` file:
   ```python
   DATABASE_URL = "postgresql+asyncpg://fastapi_user:password@localhost/userdb"
   ```

### 5. Run the Application
Start the FastAPI application using Uvicorn:
```bash
uvicorn main:app --reload
```

The application will be available at `http://localhost:8000`.

### 6. Access API Documentation
FastAPI automatically generates interactive API documentation:
- **Swagger UI:** `http://localhost:8000/docs`
- **ReDoc:** `http://localhost:8000/redoc`

---

## API Endpoints

### 1. **Create a User**
- **Method:** `POST`
- **URL:** `/users`
- **Request Body:**
  ```json
  {
      "name": "John Doe",
      "email": "john@example.com",
      "password": "secret123"
  }
  ```
- **Response:**
  ```json
  {
      "id": 1,
      "name": "John Doe",
      "email": "john@example.com"
  }
  ```

### 2. **Get All Users**
- **Method:** `GET`
- **URL:** `/users`
- **Response:**
  ```json
  [
      {
          "id": 1,
          "name": "John Doe",
          "email": "john@example.com"
      }
  ]
  ```

### 3. **Get a Single User**
- **Method:** `GET`
- **URL:** `/users/{user_id}`
- **Response:**
  ```json
  {
      "id": 1,
      "name": "John Doe",
      "email": "john@example.com"
  }
  ```

### 4. **Update a User**
- **Method:** `PUT`
- **URL:** `/users/{user_id}`
- **Request Body:**
  ```json
  {
      "name": "John Updated",
      "email": "john.new@example.com",
      "password": "newsecret456"
  }
  ```
- **Response:**
  ```json
  {
      "id": 1,
      "name": "John Updated",
      "email": "john.new@example.com"
  }
  ```

### 5. **Delete a User**
- **Method:** `DELETE`
- **URL:** `/users/{user_id}`
- **Response:**
  ```json
  {
      "message": "User deleted successfully"
  }
  ```






## Contact
For questions or feedback, please contact:
- **uday tripurani**
- **Email:** udaytripurani@gmail.com
- **GitHub:** [uday](https://github.com/udaytripurani)

