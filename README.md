House Rental Project Documentation
Project Overview
The House Rental Project is a web-based platform designed to facilitate the rental of various types of properties (houses, apartments, etc.). The platform allows both owners and brokers to post, edit, and manage property listings. The admin has full control over the platform, including the ability to edit properties. Users can sign up, log in, and manage their property listings, and the platform provides essential features like authentication, authorization, and security.

Key Features
1. User Roles
Owner: Users who own properties and want to rent them out. They can post properties and manage their listings.
Broker: Users who facilitate property rentals on behalf of property owners. Brokers can post and manage properties on behalf of their clients.
Admin: A privileged user who has full control over the platform. The admin can manage users, edit or delete properties, and oversee the entire platform.
2. Authentication & Authorization
The project implements Spring Security for user authentication and authorization. The following features are supported:

User Authentication: Users are required to log in using their credentials (username and password).
User Roles: Depending on the user's role (Owner, Broker, Admin), different permissions are granted. For example, only admins can edit other users' properties.
JWT Token: The platform uses JSON Web Tokens (JWT) to manage user sessions and securely transmit information between the client and server.
Password Reset: A "forgot password" feature is available, allowing users to reset their password through a secure process.
3. Property Management
Post Property: Users (owners and brokers) can create new property listings by providing details like title, description, price, location, and media (images).
Edit Property: Admin users can edit any property listed on the platform. Owners and brokers can only edit their own properties.
Property Details: The platform supports detailed property information, including price, description, location, and media (images).
Search & Filters: Users can search and filter properties based on various criteria such as price range, location, and property type.
4. Security Features
CORS (Cross-Origin Resource Sharing): The platform supports CORS to allow communication between different domains (frontend on port 3000 and backend on port 8090).
JWT Authentication: The authentication system uses JWT tokens to secure API endpoints. Users need to log in to get a JWT token, which is then used to authorize access to protected routes.
Session Management: Once authenticated, the user's session is managed through JWT tokens. The frontend sends this token in the authorization header for every request.
5. Forgot Password and Reset
Users can reset their passwords through an email-based process:

The user requests a password reset.
A reset link is sent to the user's email address.
Upon clicking the link, the user is prompted to set a new password.
6. Frontend & Backend Integration
The frontend is built using React, where users can interact with the platform to post properties, view listings, and manage their accounts.
The backend is implemented with Spring Boot, which handles business logic, security, and data management.
API Endpoints: The platform exposes RESTful API endpoints for managing properties, users, and authentication.
File Upload: The frontend allows users to upload property images. The backend handles the file storage and associates the images with the respective property listing.
7. File Upload
Users can upload media (images) while posting or editing properties. These files are stored on the server and linked to the property listings.
The system supports a maximum file size of 5MB and only allows image files (JPG, PNG, etc.).
8. Admin Panel
Admin Dashboard: Admins can view a list of all users and their properties.
User Management: Admins can edit user details, change roles, or deactivate accounts.
Property Management: Admins can manage any property listing, regardless of the owner or broker.
9. Localization (i18n)
The platform supports multiple languages (English, French, Kinyarwanda) for a broader audience. Users can switch languages for an enhanced experience.

Technical Details
1. Frontend (React)
React.js: The frontend is built with React to create a dynamic, interactive UI.
Formik: Used for handling forms and form validation.
Yup: Used for validating form input values.
React Dropzone: A library for handling file uploads (images).
Axios: Used for making HTTP requests to the backend API.
2. Backend (Spring Boot)
Spring Boot: A Java framework for building RESTful APIs.
Spring Security: For implementing authentication and authorization.
JWT: For secure token-based authentication.
Postgres: Database to store user and property data.
Spring Data JPA: For database interactions.
3. CORS Configuration
The backend allows cross-origin requests from specific frontend domains to ensure smooth communication between the client (React) and server (Spring Boot).

4. API Endpoints
POST /api/property/post: Allows users to post a new property listing.
GET /api/property/{id}: Retrieves details of a specific property.
GET /api/property: Retrieves a list of all properties.
PUT /api/property/{id}: Allows the user to edit their property.
DELETE /api/property/{id}: Allows the user to delete their property.
