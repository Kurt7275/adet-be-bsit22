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
│   └── db.ts                # Database connection pool
├── controllers/
│   └── posts.controller.ts  # Request handlers
├── models/
│   └── posts.model.ts       # TypeScript interfaces
├── routes/
│   └── posts.route.ts       # API route definitions
└── index.ts                 # App entry point
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

## 🧪 Testing with Postman

### ⬇️ Download Postman
👉 https://www.postman.com/downloads

---

### 1️⃣ GET — Fetch All Posts

| Field | Value |
|-------|-------|
| Method | `GET` |
| URL | `http://localhost:3000/posts` |
| Body | None |

**Expected Response:**
```json
[
  {
    "post_id": 1,
    "title": "My First Post",
    "description": "Hello World",
    "status": "Active",
    "created_at": "2026-03-15T08:53:42.000Z"
  }
]
```

---

### 2️⃣ GET — Fetch Post by ID

| Field | Value |
|-------|-------|
| Method | `GET` |
| URL | `http://localhost:3000/posts/1` |
| Body | None |

**Expected Response:**
```json
{
  "post_id": 1,
  "title": "My First Post",
  "description": "Hello World",
  "status": "Active",
  "created_at": "2026-03-15T08:53:42.000Z"
}
```

---

### 3️⃣ POST — Create a New Post

| Field | Value |
|-------|-------|
| Method | `POST` |
| URL | `http://localhost:3000/posts` |
| Body | `raw` → `JSON` |

**Request Body:**
```json
{
  "title": "My First Post",
  "description": "Hello World",
  "status": "Active"
}
```

**Expected Response** `201 Created`:
```json
{
  "post_id": 1,
  "title": "My First Post",
  "description": "Hello World",
  "status": "Active",
  "created_at": "2026-03-15T08:53:42.000Z"
}
```

> ⚠️ `title` is **required**. Leaving it empty returns a `400` error.

---

### 4️⃣ PATCH — Update a Post

| Field | Value |
|-------|-------|
| Method | `PATCH` |
| URL | `http://localhost:3000/posts/1` |
| Body | `raw` → `JSON` |

**Request Body:**
```json
{
  "status": "Inactive"
}
```

> You can update any combination of `title`, `description`, and `status`.

**Expected Response** `200 OK`:
```json
{
  "post_id": 1,
  "title": "My First Post",
  "description": "Hello World",
  "status": "Inactive",
  "created_at": "2026-03-15T08:53:42.000Z"
}
```

---

### 5️⃣ DELETE — Remove a Post

| Field | Value |
|-------|-------|
| Method | `DELETE` |
| URL | `http://localhost:3000/posts/1` |
| Body | None |

**Expected Response** `200 OK`:
```json
{
  "message": "Post successfully deleted"
}
```

**If post doesn't exist** `404 Not Found`:
```json
{
  "message": "Post not found"
}
```

---

### 💡 Postman Tips
- Always do a **POST** first to create data before testing GET, PATCH, or DELETE
- Set Body type to **raw** and format to **JSON** for POST and PATCH requests
- Check the **status code** in Postman to verify correct responses

---

## 👨‍💻 Author

**Kurt Xierick Bautista**
- GitHub: [@Kurt7275](https://github.com/Kurt7275)

---

## 📄 License

This project is for educational purposes —
**Liceo de Cagayan University | College of Information Technology**
