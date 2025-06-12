# Microservices Blog Application

This is a simple blog application built using a microservices architecture. It is designed to demonstrate how different services can work together in a decoupled and scalable way.

## Overview

The application consists of two main services:

1. **Posts Service**
2. **Comments Service**

![image](https://github.com/user-attachments/assets/4c42dcb2-2f6d-4756-b103-ff12cdb68e3f)

Each service is self-contained and communicates through RESTful APIs. This modular structure allows for easier maintenance, testing, and future scalability.

---

## Architecture

### Posts Service

Responsible for creating and retrieving blog posts.

#### Endpoints:
- `POST /posts`  
  Creates a new blog post.

- `GET /posts`  
  Retrieves all blog posts.

![image](https://github.com/user-attachments/assets/dabb236d-1402-468b-9677-c2b9970ef118)

#### Functionality:
- Stores posts in an in-memory data structure (can be replaced with a persistent DB).
- Each post has a unique ID and a title.
- Returns a list of all posts, including nested comments (fetched from the Comments service).

---

### Comments Service

Handles creation and retrieval of comments associated with posts.

#### Endpoints:
- `POST /posts/:id/comments`  
  Adds a new comment to the post with the given ID.

- `GET /posts/:id/comments`  
  Retrieves all comments associated with the given post ID.

#### Functionality:
- Stores comments in an in-memory structure keyed by post ID.
- Each comment has an ID, content, and reference to a post ID.

![image](https://github.com/user-attachments/assets/90997591-9d47-468d-8129-39616e589e0f)

---

## Tech Stack

- **Reactjs**,**Node.js** with **Express.js**
- **Docker** (optional, for containerization)
- **Axios** (for inter-service communication)

---

## Running the Application

### Prerequisites
- Node.js (v14+)
- npm or yarn

### Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/kushagra1934/blog.git
   cd blog


