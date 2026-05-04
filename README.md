# Poster App

A simple social media posting application built with Node.js and a custom web framework called "Butter".

## Overview

Poster is a lightweight web application that allows users to:
- Create an account and log in
- View posts from other users
- Create new posts
- Update their profile information
- Log out securely

## Features

- **Authentication System**: Token-based authentication with secure session management
- **User Management**: Create, read, and update user profiles
- **Posting System**: Create and view posts with author information
- **Custom Framework**: Built on top of a custom Node.js web framework called "Butter"
- **Responsive Frontend**: Clean, modern UI with vanilla JavaScript

## Architecture

### Backend
- **Custom Framework**: Butter - A lightweight Express-like web framework built with Node.js
- **Authentication**: Token-based sessions stored in memory
- **Data Storage**: In-memory arrays for users, posts, and sessions
- **Middleware**: Custom middleware for authentication, JSON parsing, and routing

### Frontend
- **Single Page Application**: Vanilla JavaScript with client-side routing
- **Responsive Design**: Modern CSS with mobile-friendly layout
- **Dynamic Content**: Dynamic DOM manipulation for posts and user interactions

## Project Structure

```
poster-app/
├── server.js          # Main application server
├── butter.js          # Custom web framework
├── public/            # Static files
│   ├── index.html     # Main HTML template
│   ├── styles.css     # Application styles
│   └── scripts.js     # Client-side JavaScript
└── README.md          # This file
```

## API Endpoints

### Authentication
- `POST /api/login` - User login
- `DELETE /api/logout` - User logout

### User Management
- `GET /api/user` - Get current user information
- `PUT /api/user` - Update user profile

### Posts
- `GET /api/posts` - Get all posts with author information
- `POST /api/posts` - Create a new post (requires authentication)

### Static Files
- `GET /styles.css` - CSS stylesheet
- `GET /scripts.js` - Client-side JavaScript
- `GET /` - Main application (serves index.html)

## Getting Started

### Prerequisites
- Node.js (version 14 or higher)
- npm (usually comes with Node.js)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/vasylpryimakdev/node-js-poster.git
cd node-js-poster
```

2. Start the application:
```bash
node server.js
```

3. Open your browser and navigate to:
```
http://localhost:8000
```

## Default Users

The application comes with pre-configured test users:

| Username | Password | Name |
|----------|----------|------|
| liam23 | string | Liam Brown |
| merit.sky | string | Meredith Green |
| ben.poet | string | Ben Adams |

## Technical Details

### Butter Framework Features
- **Routing**: Simple route registration with HTTP methods
- **Middleware**: BeforeEach middleware for cross-cutting concerns
- **Response Helpers**: Built-in methods for JSON, file serving, and status codes
- **Request Parsing**: Automatic JSON body parsing

### Security Features
- Token-based authentication
- Secure cookie handling
- Route protection with middleware
- Session management

### Data Models

#### User
```javascript
{
  id: Number,
  name: String,
  username: String,
  password: String
}
```

#### Post
```javascript
{
  id: Number,
  title: String,
  body: String,
  userId: Number,
  author: String (populated from user data)
}
```

#### Session
```javascript
{
  userId: Number,
  token: String
}
```

## Development Notes

- The application uses in-memory storage, so data is lost when the server restarts
- Passwords are stored in plain text (for demonstration purposes only)
- The Butter framework is a simplified version of Express.js for educational purposes
- The frontend is a single-page application with client-side routing

## Future Improvements

- Persistent data storage (database integration)
- Password hashing and security improvements
- Error handling and validation
- Test coverage
- Docker containerization
- Production deployment configuration
