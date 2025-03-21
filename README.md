# webdev-A2
Submission point for A2 web dev. Due March 21, 2025.

For this project, I used Node.js and MongoDB to create a backend for a social media app. This setup allows a user to register with the app, login with their registration details, see all of the posts on the app (though this is also publicly available), create posts of their own, and edit and delete these posts. Authentication is required for creating, deleting, and updating posts in order to keep users' data safe. To set this up, download and open the zip file with all of the code inside, install the required packages (express nodemon mongoose dotenv body-parser joi bcryptjs jsonwebtoken), ensure the .env file includes the correct DB_CONNECTOR and TOKEN_SECRET variables connected to the MongoDB database, and type npm start in the terminal to start the server running. The app should then run on http://localhost:3000, and this can be accessed through postman. The following are all of the API endpoints:

POST /register: Register a new user with the app
  - requires a name, email, and password that follow email protocol guidelines and password length requirements (6-1024 characters)

POST /login: Login with an existing user
  - requires the user's email and password, returns an auth-token to be used to verify user's identity for creating, editing, and deleting posts

POST /posts: Create a new post (authentication required)
  - requires a title, description, and like count (default 0) for the post

GET /posts: Get all posts (public)
  - returns all posts on the app

GET /posts/:id: Get a single post by ID (public)
  - returns details of any post based on id

PATCH /posts/:id: Update a post (authentication required, only the creator can update)
  - need to update title, description, and/or like count
    
DELETE /posts/:id: Delete a post (authentication required, only the creator can delete)



