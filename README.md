# Threadly — Real-Time Chat & Thread-Based Social Platform

Threadly is a full-stack application that combines real-time messaging with a thread-driven social interaction system. It enables users to communicate instantly, share posts, and engage through likes and comments.

The system is designed with a strong focus on scalability, modular architecture, and real-time performance.

---

## Overview

Threadly allows users to:
- Communicate in real-time using WebSockets
- Create and explore thread-based posts
- Like and comment on posts
- Upload and manage media efficiently

---

## Tech Stack

### Frontend
- Next.js 
- TypeScript
- Tailwind CSS
- Socket.IO Client
- Clerk Authentication
- React Hook Form + Zod

### Backend
- Node.js
- Express.js
- PostgreSQL (pg)
- Socket.IO
- Clerk (Express SDK)
- Cloudinary
- Multer
- Winston

---

## Folder Structure

```bash
threadly/
│
├── frontend/                      # Next.js Frontend
│   ├── .next/
│   ├── node_modules/
│   ├── public/
│   │
│   ├── src/
│   │   ├── app/
│   │   │   ├── chat/
│   │   │   ├── notifications/
│   │   │   ├── profile/
│   │   │   ├── sign-in/
│   │   │   ├── sign-up/
│   │   │   ├── threads/
│   │   │   ├── favicon.ico
│   │   │   ├── globals.css
│   │   │   ├── layout.tsx
│   │   │   └── page.tsx
│   │   │
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── lib/
│   │   ├── types/
│   │   └── proxy.ts
│   │
│   ├── .env
│   ├── .gitignore
│   ├── components.json
│   ├── next-env.d.ts
│   ├── next.config.ts
│   ├── package.json
│   ├── package-lock.json
│   ├── postcss.config.mjs
│   ├── tsconfig.json
│   └── README.md
│
├── backend/                       # Express Backend
│   ├── node_modules/
│   │
│   ├── src/
│   │   ├── config/
│   │   ├── db/
│   │   ├── lib/
│   │   ├── middleware/
│   │   ├── migrations/
│   │   ├── modules/
│   │   ├── realtime/
│   │   ├── routes/
│   │   ├── app.ts
│   │   └── server.ts
│   │
│   ├── .env
│   ├── .gitattributes
│   ├── .gitignore
│   ├── .prettierignore
│   ├── .prettierrc
│   ├── package.json
│   ├── package-lock.json
│   └── tsconfig.json
│
├── docker-compose.yml
└── README.md
```

---

## Features

### Real-Time Chat
- WebSocket-based communication using Socket.IO
- Low-latency, event-driven messaging

### Thread Posts
- Create, edit, and delete posts
- Comment on threads
- Like and unlike posts

### Authentication
- Secure authentication using Clerk
- Session handling across frontend and backend

### Media Uploads
- File uploads using Multer
- Cloudinary integration for storage

### Validation & Logging
- Zod for schema validation
- Centralized error handling
- Logging with Winston

---

## Environment Variables

### Frontend (.env.local)
```env
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=
NEXT_PUBLIC_API_URL=
```

### Backend (.env)
```env
PORT=5000
DATABASE_URL=
CLERK_SECRET_KEY=
CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
```

---

## Getting Started

### Install Dependencies

```bash
# frontend
cd frontend
npm install

# backend
cd ../backend
npm install
```

### Run the Application

```bash
# backend

npm run migration
npm run dev

# frontend
npm run dev
```

---

## Docker Setup (PostgreSQL)

The project includes a Docker configuration for running PostgreSQL locally.

See configuration: :docker-compose.yml

### Run Database

```bash
docker-compose up -d
```

### Database Connection

```env
DATABASE_URL=postgresql://postgres:postgres@localhost:6450/threadly_chat_app
```

### Notes

- No need to install PostgreSQL locally
- Data persists via Docker volumes
- Easy to extend for production setups

---

## Architecture Highlights

- Modular backend structure (controllers, services, routes)
- Real-time communication using Socket.IO
- Feature-based organization (`modules`)
- Clean separation between frontend and backend
- Scalable and maintainable codebase

---

## Future Improvements

- Group chat support
- Notifications system
- Redis for scaling real-time events
- Infinite scrolling feed
- Read receipts and delivery tracking

---

## Author

Sahil Khan  
Full Stack Developer
