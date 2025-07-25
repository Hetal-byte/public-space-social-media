
# 📢 Public Space – Friend-Gated Social Media Platform

A **Node.js-powered social network** that flips the script on traditional platforms. In this world, your social circle isn’t just clout—it’s your **posting fuel**. No friends? No posts. More friends? More power. Welcome to a social space where quality connections = expression.

---

## 🔍 Project Overview

This is a dynamic full-stack web app built using **Node.js + Express** on the backend and **Vanilla JS, HTML5, and CSS3** on the frontend. It introduces a gamified posting system that encourages organic connection growth by limiting post frequency based on a user's friend count.

---

## 🚀 Core Features

### 🔐 User Authentication

- **Register** with username, email & password  
- **Login** with secure JWT-based session  
- **Token Expiry** after 24 hours  
- **Password Encryption** via `bcryptjs`  

### 👥 Friend System

- Add friends via **email**
- Smart checks: ❌ No self-friends or duplicates
- Real-time **friend counter**  
- Social growth fuels platform interaction

### 📝 Friend-Gated Posting Rules

| Friends | Posts/Day |
|---------|-----------|
| 0       | ❌ None   |
| 1       | 1         |
| 2–9     | 2         |
| 10+     | 🔓 Unlimited |

### 📸 Post Management

- Text + optional **media attachments**
- Supported Media:
  - Images: `jpeg`, `jpg`, `png`, `gif`
  - Videos: `mp4`, `mov`, `avi`, `mkv`
- File Limit: **50MB max**
- Features:
  - ❤️ Like/unlike
  - 💬 Commenting
  - 🔁 Share tracking
  - 🔄 Real-time metrics

---

## 🏗️ Tech Stack

### Backend

- **Express.js** - Web framework
- **JWT** - Session security
- **bcryptjs** - Password hashing
- **Multer** - Media file uploads
- **CORS** - Secure cross-origin access
- **Body-parser** - Flexible request parsing

### Frontend

- **Vanilla JS** - Dynamic UI logic
- **HTML5** - Semantic structure
- **CSS3** - Clean, responsive layout

---

## 💾 Data Handling

Currently using **in-memory storage** for:

- Users & credentials  
- Posts, media, likes, comments  
- Friend relationships  
- JWT session tokens

⚠️ **Note**: Replace with **MongoDB**, **PostgreSQL**, or other DB for production.

---

## ⚙️ Installation & Setup

### 🔧 Prerequisites

```bash
npm install
```

### 📦 Dependencies

#### Production:
- `bcryptjs`
- `body-parser`
- `cors`
- `express`
- `jsonwebtoken`
- `multer`

#### Dev:
- `nodemon` – auto-reloads server during development

### 🌍 Run the App

- **Dev Mode**  
  ```bash
  npm run dev
  ```

- **Production Mode**  
  ```bash
  npm start
  ```

- **Default Access Points**  
  - Localhost: `http://localhost:3000`  
  - Network: `http://0.0.0.0:3000`

---

## 📡 API Endpoints

### 🔐 Authentication

**Register** – `POST /api/register`  
Fields: `username`, `email`, `password`  
Returns: JWT token + user data

**Login** – `POST /api/login`  
Fields: `email`, `password`  
Returns: JWT token + session info

### 👤 User Info

**Get Info** – `GET /api/user/info`  
Auth: ✅ Required  
Returns: Friend count, post limit, posting eligibility

### 🤝 Friend Actions

**Add Friend** – `POST /api/friends/add`  
Body: `email`  
Validates: no self/duplicate adds

### 📝 Post Actions

**Create Post** – `POST /api/posts`  
Auth: ✅ Required  
Body: text + optional media file  
Checks: file size, type, daily limit

**Get Posts** – `GET /api/posts`  
Returns: all posts + interaction stats

**Like** – `POST /api/posts/:postId/like`  
Toggles like status

**Comment** – `POST /api/posts/:postId/comment`  
Field: `comment`  
Returns: comment object

**Share** – `POST /api/posts/:postId/share`  
Increments share counter

---

## 📁 Project Structure

```
project-root/
├── server.js          # Server + API routes
├── index.html         # UI structure
├── script.js          # Frontend logic
├── style.css          # Styling & responsiveness
├── package.json       # Config & dependencies
├── uploads/           # Uploaded media files
└── README.md          # You're here!
```

---

## 🔐 Security Summary

- **Passwords** hashed before storage
- **JWTs** for session validation
- **CORS** restricted origin access
- **Upload Validations**:
  - File type & size enforced
  - Directory isolated
- **Rate limiting** via posting logic

---

## 🌍 Browser & UX Compatibility

- JS: Uses modern **ES6+**
- Media: Upload via `FormData`
- API: Uses native **Fetch**
- Storage: LocalStorage (temporary/session state)
- Layout: Fully **responsive design**

---

## 🧠 Developer Notes

> "Post less, connect more."

This project’s friend-gated interaction model reduces spam, increases meaningful content, and introduces a growth-based incentive structure.

🔮 Future Upgrades:
- MongoDB/PostgreSQL integration
- User feed algorithms
- Real-time notifications via WebSockets
- Admin/moderator dashboard
- Story feature, profile customization

---

## 🏁 License

MIT License. Open-source. Do your thing 🤘
