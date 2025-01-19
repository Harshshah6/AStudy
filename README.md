# AStudy API Documentation

## Routes

### Schedule Routes

- **GET /schedule/all**
  - Fetch all schedules.
  - **Response:**
    ```json
    {
      "status": true,
      "schedules": [
        {
          "title": "Meeting",
          "description": "Project meeting",
          "timestamp": "2023-10-01T10:00:00Z",
          "start": "2023-10-01T10:00:00Z",
          "stop": "2023-10-01T11:00:00Z",
          "background": "blue"
        }
      ]
    }
    ```

- **POST /schedule/add**
  - Add a new schedule.
  - **Request Body:**
    ```json
    {
      "title": "Meeting",
      "description": "Project meeting",
      "timestamp": "2023-10-01T10:00:00Z",
      "start": "2023-10-01T10:00:00Z",
      "stop": "2023-10-01T11:00:00Z",
      "background": "blue"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "Schedule added successfully",
      "event": {
        "title": "Meeting",
        "description": "Project meeting",
        "timestamp": "2023-10-01T10:00:00Z",
        "start": "2023-10-01T10:00:00Z",
        "stop": "2023-10-01T11:00:00Z",
        "background": "blue"
      }
    }
    ```

### Posts Routes

- **GET /posts/all**
  - Fetch all posts.
  - **Response:**
    ```json
    {
      "status": true,
      "posts": [
        {
          "title": "First Post",
          "content": "This is the content of the first post.",
          "photos": ["photo1.jpg"],
          "uid": "user123"
        }
      ]
    }
    ```

- **POST /posts/add**
  - Add a new post.
  - **Request Body:**
    ```json
    {
      "title": "First Post",
      "content": "This is the content of the first post.",
      "photos": ["photo1.jpg"],
      "uid": "user123"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "Post added successfully",
      "post": {
        "title": "First Post",
        "content": "This is the content of the first post.",
        "photos": ["photo1.jpg"],
        "uid": "user123"
      }
    }
    ```

- **GET /posts/:id**
  - Fetch a post by ID.
  - **Response:**
    ```json
    {
      "status": true,
      "post": {
        "title": "First Post",
        "content": "This is the content of the first post.",
        "photos": ["photo1.jpg"],
        "uid": "user123"
      }
    }
    ```

- **POST /posts/update/:pid**
  - Update a post by ID.
  - **Request Body:**
    ```json
    {
      "title": "Updated Post",
      "content": "This is the updated content.",
      "photos": ["photo2.jpg"],
      "uid": "user123"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "Post updated successfully",
      "post": {
        "title": "Updated Post",
        "content": "This is the updated content.",
        "photos": ["photo2.jpg"],
        "uid": "user123"
      }
    }
    ```

- **DELETE /posts/delete/:pid**
  - Delete a post by ID.
  - **Request Body:**
    ```json
    {
      "uid": "user123"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "Post deleted successfully"
    }
    ```

- **POST /posts/:pid/postcomment/**
  - Add a comment to a post.
  - **Request Body:**
    ```json
    {
      "uid": "user123",
      "content": "This is a comment."
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "Comment added successfully"
    }
    ```

### Events Routes

- **GET /events/all**
  - Fetch all events.
  - **Response:**
    ```json
    {
      "status": true,
      "events": [
        {
          "title": "Conference",
          "description": "Tech conference",
          "thumbnail": "thumbnail.jpg",
          "date": "2023-10-01T10:00:00Z"
        }
      ]
    }
    ```

- **POST /events/add**
  - Add a new event.
  - **Request Body:**
    ```json
    {
      "title": "Conference",
      "description": "Tech conference",
      "thumbnail": "thumbnail.jpg"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "Event added successfully",
      "event": {
        "title": "Conference",
        "description": "Tech conference",
        "thumbnail": "thumbnail.jpg",
        "date": "2023-10-01T10:00:00Z"
      }
    }
    ```

### Chats Routes

- **GET /chats/all**
  - Fetch all chats.
  - **Response:**
    ```json
    {
      "status": true,
      "chats": [
        {
          "from": "user123",
          "to": "user456",
          "content": "Hello!",
          "timestamp": "2023-10-01T10:00:00Z",
          "attachments": ["file1.jpg"]
        }
      ]
    }
    ```

- **POST /chats/add**
  - Add a new chat.
  - **Request Body:**
    ```json
    {
      "to": "user456",
      "content": "Hello!",
      "attachments": ["file1.jpg"],
      "uid": "user123"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "Chat added successfully",
      "chat": {
        "from": "user123",
        "to": "user456",
        "content": "Hello!",
        "timestamp": "2023-10-01T10:00:00Z",
        "attachments": ["file1.jpg"]
      }
    }
    ```

- **GET /chats/:cid**
  - Fetch a chat by ID.
  - **Response:**
    ```json
    {
      "status": true,
      "chat": {
        "from": "user123",
        "to": "user456",
        "content": "Hello!",
        "timestamp": "2023-10-01T10:00:00Z",
        "attachments": ["file1.jpg"]
      }
    }
    ```

- **POST /chats/update/:cid**
  - Update a chat by ID.
  - **Request Body:**
    ```json
    {
      "content": "Updated content",
      "attachments": ["file2.jpg"],
      "uid": "user123"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "Chat updated successfully",
      "chat": {
        "from": "user123",
        "to": "user456",
        "content": "Updated content",
        "timestamp": "2023-10-01T10:00:00Z",
        "attachments": ["file2.jpg"]
      }
    }
    ```

- **DELETE /chats/delete/:cid**
  - Delete a chat by ID.
  - **Request Body:**
    ```json
    {
      "uid": "user123"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "Chat deleted successfully"
    }
    ```

### Auth Routes

- **POST /auth/upload**
  - Upload a profile picture.
  - **Request Body:**
    ```json
    {
      "file": "profile.jpg",
      "uid": "user123"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "Profile picture uploaded successfully",
      "user": {
        "uid": "user123",
        "profile_pic": "user123.jpg"
      }
    }
    ```

- **POST /auth/updateprofile**
  - Update user profile.
  - **Request Body:**
    ```json
    {
      "name": "John Doe",
      "dob": "1990-01-01",
      "region": "USA"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "User profile updated successfully",
      "user": {
        "uid": "user123",
        "name": "John Doe",
        "dob": "1990-01-01",
        "region": "USA"
      }
    }
    ```

- **POST /auth/register**
  - Register a new user.
  - **Request Body:**
    ```json
    {
      "gtoken": "some-google-token"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "User registered successfully",
      "user": {
        "uid": "user123",
        "name": "John Doe",
        "email": "john.doe@example.com",
        "dob": "1990-01-01",
        "region": "USA",
        "role": "user"
      }
    }
    ```

- **POST /auth/login**
  - Login a user.
  - **Request Body:**
    ```json
    {
      "gtoken": "some-google-token"
    }
    ```
  - **Response:**
    ```json
    {
      "status": true,
      "message": "User logged in successfully",
      "user": {
        "uid": "user123",
        "name": "John Doe",
        "email": "john.doe@example.com",
        "dob": "1990-01-01",
        "region": "USA",
        "role": "user"
      }
    }
    ```

- **GET /auth/profile**
  - Fetch user profile.
  - **Response:**
    ```json
    {
      "status": true,
      "user": {
        "uid": "user123",
        "name": "John Doe",
        "email": "john.doe@example.com",
        "dob": "1990-01-01",
        "region": "USA",
        "role": "user"
      }
    }
    ```

- **GET /auth/users**
  - Fetch all users.
  - **Response:**
    ```json
    {
      "status": true,
      "users": [
        {
          "uid": "user123",
          "name": "John Doe",
          "email": "john.doe@example.com",
          "dob": "1990-01-01",
          "region": "USA",
          "role": "user"
        }
      ]
    }
    ```

### API Routes

- **GET /api/image**
  - Fetch user profile image.
  - **Response:**
    - Image file
