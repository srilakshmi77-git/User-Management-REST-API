# User Management API using Flask

## Project Overview

This project is a simple REST API developed using Python Flask. The API allows users to add multiple names through a POST request and retrieve all stored users through a GET request. Data is stored temporarily in a Python list during runtime.

## Objective

The objective of this project is to demonstrate the implementation of RESTful APIs using Flask, including handling GET and POST requests and returning JSON responses.

## Technologies Used

* Python 3.x
* Flask
* JSON

## Project Structure

project-2/
│
├── backend.py
├── post.py
└── README.md
```

## Source Code Description

The application contains:

### GET Endpoint

Retrieves all users currently stored in memory.

```http
GET /users
```

### POST Endpoint

Accepts multiple user names and stores them in the application.

```http
POST /users
```

### Request Format

```json
{
  "names": [
    "Lakshmi",
    "Ravi",
    "Kalyan"
  ]
}
```

### Response Format

```json
{
  "message": "Users added successfully",
  "users": [
    {
      "id": 1,
      "name": "Lakshmi"
    },
    {
      "id": 2,
      "name": "Ravi"
    },
    {
      "id": 3,
      "name": "Kalyan"
    }
  ]
}
```

## Installation

### Step 1: Install Python

Download and install Python 3.x from the official Python website.

### Step 2: Install Flask

Open Command Prompt and run:

```bash
pip install flask
```

### Step 3: Verify Installation

```bash
python --version
pip show flask
```

## Running the Application

Navigate to the project directory and run:

```bash
python app.py
```

Output:

```text
* Running on http://127.0.0.1:5000
```

## Testing the API

### Using a Web Browser

Open:

```text
http://127.0.0.1:5000/users
```

This will display all users currently stored.

### Using Python Requests Library

Create a file named `test.py` and add the following code:

```python
import requests

url = "http://127.0.0.1:5000/users"

data = {
    "names": ["Lakshmi", "Ravi", "Kalyan"]
}

response = requests.post(url, json=data)

print(response.json())
```

### Running the Test

1. Start the Flask server:

```bash
python app.py
```

2. Open a new terminal.
3. Run the test file:

```bash
python test.py
```

### Expected Output

```json
{
  "message": "Users added successfully",
  "users": [
    {
      "id": 1,
      "name": "Lakshmi"
    },
    {
      "id": 2,
      "name": "Ravi"
    },
    {
      "id": 3,
      "name": "Kalyan"
    }
  ]
}
```

### Retrieving Stored Users

After executing `test.py`, open:

```text
http://127.0.0.1:5000/users
```
## Limitations

* Data is stored only in memory.
* Data is lost when the server is restarted.
* No database integration.
* No update or delete functionality.

## Future Enhancements

* Integrate MySQL or MongoDB.
* Add PUT API for updating users.
* Add DELETE API for removing users.
* Implement input validation.
* Add authentication and authorization.

## Learning Outcomes

* Understanding Flask application structure.
* Creating RESTful APIs.
* Handling GET and POST requests.
* Working with JSON data.
* Testing APIs using Postman.

## Conclusion

This project successfully demonstrates the development of a simple User Management REST API using Python Flask. It provides basic functionality for adding and retrieving users and serves as a foundation for more advanced backend development projects.


