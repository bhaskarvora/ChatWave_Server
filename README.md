
----------

Hii, I am **Bhaskar Vora** 
I am a self motivated and versatile individual, always eager to take on new challenges. With a passion for learning I am dedicated to delivering high-quality results. With a positive attitude and a growth mindset, I am ready to make a meaningful contribution and achieve great things.

# ChatWave Web Application

**ChatWave** is a modern chat application that enables real-time messaging between users. It offers features for user authentication, chat rooms, private messaging, and administrative controls for managing users and messages. This application provides a seamless user experience with modern design and real-time updates.

# Features

-   **User Authentication**: Secure login and registration with JWT-based authentication.
-   **Real-Time Chat**: Real-time messaging in both individual and group chats.
-   **User Management**: Admins can manage user accounts and chat history.
-   **Group Management**: Users can create and manage group chats.
-   **Message Management**: View, delete, and manage chat messages.
-   **Responsive Design**: Optimized for both desktop and mobile use.


### Server-Side Architecture Overview

#### 1. Environment Configuration (.env File)

-   Purpose: Contains sensitive configuration and credentials.
    
-   Contents:
    

-   MONGO_URI: MongoDB connection string.
    
-   JWT_SECRET: Secret key for JWT token signing.
    
-   ADMIN_SECRET_KEY: Key for admin-related operations.
    
-   NODE_ENV: Environment mode (e.g., DEVELOPMENT, PRODUCTION).
    
-   CLIENT_URL: URL for the frontend application.
    
-   CLOUDINARY_CLOUD_NAME, CLOUDINARY_API_KEY, CLOUDINARY_API_SECRET: Credentials for Cloudinary file uploads.
    

#### 2. Server Setup (app.js)

-   Imports and Configuration:
    

-   Dependencies: Imports libraries and middleware such as Express, Socket.IO, dotenv, and Cloudinary.
    
-   Environment Configuration: Loads environment variables from the .env file.
    
-   Database and Cloudinary: Configures connections to MongoDB and Cloudinary.
    

-   Express Server:
    

-   Initialization: Sets up the Express application and HTTP server.
    
-   Middleware:
    

-   express.json(): Parses JSON requests.
    
-   cookieParser(): Parses cookies from requests.
    
-   cors(): Handles Cross-Origin Resource Sharing (CORS).
    

-   Routes:
    

-   User Routes: userRoute for user-related operations.
    
-   Chat Routes: chatRoute for chat and message operations.
    
-   Admin Routes: adminRoute for admin-specific operations.
    

-   Socket.IO Integration:
    

-   Configuration: Sets up Socket.IO with CORS options.
    
-   Middleware: Uses cookieParser for authentication.
    
-   Event Handlers:
    

-   NEW_MESSAGE: Handles new messages in real-time.
    
-   START_TYPING and STOP_TYPING: Handles typing indicators.
    
-   CHAT_JOINED and CHAT_LEAVED: Manages user presence in chats.
    

-   User Management:
    

-   Online Users: Tracks and updates the list of online users.
    

-   Error Handling:
    

-   Uses errorMiddleware to handle application errors.
    

-   Server Listening:
    

-   Starts the server on the specified port and logs the environment mode.
    

#### 3. Utility Functions (utils/features.js and utils/utility.js)

-   connectDB: Connects to MongoDB using Mongoose.
    
-   sendToken: Generates and sends a JWT token in a cookie.
    
-   emitEvent: Emits real-time events via Socket.IO.
    
-   uploadFilesToCloudinary: Uploads files to Cloudinary.
    
-   deletFilesFromCloudinary: Placeholder for deleting files from Cloudinary.
    
-   ErrorHandler: Custom error class for consistent error handling.
    

#### 4. Routes

-   routes/admin.js:
    

-   Admin Routes: Handles admin-specific operations (login, logout, viewing stats, etc.).
    
-   Middleware: Protects routes using adminOnly middleware.
    

-   routes/chat.js:
    

-   Chat Routes: Manages chat-related operations (creating groups, sending messages, etc.).
    
-   Middleware: Protects routes using isAuthenticated middleware.
    

-   routes/user.js:
    

-   User Routes: Handles user operations (registration, login, friend requests, etc.).
    
-   Middleware: Protects routes using isAuthenticated middleware.
    

#### 5. Seeders (seeders/chat.js and seeders/user.js)

-   createUser: Generates fake user data.
    
-   createSingleChats: Creates single chats between pairs of users.
    
-   createGroupChats: Creates group chats with multiple users.
    
-   createMessages: Generates random messages in various chats.
    
-   createMessagesInAChat: Generates messages for a specific chat.
    

#### 6. Constants and Helpers

-   constants/events.js: Defines event constants used in Socket.IO.
    
-   lib/helper.js: Contains helper functions like getBase64 and getSockets.
    

### Summary

Your server-side code handles the following:

-   Environment Setup: Manages configurations and credentials.
    
-   Server Configuration: Sets up Express, Socket.IO, and integrates Cloudinary.
    
-   Real-Time Communication: Handles real-time chat events using Socket.IO.
    
-   Database Operations: Connects to MongoDB and manages data.
    
-   Error Handling: Consistent error management with custom middleware.
    
-   User and Chat Management: Routes for user interactions, chat management, and admin operations.
    

Feel free to ask if you need more details or help with specific aspects of your server setup!


## Install Dependencies

 `npm install` 

  

## Environment Variables

Before running the project, you need to set up the environment variables. 

 `mv .sampleEnv .env`
  `npm start` 
   
. Replace the placeholder values with your actual credentials.

Example:

CLOUDINARY_CLOUD_NAME= YOURCLOUDINARY_CLOUD_NAME
CLOUDINARY_API_KEY = YOURCLOUDINARY_API_KEY
CLOUDINARY_API_SECRET =  YOURCLOUDINARY_API_SECRET



## Application Images

![Screenshot 2024-08-30 164057](https://github.com/user-attachments/assets/e0579ee0-2b24-4c8f-acdc-0b17095d5729)
ChatWave Realtime Chat Application

![Screenshot 2024-08-30 164128](https://github.com/user-attachments/assets/2281e172-a620-4c23-aee6-35e4f09895fe)
Messaging Example We can share any image, audio, video or files

![Screenshot 2024-08-30 164148](https://github.com/user-attachments/assets/648cf0d9-18f2-4ed7-a341-9b3d60beef0f)
Create New Group 

![Screenshot 2024-08-30 164444](https://github.com/user-attachments/assets/dd093ce7-d12c-412a-9114-8b64445e7dab)
Group Details

![Screenshot 2024-08-30 164520](https://github.com/user-attachments/assets/4680c606-73de-4643-b402-febb37d6b134)
ChatWave Dashboard Showing Statistics using Line Chart

![Screenshot 2024-08-30 165130](https://github.com/user-attachments/assets/50f26c76-6387-475a-9521-0a9c6705d557)
ChatWave Dashboard Showing Statistics of Last Messages

![Screenshot 2024-08-30 165158](https://github.com/user-attachments/assets/23260062-483e-4962-b6dd-1fe85854dbb0)
ChatWave Dashboard Showing All Users

![Screenshot 2024-08-30 165212](https://github.com/user-attachments/assets/dcaf544c-6cf5-4818-9fd4-d1ebbd5d3f72)












