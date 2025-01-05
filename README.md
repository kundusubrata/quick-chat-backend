# Real-Time Chat Application - Backend

This repository contains the backend server for a real-time chat application built with TypeScript, Express, Socket.IO, Prisma, PostgreSQL, and Redis. It manages authentication, chat groups, users, and real-time messaging functionalities.

---

## Features

- User Authentication
- Create, Read, Update, and Delete (CRUD) operations for Chat Groups
- Real-time messaging with Socket.IO
- Scalable backend architecture

---

## Tech Stack

- **Language**: TypeScript
- **Framework**: Express.js
- **Database**: PostgreSQL (via Prisma ORM)
- **Caching/Queue**: Redis
- **Real-time Communication**: Socket.IO

---

## Prerequisites

Ensure you have the following installed on your system:

- [Node.js](https://nodejs.org/) (v16 or higher)
- [Docker](https://www.docker.com/)
- PostgreSQL (ensure a running database instance)

---

## Local Setup

Follow these steps to set up the backend server locally:

 1. Clone the Repository
	```
	git clone <repository-url>
	cd server
	```
2. Install Dependencies:
	```
	npm install
	```
3. Configure Environment Variablesa:
	Create a `.env` file in the root directory and set the following:
	```
	PORT=8000
	JWT_SECRET=jsfd234%$FD^&89dfsaSDF!@fsdlf432RET
	DATABASE_URL=""
	CLIENT_APP_URL=http://localhost:3000
	REDIS_URL="The URL is only for production use and for local Redis/Stack using Docker"
	```
4. Set Up Redis:
	```
	docker run -d --name redis-stack -p 6379:6379 -p 8001:8001 redis/redis-stack:latest
	```
5. Run Migrations:
	Use Prisma to push the database schema:
	```
	npx prisma db push
	```
6. Build and Run the Server:
	```
	npm run build 
	npm run dev
	```
	The server will run at http://localhost:8000.

## Available Routes

The backend provides the following routes:

### **Authentication**

-   `POST /api/auth/login`: Login a user.

### **Chat Groups**

-   `GET /api/chat-group`: Fetch all chat groups.
-   `POST /api/chat-group`: Create a new chat group.
-   `PUT /api/chat-group/:id`: Update a chat group.
-   `DELETE /api/chat-group/:id`: Delete a chat group.
-   `GET /api/chat-group/:id`: Get details of a specific chat group.

### **Chat Group Users**

-   `GET /api/chat-group-user`: Get all chat group users.
-   `POST /api/chat-group-user`: Add a user to a chat group.

### **Chats**

-   `GET /api/chats/:groupId`: Fetch all chats for a specific group.

----------

## Production URL

The application is deployed at:  
[https://quick-chat-backend-umhq.onrender.com](https://quick-chat-backend-umhq.onrender.com)

----------

## Development Notes

-   **Port**: The server runs on port `8000` by default.
-   **Redis Dashboard**: Accessible at http://localhost:8001.

----------

## Contributions

Feel free to contribute by submitting issues or pull requests. Follow best practices for code quality and documentation.

