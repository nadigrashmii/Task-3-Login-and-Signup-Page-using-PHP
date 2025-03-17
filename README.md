# User Authentication System (PHP & MySQL)

## **Project Overview**
This project is a **Login and Signup system** using **PHP and MySQL**. It securely stores user credentials in a database, allowing users to register, log in, and access a protected dashboard.

---
## **Installation & Setup**
### **1. Install Required Software**
- **XAMPP** (Apache + MySQL + PHP) - [Download](https://www.apachefriends.org/index.html)
- **VS Code** (Text Editor) - [Download](https://code.visualstudio.com/)

### **2. Start XAMPP Services**
1. Open **XAMPP Control Panel**.
2. Start **Apache** (PHP) and **MySQL** (Database).

### **3. Clone or Download the Project**
- Clone using Git:
  ```sh
  git clone https://github.com/your-repo/user_auth_project.git
  ```
- OR manually download and extract the project folder.

### **4. Setup MySQL Database**
1. Open **phpMyAdmin** (`http://localhost/phpmyadmin`).
2. Create a database:
   ```sql
   CREATE DATABASE user_auth;
   ```
3. Select the **user_auth** database and run the following SQL command:
   ```sql
   CREATE TABLE users (
       id INT AUTO_INCREMENT PRIMARY KEY,
       username VARCHAR(50) NOT NULL UNIQUE,
       email VARCHAR(100) NOT NULL UNIQUE,
       password VARCHAR(255) NOT NULL,
       created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   ```

### **5. Configure the Database Connection**
Edit the **db.php** file with your MySQL credentials:
```php
<?php
$host = "localhost";
$username = "root";
$password = "";
$database = "user_auth";
$conn = new mysqli($host, $username, $password, $database);
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
?>
```

### **6. Start the PHP Server**
Open **VS Code Terminal** and navigate to the project folder:
```sh
cd C:\xampp\htdocs\user_auth_project
php -S localhost:8000
```
Then open your browser and visit:
- **Signup Page:** `http://localhost:8000/signup.html`
- **Login Page:** `http://localhost:8000/login.html`

---
## **Project Structure**
```
user_auth_project/
│── db.php          # Database connection file
│── signup.php      # Handles user registration
│── login.php       # Handles user login
│── dashboard.php   # Protected user dashboard
│── logout.php      # Logs out the user
│── index.html      # Home page
│── signup.html     # Signup form UI
│── login.html      # Login form UI
│── styles.css      # CSS for styling
└── .htaccess       # (Optional) Security configurations
```

---
## **Usage Instructions**
### **Signup Process**
1. Open `signup.html`.
2. Enter username, email, and password.
3. Click **Sign Up**.
4. If successful, you'll be redirected to the login page.

### **Login Process**
1. Open `login.html`.
2. Enter **username/email** and **password**.
3. Click **Login**.
4. If successful, you'll be redirected to `dashboard.php`.

### **Logout Process**
- Click **Logout** to destroy the session and return to `login.html`.


🚀 **Happy Coding!**

