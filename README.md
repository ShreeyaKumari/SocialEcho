# SocialEcho

SocialEcho is a social networking platform where users can create accounts, join communities, create posts, and interact with other users.

This repository contains both the backend server and frontend client required to run the application locally.

---

## Project Overview

The project consists of two main parts:

- Backend server built with Node.js, Express, and MongoDB
- Frontend client built with React
- JWT-based authentication
- Community and post management features

---

## Project Structure
SocialEcho/
│
├── server/ Backend (Node.js + Express + MongoDB)
├── client/ Frontend (React)
└── README.md



---

## Prerequisites

Before running the project, ensure the following tools are installed:

- Node.js (version 18 recommended)
- npm (comes with Node.js)
- MongoDB (local installation or MongoDB Atlas)
- Git

Verify installation:
node -v
npm -v
git --version


---

## Step 1: Clone Repository

Open terminal or command prompt and run:

git clone https://github.com/ShreeyaKumari/SocialEcho.git




---

## Step 2: Install Backend Dependencies

Navigate to server folder:

cd server
npm install


This installs backend dependencies.

---

## Step 3: Backend Environment Setup

Create a `.env` file inside the `server` folder.

Example configuration:

PORT=4000
MONGODB_URI=mongodb://127.0.0.1:27017/db_socialecho
SECRET=your_access_secret
REFRESH_SECRET=your_refresh_secret


If using MongoDB Atlas, replace the MongoDB URI with your connection string.

---

## Step 4: Start Backend Server

Inside the server folder, run:

npm start


If successful, terminal shows:

Server up and running on port 4000
Connected to database


Keep this terminal open.

---

## Step 5: Install Frontend Dependencies

Open a new terminal and navigate to client folder:

cd SocialEcho/client
npm install


---

## Step 6: Frontend Environment Setup

Create `.env` file inside the client folder:

REACT_APP_API_URL=http://localhost:4000


This connects frontend to backend.

---

## Step 7: Start Frontend Application

Inside client folder:

npm start


The application will open automatically in browser:

http://localhost:3000


---

## Running the Project

Two terminals must be active:

Terminal 1 (Backend):
cd server
npm start


Terminal 2 (Frontend):
cd client
npm start


---

## Common Issues and Fixes

### Server shows "Server is down"
- Ensure backend server is running.
- Check MongoDB is running.
- Verify frontend `.env` API URL.

### Port already in use
Stop conflicting application or change port in `.env`.

### Dependencies missing
Run:
npm install

inside respective folder.

---

## Useful Commands

Install dependencies:
npm install


Run backend:
npm start


Run frontend:
npm start


Build frontend for production:
npm run build


---

## Development Workflow

Typical development steps:

git pull
git checkout -b feature-name
make changes
git add .
git commit -m "description"
git push


Then open a pull request.

---

## Contribution Guidelines

1. Pull latest code.
2. Create a new branch.
3. Implement changes.
4. Commit changes with clear messages.
5. Push branch and create pull request.

---

## License

This project is created for academic and learning purposes.

---

## Notes

- Backend runs on port 4000 by default.
- Frontend runs on port 3000 by default.
- MongoDB must be running before starting backend.
- Environment files (.env) should not be committed to version control.

---

End of documentation.


















---------------------------------------------------------------------------
# SocialEcho

A social networking platform with automated content moderation and context-based authentication system.

[Watch Demo](https://youtu.be/Tmncayg7FeU)

![UI-community](https://raw.githubusercontent.com/nz-m/SocialEcho/main/resources/UI-community.png)

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies](#technologies)
- [Schema Diagram](#schema-diagram)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [License](#license)

## Project Overview

The project is a social networking platform built using the MERN (MongoDB, Express.js, React.js, Node.js) stack. It incorporates two major features: an automated content moderation system and context-based authentication. These features are accompanied by common functionalities found in social media applications, such as profile creation, post creation and sharing, liking and commenting on posts, and following/unfollowing users.

### Automated Content Moderation

The platform's automated content moderation system utilizes various NLP (Natural Language Processing) APIs. These APIs include:

- Perspective API: Used for filtering spam, profanity, toxicity, harassment etc.
- TextRazor API: Integrated for content categorization.
- Hugging Face Interface API: Utilized with BART Large MNLI for content categorization.

A Flask application has been developed to provide similar functionality as the Hugging Face Interface API's classifier. The Flask app utilizes the BART Large MNLI model. It operates as a zero-shot classification pipeline with a PyTorch framework.

The system allows flexibility in choosing different services for API usage or disabling them without affecting overall functionality by using a common interface for interacting with the APIs.

When a user posts content, it undergoes a thorough filtering process to ensure compliance with the community guidelines. Additionally, users have the ability to report posts that they find inappropriate, which triggers a manual review process.

### Context-Based Authentication

The platform implements context-based authentication to enhance user account security. It takes into consideration user location, IP address, and device information for authentication purposes. Users can conveniently manage their devices directly from the platform. To ensure data privacy, this information is encrypted using the AES algorithm and securely stored in the database.

In case of a suspicious login attempt, users are promptly notified via email and are required to confirm their identity to protect against unauthorized access.

### User Roles

There are three distinct user roles within the system:

1. Admin: The admin role manages the overall system, including moderator management, community management, content moderation, monitoring user activity, and more.
2. Moderators: Moderators manage communities, manually review reported posts, and perform other moderation-related tasks.
3. General Users: General users have the ability to make posts, like comments, and perform other actions within the platform.



## Features

- [x] User authentication and authorization (JWT)
- [x] User profile creation and management
- [x] Post creation and management
- [x] Commenting on posts
- [x] Liking posts and comments
- [x] Following/unfollowing users
- [x] Reporting posts
- [x] Content moderation
- [x] Context-based authentication
- [x] Device management
- [x] Admin dashboard
- [x] Moderator dashboard
- [x] Email notifications


## Technologies

- React.js
- Redux
- Node.js
- Express.js
- MongoDB
- Tailwind CSS
- JWT Authentication
- Passport.js
- Nodemailer
- Crypto-js
- Azure Blob Storage
- Flask
- Hugging Face Transformers


## Schema Diagram

![Schema Diagram](https://raw.githubusercontent.com/nz-m/SocialEcho/main/resources/Schema-Diagram.png)



## Getting Started

### Prerequisites

Before running the application, make sure you have the following installed:

- Node.js
- MongoDB or MongoDB Atlas account

### Installation

1. Clone the repository

```bash
git clone https://github.com/nz-m/SocialEcho.git
```
2. Go to the project directory and install dependencies for both the client and server

```bash
cd client
npm install
```

```bash
cd server
npm install
```

3. Create a `.env` file in both the `client` and `server` directories and add the environment variables as shown in the `.env.example` files.
4. Start the server

```bash
cd server
npm start
```

5. Start the client

```bash
cd client
npm start
```


### Configuration

Run the `admin_tool.sh` script from the server directory with permissions for executing the script. This script is used for configuring the admin account, creating the initial communities, and other settings.
```bash
./admin_tool.sh
``` 

#### `.env` Variables

For email service of context-based authentication, the following variables are required:

```bash
EMAIL=
PASSWORD=
EMAIL_SERVICE=
```

For content moderation, you need the `PERSPECTIVE_API_KEY` and either the `INTERFACE_API_KEY` or `TEXTRAZOR_API_KEY`. Visit the following links to obtain the API keys:

- [Perspective API](https://developers.perspectiveapi.com/s/docs-get-started)
- [TextRazor API](https://www.textrazor.com/)
- [Hugging Face Interface API](https://huggingface.co/facebook/bart-large-mnli)

If you prefer, the Flask server can be run locally as an alternative to using the Hugging Face Interface API or TextRazor API. Refer to the `classifier_server` directory for more information.


>**Note:** Configuration for context-based authentication and content moderation features are **_not mandatory_** to run the application. However, these features will not be available if the configuration is not provided.


## Usage

### Admin

The admin dashboard can be accessed at the `/admin` route. Use the `admin_tool.sh` script to configure the admin account. The admin account can be used to manage moderators, communities, and perform other admin-related tasks. You can also enable/disable or switch API services using the admin dashboard.

### Moderator

Moderators have specific email domain (`@mod.socialecho.com`). When registering with an email from this domain, the user is automatically assigned the moderator role. Moderators can be assigned to different communities from the admin dashboard.

#### Demo
https://youtu.be/Tmncayg7FeU

## License

This project is licensed under the [MIT License](https://github.com/nz-m/SocialEcho/blob/main/LICENSE).

