# MERN Auth Boilerplate

A full-stack authentication boilerplate with JWT-based login/signup, profile picture upload, protected routes, and a minimal React frontend.

## Tech Stack

- **Frontend:** Frontend: React, Vite, Tailwind CSS
- **Backend:**  Node.js, Express, MongoDB, Mongoose
- **Other:** Cloudinary for image upload, JWT authentication, Middleware & Error Handling

---

## Setup Instructions

```bash

1. Clone the repo:
git clone https://github.com/CoderKashyap/Mern-Auth-Boilerplate.git

2. Install frontend dependencies:
cd frontend
npm install

3. (Option A) Build frontend to let backend serve it:
npm run build

4. OR (Option B) run frontend in dev mode:
npm run dev

5. Install backend dependencies:
cd ../backend
npm install

6. Create config.env file in: backend/config/config.env

PORT=4000
DB_URI=your_mongodb_connection_string
JWT_SECRET=yourJwtSecret
JWT_EXPIRE=5d
COOKIE_EXPIRE=5
CLOUDINARY_NAME=yourCloudinaryName
CLOUDINARY_API_KEY=yourKey
CLOUDINARY_API_SECRET=yourSecret

7. Start backend server:
npm run dev



**API Documentation**

**Auth**

POST /api/auth/register
Request: { "username": "testuser", "email": "test@mail.com", "password": "123456" }
Response: { success: true, user, token }


POST /api/auth/login
Request: { "email": "test@mail.com", "password": "123456" }
Response: { success: true, user, token }

**User Profile**

GET /api/user/me
Protected route.
Returns logged-in user details.

POST /api/user/upload
Multipart FormData
Uploads profile image to Cloudinary and updates user.

Request Example:
formData: { image: File }
Response:{
  "success": true,
  "avatarUrl": "https://res.cloudinary.com/.../image.jpg"
}


**Frontend Pages**

Home Page – buttons for Login and Register
Register Page – create new user
Login Page – authenticate user
Upload Profile Page – upload profile picture
Profile Page – shows username and uploaded image


**Backend Overview**

The backend contains complete authentication logic:
- JWT generation & verification
- Secure HTTP-only cookies (optional)
- Protected routes using middleware
- User model using Mongoose
- Cloudinary integration for profile images
- Centralized error handling architecture
