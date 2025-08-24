# AirBnB Clone Project

## Overview
This project is a clone of the AirBnB web application. It is part of the Holberton School curriculum aimed at building a full-stack web application step-by-step.

## Project Goals
- To develop a complete web application from back-end to front-end.
- To implement a database storage solution using MySQL.
- To create a RESTful API for the application.
- To build a dynamic front-end using a modern framework.

## Tech Stack
- **Back-end:** Python, Django, MySQL
- **API:** RESTful API
- **Front-end:** HTML, CSS, JavaScript ( potentially a framework like React )
- **Deployment:** (e.g., using a platform like Heroku or AWS)
# AirBnB Clone Project

... [your existing overview text] ...

## Team Roles

This project involves the following key roles and responsibilities:

- **Project Manager (PM):** Oversees the project timeline, coordinates tasks between team members, and ensures project goals are met on schedule.

- **Backend Developer:** Responsible for developing the core application logic using Python and Flask. This includes creating RESTful API endpoints, user authentication, and server-side functionality.

- **Database Administrator (DBA):** Designs, implements, and maintains the MySQL database. Ensures data integrity, writes efficient queries, and manages database migrations.

- **Frontend Developer:** Builds the user interface with HTML, CSS, and JavaScript. Focuses on creating a responsive, intuitive, and visually appealing user experience that interacts with the backend API.

- **DevOps Engineer:** Manages deployment, continuous integration/continuous deployment (CI/CD) pipelines, and server infrastructure to ensure the application is reliably hosted and available.## Technology Stack

Below are the core technologies used in the Airbnb clone project, along with their purposes:

### 🧠 Backend Technologies
- **Python**: The primary programming language used for developing the application’s backend logic.
- **Django**: A high-level Python web framework that enables rapid development of secure and maintainable web applications. It handles URL routing, templating, ORM, and more.
- **Django ORM**: Django’s built-in Object-Relational Mapper used to interact with the database using Python code.

### 💾 Database
- **MySQL**: A relational database used to store user data, listings, reservations, and other persistent information.

### 🎨 Frontend Technologies
- **HTML/CSS**: Used to create and style the structure of the web application's user interface.
- **JavaScript**: Adds interactivity and dynamic features to the frontend.
- **Bootstrap**: A responsive CSS framework used for quick UI development with built-in components.

### 🌐 API Platform
- **Django REST Framework (DRF)**: Used to build RESTful APIs that enable communication between the frontend and backend.

### ☁️ Hosting & Deployment
- **Render / Heroku**: Cloud platforms used to host the Django application and database, making the app accessible online.
- **GitHub**: Used for version control and collaboration on the codebase.
## Database Design

This section outlines the core entities in the Airbnb clone project and how they relate to one another.

### 🧑 Users
Represents individuals who use the platform — either as guests or hosts.

**Key Fields:**
- `id`: Unique identifier for the user (Primary Key).
- `name`: Full name of the user.
- `email`: User's email address (must be unique).
- `password`: Hashed password for login authentication.
- `is_host`: Boolean indicating whether the user is a host.

**Relationships:**
- A user can list **multiple properties** (if `is_host` is `True`).
- A user can make **multiple bookings**.
- A user can leave **reviews**.

---

### 🏠 Properties
Represents the accommodations listed by hosts.

**Key Fields:**
- `id`: Unique identifier for the property.
- `owner_id`: Foreign key referencing the `Users` table.
- `title`: Title or name of the property.
- `location`: Address or city where the property is located.
- `price_per_night`: Cost to book per night.

**Relationships:**
- A property is owned by one **user** (host).
- A property can have multiple **bookings** and **reviews**.

---

### 📅 Bookings
Tracks when users reserve properties.

**Key Fields:**
- `id`: Unique identifier for the booking.
- `user_id`: Foreign key referencing the booking guest.
- `property_id`: Foreign key referencing the property booked.
- `check_in`: Start date of the booking.
- `check_out`: End date of the booking.

**Relationships:**
- Each booking is made by one **user** for one **property**.

---

### 💬 Reviews
Captures feedback left by guests after a stay.

**Key Fields:**
- `id`: Unique identifier for the review.
- `user_id`: Foreign key referencing the reviewer.
- `property_id`: Foreign key referencing the property reviewed.
- `rating`: Numeric score (e.g., 1–5).
- `comment`: Text feedback.

**Relationships:**
- A review is left by a **user** on a **property**.

---

### 💳 Payments
Stores payment transaction information for bookings.

**Key Fields:**
- `id`: Unique identifier for the payment.
- `booking_id`: Foreign key referencing the related booking.
- `amount`: Total amount paid.
- `payment_method`: Method used (e.g., card, PayPal).
- `status`: Status of the transaction (e.g., successful, failed).

**Relationships:**
- Each payment is tied to a single **booking**.
## Feature Breakdown

This section outlines the key features of the Airbnb Clone project and their purpose in the system.

### 👤 User Management
Users can sign up, log in, and manage their profiles. Authentication and authorization ensure that users can only access and modify their own data. The system also distinguishes between regular users (guests) and hosts.

### 🏠 Property Management
Hosts can create, update, and delete property listings. Each listing includes details like title, description, price per night, location, and images. This feature is essential for enabling hosts to share accommodations.

### 📅 Booking System
Guests can view property availability and make bookings for specific dates. The system handles booking validation (e.g., preventing overlapping bookings) and calculates the total cost based on the length of stay.

### 💬 Reviews and Ratings
After a completed stay, guests can leave reviews and ratings for the property. This feature helps future users evaluate listings and builds trust within the platform.

### 💳 Payment Processing
Guests are able to make payments for bookings using secure methods (mock or real, depending on project scope). This ensures the booking process is seamless and trustworthy.

### 🔍 Search and Filtering
Users can search for listings by location, price range, date availability, and other filters. This improves the user experience by helping guests quickly find suitable accommodations.

### 📈 Admin Dashboard (optional/bonus)
An admin interface (if implemented) allows for management of users, properties, and bookings. This feature is useful for monitoring the platform and moderating content.

