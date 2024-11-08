Mental Health Tracker

This project is a web application that allows users to log their daily mental health status and visualize their weekly/monthly trends. The application uses Google OAuth for user authentication and includes both frontend and backend components. The backend is built with Node.js and Express, and the frontend is built with React. Data is stored in an SQLite database, and the entire application is Dockerized for easy setup and deployment.

Prerequisites

Docker and Docker Compose installed on your machine.
Google account for OAuth configuration.
Getting Started

Google Client Configuration

1. Go to the Google Cloud Console.

2. Create a new project or select an existing project.

3. Navigate to the "APIs & Services" > "Credentials" page.

4. Click "Create Credentials" and choose "OAuth 2.0 Client IDs".

5. Set the application type to "Web application".

6. Add authorized redirect URIs (e.g., http://localhost:5000/auth/google/callback).

7. After creating the credentials, you will get a Client ID and Client Secret.

8. Create a .env file in the backend directory and add the following: GOOGLE_CLIENT_ID=

GOOGLE_CLIENT_SECRET=

9. Generate a session secret key for your application. You can use an online generator or Node.js to create a random string and add it to the .env file: node -e "console.log(require('crypto').randomBytes(32).toString('hex'));" SESSION_SECRET=

PORT = 5000

Docker Setup

10. Clone the repository: git close Go to the root directory
Build and start the Docker containers: docker-compose up --build
The above command should install all required dependecies and start your server at http://localhost:3000

Note: Do create and add ".env" file under /backend and add all above mentioned key value pairs for the application to run successfully. Git prevents pushing files with Secret keys likes Google ClientID, Google Secret, therefore I have not included the .env file in the repository.
