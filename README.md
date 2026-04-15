# 🐘 WebDev with PHP

> A beginner-friendly PHP learning website with interactive lessons and a user authentication system.

![PHP](https://img.shields.io/badge/PHP-8.0%2B-777BB4?style=flat&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?style=flat&logo=mysql&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-Frontend-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-Styled-1572B6?style=flat&logo=css3&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)

---

## 📖 About

**WebDev with PHP** is a free, beginner-friendly educational website that teaches PHP programming from scratch. It covers 10+ core PHP topics with clear explanations and examples, and includes a fully functional user authentication system so learners can register, log in, and submit queries.

---

## ✨ Features

- 📚 **10 PHP Learning Modules** — structured lessons covering the fundamentals
- 🔐 **User Authentication** — secure register/login/logout system using `password_hash` and prepared statements
- 📬 **Query Submission** — logged-in users can submit questions/queries stored in the database
- 📱 **Responsive Design** — mobile-friendly layout with a hamburger navigation menu
- 🎨 **Clean UI** — custom CSS with a professional look and a code-window hero section

---

## 📚 Topics Covered

| # | Topic |
|---|-------|
| 1 | 📚 Introduction to PHP |
| 2 | 📦 PHP Variables |
| 3 | ⚙️ PHP Functions |
| 4 | 📝 PHP Strings |
| 5 | 📊 PHP Arrays |
| 6 | 📋 PHP Forms |
| 7 | 🗄️ PHP Database Connectivity (MySQL) |
| 8 | 🍪 PHP Cookies |
| 9 | 🔐 PHP Sessions |
| 10 | 📁 PHP File System |

---

## 🗂️ Project Structure

```
phpfweb/
├── index.html        # Home page with hero, features, and PHP intro
├── lrnphp.html       # Main learning page with all 10 PHP topics
├── about.html        # About page
├── login.php         # User login with session management
├── register.php      # New user registration
├── logout.php        # Session destroy and redirect
├── query.php         # Protected page for logged-in users to submit queries
├── config.php        # Database connection configuration
├── index.css         # Main stylesheet for home page
├── styles.css        # Shared/global styles
├── style1.css        # Additional styles
└── mypic.jpeg        # Site image asset
```

---

## 🛠️ Tech Stack

- **Frontend:** HTML5, CSS3 (vanilla)
- **Backend:** PHP 8+
- **Database:** MySQL (via MySQLi with prepared statements)
- **Auth:** PHP Sessions + `password_hash` / `password_verify`

---

## ⚙️ Getting Started

### Prerequisites

- [XAMPP](https://www.apachefriends.org/) or any local server with **PHP 8+** and **MySQL**
- A web browser

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/phpfweb.git
   ```

2. **Move to your server's web root**
   ```bash
   # For XAMPP on Windows:
   mv phpfweb/ C:/xampp/htdocs/

   # For XAMPP on Linux/macOS:
   mv phpfweb/ /opt/lampp/htdocs/
   ```

3. **Set up the database**

   Open **phpMyAdmin** (or your MySQL client) and run:

   ```sql
   CREATE DATABASE j4java;

   USE j4java;

   CREATE TABLE users (
     id INT AUTO_INCREMENT PRIMARY KEY,
     username VARCHAR(50) NOT NULL UNIQUE,
     password VARCHAR(255) NOT NULL,
     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );

   CREATE TABLE queries (
     id INT AUTO_INCREMENT PRIMARY KEY,
     user_id INT NOT NULL,
     query_text TEXT NOT NULL,
     submitted_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
     FOREIGN KEY (user_id) REFERENCES users(id)
   );
   ```

4. **Configure the database connection**

   Open `config.php` and update your credentials if needed:

   ```php
   $host = 'localhost';
   $db   = 'j4java';
   $user = 'root';
   $pass = '';  // your MySQL password
   ```

5. **Start your local server and visit:**
   ```
   http://localhost/phpfweb/index.html
   ```

---

## 🔐 Authentication Flow

```
Register (register.php)
    ↓ stores hashed password
Login (login.php)
    ↓ verifies password, starts session
Query Submission (query.php)  ← protected, redirects to login if not logged in
    ↓
Logout (logout.php)  → destroys session → redirects to login
```

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a new branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

Built as an educational resource for PHP beginners. 100% free to use and learn from.
