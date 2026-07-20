# MomentS

A full-stack social media web app built with React, Vite, Express, MongoDB, Socket.IO, and Cloudinary. MomentS supports user authentication, profile editing, post creation with image upload, likes, comments, bookmarks, follow system, real-time chat, and notifications.

## Features

- User registration and login
- Profile editing and avatar upload
- Create, like, dislike, bookmark, and delete posts
- Add comments to posts
- Follow and unfollow users
- Suggested users feed
- Realtime messaging with Socket.IO
- Like/notification events in real time
- Responsive React UI built with Tailwind CSS

## Tech Stack

- Frontend: React, Vite, React Router, Redux Toolkit, Tailwind CSS, Socket.IO Client
- Backend: Node.js, Express, MongoDB, Mongoose, JWT, Cloudinary, Socket.IO
- Authentication: JWT stored in cookies
- Image upload: Cloudinary via `sharp` and `multer`

## Prerequisites

- Node.js 18+ / npm
- MongoDB connection string
- Cloudinary account

## Setup

1. Clone the repository

```bash
git clone <repository-url>
cd instaclone-main
```

2. Install root dependencies and frontend dependencies

```bash
npm install
npm install --prefix frontend
```

3. Create a `.env` file in the root project directory with the following variables:

```env
PORT=8000
URL=http://localhost:8000
MONGO_URI=<your-mongodb-connection-string>
SECRET_KEY=<your-jwt-secret>
CLOUD_NAME=<your-cloudinary-cloud-name>
API_KEY=<your-cloudinary-api-key>
API_SECRET=<your-cloudinary-api-secret>
```

> The backend serves the compiled frontend from `frontend/dist` in production mode.

## Running the Project

### Development mode

```bash
npm run dev
```

This starts the Express backend with `nodemon` and expects the frontend assets to already exist in `frontend/dist` when running production behavior. For development of frontend separately, you can start Vite inside `frontend`:

```bash
cd frontend
npm run dev
```

### Production / Build

Build the frontend and ensure the backend serves the compiled files:

```bash
npm run build
npm start
```

## Project Structure

- `backend/` - Express server, MongoDB models, routes, controllers, and real-time Socket.IO setup
  - `controllers/` - business logic for users, posts, and messages
  - `middlewares/` - authentication and file upload middleware
  - `models/` - Mongoose schemas for users, posts, comments, conversations, and messages
  - `routes/` - backend routes exposed under `/api/v1`
  - `socket/` - Socket.IO server configuration and event handling
  - `utils/` - database connection, Cloudinary setup, and file helpers
- `frontend/` - React application powered by Vite
  - `src/` - main application source files
  - `src/components/` - page and UI components
  - `src/hooks/` - reusable custom hooks for API data fetching
  - `src/redux/` - application state management with Redux Toolkit
  - `public/` - static assets served by Vite

## Notes

- The backend serves the compiled frontend from `frontend/dist` in production mode.
- The frontend and backend communicate through the configured `URL` environment variable.
- Socket.IO is used for real-time chat and notification events.
