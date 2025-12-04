Classroom Booking System 

This repository contains the full source code and documentation for a relational database system designed to manage classroom and resource bookings in an educational institution.

The core logic of this system relies on a normalized 8-table schema (implemented in MySQL) to manage users, rooms, features, and prevent double-booking via unique constraints.

Repository Structure

The repository is organized exactly according to the submission requirements:

[Project Root]
├── project-root/           <-- Front-end source files (Entry point for correction)
│   ├── index.html          <-- The complete application file (HTML, CSS, JS)
│   └── README.md           <-- This file
├── sql/                    <-- Database scripts
│   └── CP3520_submission_script.sql
└── docs/                   <-- Documentation and Diagrams
    └── booking_sequence_diagram.md


Front-end Application (project-root/index.html)

This file is the single entry point for the application.

Technology: Pure HTML5 and JavaScript (JS logic runs entirely in the browser).

Styling: Uses Tailwind CSS (via CDN) for modern, responsive design.

Data Source: The JS code contains Mock Data (let DB = { ... }) that exactly mirrors the tables created in the SQL submission. This allows the application to run immediately when opened in any browser (e.g., Chrome, Firefox) without needing a live server connection.

Functionality Demonstration:

User Switching: The top selector allows testing permissions for Instructor IDs (1-5) and Admin IDs (1-5).

Instructor View: Allows users to search by capacity and features, submit pending booking requests, and cancel their own pending requests.

Admin View: Displays pending requests (Informal Query 1) and allows the Administrator to Approve (Func 5) or Reject (Func 3) them. Approval logic includes a JavaScript check to prevent double-booking.

Database Implementation (sql/CP3520_submission_script.sql)

This script must be run once in a local MySQL environment (MAMP/Laragon) before correcting.

Naming: The script uses CP3520_<GROUP_NUMBER> for the database name.

Content: The script performs three primary functions:

DDL: Creates all 8 entity and junction tables (Instructors, Rooms, Bookings, Features, etc.).

Cleanup: Uses TRUNCATE TABLE to safely clear the database if run multiple times.

DML: Populates all key entity tables with 5 or more entries (Instructors, Admins, Rooms, Courses, Features).

How to Run the Project Locally

Run the Database: Open the sql/CP3520_submission_script.sql file in your MySQL environment (MAMP/XAMPP/VS Code SQLTools). Execute the entire script.

Run the Application: Open the project-root/index.html file directly in any web browser.

Test: Use the "Change User" selector to test the distinct functionalities of the Instructor and Administrator roles.
