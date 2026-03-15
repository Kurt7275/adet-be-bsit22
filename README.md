# 📝 Blog Posts REST API

A RESTful API for managing blog posts, built with **Hono**, **TypeScript**, and **MySQL**.

---

## 🚀 Tech Stack

![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

---

## 📁 Project Structure
```
src/
├── config/
│   └── db.ts           # Database connection pool
├── controllers/
│   └── posts.controller.ts  # Request handlers
├── models/
│   └── posts.model.ts  # TypeScript interfaces
├── routes/
│   └── posts.route.ts  # API route definitions
└── index.ts            # App entry point
```

---

## ⚙️ Getting Started

### Prerequisites
- Node.js
- MySQL (XAMPP recommended)

### Installation

1. Clone the repository
```bash
   git clone https://github.com/Kurt7275/adet-be-bsit22
   cd adet-be-bsit22
```

2. Install dependencies
```bash
   npm install
```

3. Set up your `.env` file
```env
   DB_HOST=localhost
   DB_PORT=3306
   DB_USER=root
   DB_PASSWORD=
   DB_NAME=bsit-22
```

4. Set up the database
```sql
   CREATE DATABASE `bsit-22`;
   USE `bsit-22`;

   CREATE TABLE posts (
       post_id INT AUTO_INCREMENT PRIMARY KEY,
       title VARCHAR(60) NOT NULL,
       description TEXT,
       status ENUM('Active', 'Inactive') DEFAULT 'Active',
       created_at DATETIME DEFAULT CURRENT_TIMESTAMP
   );
```

5. Run the server
```bash
   npm run dev
```

6. Open in browser
```
   http://localhost:3000
```

---

## 📌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/posts` | Fetch all posts |
| `GET` | `/posts/:id` | Fetch a post by ID |
| `POST` | `/posts` | Create a new post |
| `PATCH` | `/posts/:id` | Update a post |
| `DELETE` | `/posts/:id` | Delete a post |

---

## 📨 Request Examples

### Create a Post
```json
POST /posts
{
  "title": "My First Post",
  "description": "Hello World",
  "status": "Active"
}
```

### Update a Post
```json
PATCH /posts/1
{
  "status": "Inactive"
}
```

---

## 👨‍💻 Author

**Kurt Xierick Bautista**
- GitHub: [@Kurt7275](https://github.com/Kurt7275)

---

## 📄 License

This project is for educational purposes —
**Liceo de Cagayan University | College of Information Technology**
