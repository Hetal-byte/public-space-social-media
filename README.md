Public Space Social Media Platform - Complete Documentation
Project Overview
A comprehensive Node.js-based social media application that implements a unique friend-based posting limitation system. The platform encourages social connections by restricting posting capabilities based on the number of friends a user has.

Core Features
User Authentication System
Registration: New user signup with username, email, and password

Login: Secure authentication using JWT tokens

Session Management: Token-based authentication with 24-hour expiration

Password Security: bcryptjs hashing for secure password storage

Social Networking Capabilities
Friend System: Add friends using email addresses

Friend Validation: Prevents duplicate friendships and self-friending

Social Metrics: Real-time friend count tracking

Network Growth: Encourages user engagement through friend connections

Dynamic Posting System
The platform's unique feature is its friend-based posting restrictions:

0 friends: Cannot create any posts

1 friend: Limited to 1 post per day

2-9 friends: Limited to 2 posts per day

10+ friends: Unlimited posting privileges

Post Management
Content Creation: Text-based posts with optional media attachments

Media Support:

Images: JPEG, JPG, PNG, GIF formats

Videos: MP4, MOV, AVI, MKV formats

File Size: 50MB maximum per upload

Post Interactions:

Like/unlike functionality

Comment system

Share counter with tracking

Real-time Updates: Instant engagement metrics

Technical Architecture
Backend Technology Stack
Framework: Express.js for robust web application structure

Security:

CORS configuration for secure cross-origin requests

JWT authentication for session management

bcryptjs for password encryption

File Handling:

Multer middleware for file upload processing

File system operations for media management

Request Processing: Body-parser for handling various request formats

Frontend Implementation
Core Technologies:

Vanilla JavaScript for client-side functionality

HTML5 semantic structure

CSS3 with modern styling approaches

Design Features:

Responsive layout for mobile compatibility

Gradient backgrounds and modern UI elements

Interactive user interface components

Data Management
Currently implements in-memory storage for:

User account information and credentials

Post content, metadata, and engagement data

Friend relationship mappings

Session management data

Note: Production deployment should integrate a persistent database solution

Installation and Setup
Prerequisites Installation

npm install
Required Dependencies
The application automatically installs these packages:

Production Dependencies:

bcryptjs ^2.4.3 - Password hashing and security

body-parser ^1.20.3 - Request parsing middleware

cors ^2.8.5 - Cross-origin resource sharing

express ^4.21.2 - Web application framework

jsonwebtoken ^9.0.2 - JWT token management

multer ^1.4.5-lts.1 - File upload handling

Development Dependencies:

nodemon ^3.0.1 - Development server with auto-restart

Server Configuration
Development Environment:

npm run dev
Production Environment:

npm start
Access Points:

Local development: http://localhost:3000

Network access: http://0.0.0.0:3000

API Documentation
Authentication Endpoints
User Registration

Endpoint: POST /api/register

Purpose: Create new user accounts

Required Fields: username, email, password

Returns: JWT token and user information

User Login

Endpoint: POST /api/login

Purpose: Authenticate existing users

Required Fields: email, password

Returns: JWT token and session data

User Management
User Information Retrieval

Endpoint: GET /api/user/info

Purpose: Get comprehensive user statistics

Authentication: Required

Returns: Friend count, daily post limits, posting eligibility

Friend Management

Endpoint: POST /api/friends/add

Purpose: Add new friends by email

Authentication: Required

Validation: Prevents duplicate and self-friendships

Post Management System
Post Creation

Endpoint: POST /api/posts

Purpose: Create new posts with optional media

Authentication: Required

Features: Content validation, posting limit enforcement

File Support: Images and videos with size restrictions

Post Retrieval

Endpoint: GET /api/posts

Purpose: Fetch all posts with engagement data

Authentication: Required

Returns: Posts with like status and interaction counts

Post Interaction Endpoints
Like Management

Endpoint: POST /api/posts/:postId/like

Purpose: Toggle like status on posts

Returns: Updated like count and status

Comment System

Endpoint: POST /api/posts/:postId/comment

Purpose: Add comments to posts

Validation: Comment content required

Returns: Comment data with user information

Share Functionality

Endpoint: POST /api/posts/:postId/share

Purpose: Increment share counter

Returns: Updated share count

File Structure and Organization
text
project-root/
├── server.js          # Main application server and API endpoints
├── index.html         # Frontend HTML structure and layout
├── script.js          # Client-side JavaScript functionality
├── style.css          # Responsive CSS styling and design
├── package.json       # Project configuration and dependencies
├── package-lock.json  # Dependency version locking
└── uploads/           # Media file storage directory
Configuration Details
Default Application Settings
Server Port: 3000 (configurable via PORT environment variable)

JWT Secret: 'your-secret-key-change-this-in-production' (Change for production)

Upload Directory: './uploads'

File Size Limit: 50MB maximum

Supported Formats: Images (JPEG, JPG, PNG, GIF) and Videos (MP4, MOV, AVI, MKV)

Security Implementation
Password Protection: bcrypt hashing before database storage

Session Security: JWT token authentication for protected routes

File Validation: Strict file type and size checking

CORS Protection: Configured for secure cross-origin requests

Request Limiting: Size limits to prevent abuse and attacks

Storage Architecture
The application currently uses in-memory storage for rapid development and testing:

User Data: Account credentials and profile information

Post Content: Text, media URLs, and engagement metrics

Social Connections: Friend relationships and network data

Session Data: Active user sessions and authentication tokens

Production Recommendation: Implement a robust database solution such as PostgreSQL or MongoDB for persistent data storage.

Browser Compatibility
The application supports modern web browsers with:

JavaScript: ES6+ features and syntax

Network: Fetch API for HTTP requests

File Handling: FormData for media uploads

Storage: Local storage for client-side data persistence

Responsive Design: Mobile-first approach with flexible layouts

Development Notes
This social media platform demonstrates modern web development practices while implementing a unique gamification approach to social networking. The friend-based posting system encourages users to build meaningful connections before gaining full platform privileges, potentially reducing spam and promoting quality interactions.

The current implementation serves as a solid foundation for a production-ready social media application, with clear upgrade paths for database integration, advanced security features, and scalability improvements.
