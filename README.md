# Simple Login Flask App 
A minimal flask project implementing user registration and login.
Based on [this tutorial](https://www.geeksforgeeks.org/python/login-and-registration-project-using-flask-and-mysql/). I've changed a couple of things:
- password hashing (using Werkezeug);
- adding secure cookie settings;
- using enviroment variables for credentials and secret key.

## Setup Instructions
### 1. Enviroment
- Create a virtual enviroment by running ```python venv -m .venv```
- Install the required libraries by running ```pip install -r requirements.txt```
### 2. Database
- Make sure to have MySQL installed;
- Create a database and a table (with an id, username, email and password field), you can use the following commands in the terminal if you want:
1) ```mysql -u root -p``` , this will let you run mysql commands on your terminal
2)

    CREATE DATABASE yourDatabaseName
    DEFAULT CHARACTER SET utf8mb4
    COLLATE utf8mb4_general_ci;
3)

    CREATE TABLE IF NOT EXISTS accounts (
        id INT(11) NOT NULL AUTO_INCREMENT,
        username VARCHAR(50) NOT NULL,
        password VARCHAR(255) NOT NULL,
        email VARCHAR(100) NOT NULL,
        PRIMARY KEY (id)
    ) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8mb4;

### 3. Setting up an .env
- Next you'll want to create a .env file with two fields MYSQL_PASSWORD and SECRET_KEY. The first is to have root access to MySQL, and the second will be the secret key with which your cookies will be encoded.
- To generate the SECRET_KEY you can run ```import secrets print(secrets.token_hex(16))``` in a python file or the terminal.
### 4. Running the app
- In the terminal: ```flask run``` or ```python app.py```— make sure your venv is active. The login app will be running on localhost.