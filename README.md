# ⚙️ Modern Blog Platform (Backend API)

The backend API for a MERN stack blog platform, built with **Node.js**, **Express**, and **MongoDB Atlas**.  
This server handles authentication, blog management, AI content generation, and secure data operations.

---

## 🚀 Features

1. **Authentication (JWT)** – Secure user registration and login with hashed passwords via `bcryptjs`.
2. **Blog CRUD** – Admins can create, edit, delete, and fetch posts with optional cover images.
3. **Tags & Search** – Fetch posts by tag, search by title/content, or get trending posts.
4. **Markdown Support** – Posts support markdown content rendered on the frontend.
5. **AI Generation** – Generate ideas, summaries, full posts, and comment replies using **Google Gemini API**.
6. **Comments** – Authenticated users can post and delete comments.
7. **Dashboard Summary** – Admin analytics endpoint for quick overviews.
8. **CORS & Uploads** – Securely handles cross-origin requests and image uploads.
9. **JWT Middleware** – Route-level access control for users and admins.

---

## 🧩 Tech Stack

| Category | Technologies |
|-----------|---------------|
| **Runtime** | Node.js |
| **Framework** | Express 5.x |
| **Database** | MongoDB (Mongoose 8.x) |
| **Auth** | JWT (`jsonwebtoken`) + `bcryptjs` |
| **AI** | `@google/genai` (Gemini API) |
| **File Uploads** | `multer` |
| **Environment Config** | `dotenv` |
| **CORS Handling** | `cors` |

---

## ⚙️ Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/blog-app-backend.git
   cd blog-app-backend
   ```

2. **Install dependencies**
   ```bash
    npm install
   ```

3. **Create a .env file**
   ```bash
   git clone https://github.com/yourusername/blog-app-backend.git
   cd blog-app-backend
   ```

4. **Run in development**
   ```bash
   npm run dev
   ```

5. **Run in production**
   ```bash
   npm start
   ```

## API overview

### Auth Routes → /api/auth

| Method | Endpoint        | Description                  | Auth |
| ------ | --------------- | ---------------------------- | ---- |
| POST   | `/register`     | Register a new user          | ❌    |
| POST   | `/login`        | Login, returns JWT token     | ❌    |
| GET    | `/profile`      | Fetch logged-in user profile | ✅    |
| POST   | `/upload-image` | Upload profile/cover image   | profile ✅ - cover ✅    |


## Blog Routes → /api/posts

| Method | Endpoint      | Description                      | Auth    |
| ------ | ------------- | -------------------------------- | ------- |
| POST   | `/`           | Create a new post *(admin only)* | ✅ admin |
| GET    | `/`           | Get all published posts          | ❌       |
| GET    | `/slug/:slug` | Get single post by slug          | ❌       |
| PUT    | `/:id`        | Update post *(admin only)*       | ✅ admin |
| DELETE | `/:id`        | Delete post *(admin only)*       | ✅ admin |
| GET    | `/tag/:tag`   | Get posts by tag                 | ❌       |
| GET    | `/search`     | Search posts by keyword          | ❌       |
| POST   | `/:id/view`   | Increment post view count        | ❌       |
| POST   | `/:id/like`   | Like or unlike a post            | ✅       |
| GET    | `/trending`   | Get top trending posts           | ❌       |

## Comment Routes → /api/comments

| Method | Endpoint      | Description                    | Auth    |
| ------ | ------------- | ------------------------------ | ------- |
| POST   | `/:postId`    | Add comment to post            | ✅       |
| GET    | `/:postId`    | Get all comments for a post    | ❌       |
| GET    | `/`           | Get all comments (admin panel) | ✅ admin |
| DELETE | `/:commentId` | Delete a comment               | ✅       |

## AI Routes → /api/ai

| Method | Endpoint            | Description                      | Auth |
| ------ | ------------------- | -------------------------------- | ---- |
| POST   | `/generate`         | Generate full markdown blog post | ✅    |
| POST   | `/generate-ideas`   | Generate blog topic ideas        | ✅    |
| POST   | `/generate-reply`   | Generate AI comment replies      | ✅    |
| POST   | `/generate-summary` | Generate summary for a post      | ❌    |


## Dashboard Routes → /api/dashboard-summary

| Method | Endpoint | Description                 | Auth    |
| ------ | -------- | --------------------------- | ------- |
| GET    | `/`      | Get admin dashboard summary | ✅ admin |


## Deployment

### Status: Coming Soon 


## 👤 Author

**Mohamed Ragab Awad Bahr**  
📍 Markham, Ontario, Canada  
🎓 B.Sc. Mechanical Engineering – *Virginia Tech*  
🎓 Diploma in Computer Programming – *Seneca Polytechnic*  
🔗 [LinkedIn](https://www.linkedin.com/in/mohamed-bahr-84656a278/)  
💻 [GitHub](https://github.com/MoBahr98)