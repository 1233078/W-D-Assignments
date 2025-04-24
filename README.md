IT Help Desk Complaint System
Welcome to the IT Help Desk Complaint System, a web application designed to streamline customer support by allowing users to report IT issues through an interactive chat interface. Users are greeted with a welcome page, start a chat, select from predefined complaint categories, navigate sub-options, and submit reports that are emailed to the support team. This project is built with HTML, CSS, JavaScript, AJAX, PHP, and SQL, using the CakePHP framework for robust backend functionality.
Project Overview
The IT Help Desk Complaint System enables users to:

View a welcome page with a friendly greeting and a "Let's Chat" button.
Begin a chat session for reporting issues.
Choose from 5 predefined complaint categories (e.g., "A type Error").
Select sub-options to specify the issue details.
Submit the complaint, which is sent to assignmentdbweb2@gmail.com as a report.

The system is designed for ease of use, team collaboration, and scalability, with a focus on secure data handling and a responsive user interface.
Tech Stack

HTML: Structures the welcome page, chat interface, and forms.
CSS: Styles the application, including a full-page background and responsive design.
JavaScript/AJAX: Powers the interactive chat and dynamic sub-option loading without page reloads.
PHP (CakePHP): Handles backend logic, form processing, and email sending.
SQL (MySQL): Stores user data, complaints, and chat interactions.

Project Structure
it-helpdesk/
├── config/                 # CakePHP configuration (e.g., app_local.php)
├── src/                    # PHP controllers, models, and templates
│   ├── Controller/         # CakePHP controllers (e.g., ComplaintsController.php)
│   ├── Model/              # Database models (e.g., ComplaintsTable.php)
│   └── Template/           # Views (e.g., chat.ctp, welcome.ctp)
├── webroot/                # Public assets
│   ├── css/                # Styles (style.css)
│   ├── js/                 # Scripts (chat.js)
│   └── img/                # Images (e.g., background.jpg)
├── sql/                    # Database schema
│   └── init.sql            # Schema for users, complaints, etc.
├── vendor/                 # Composer dependencies (ignored)
├── .env                    # Environment variables (ignored)
├── .gitignore              # Git ignore rules
├── composer.json           # PHP dependencies
└── README.md               # This file

Setup Instructions
Follow these steps to set up the project locally:

Clone the Repository:
git clone https://github.com/your-username/it-helpdesk.git
cd it-helpdesk


Install Dependencies:

Ensure Composer is installed.
Run:composer install




Configure the Database:

Create a MySQL database:mysql -u root -p -e "CREATE DATABASE it_helpdesk;"


Import the schema:mysql -u root -p it_helpdesk < sql/init.sql


Copy config/app_local.php.example to config/app_local.php and update with your database credentials:'Datasources' => [
    'default' => [
        'host' => 'localhost',
        'username' => 'root',
        'password' => 'your_password',
        'database' => 'it_helpdesk',
    ],
]




Set Up Environment Variables:

Copy .env.example to .env and configure email settings for sending reports:EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USERNAME=assignmentdbweb2@gmail.com
EMAIL_PASSWORD=your_app_password




Run the Application:

Start the CakePHP development server:bin/cake server


Access the app at http://localhost:####.


Test Email Functionality:

Ensure your email configuration (e.g., Gmail SMTP) is correct.
Submit a complaint to verify that a report is sent to assignmentdbweb2@gmail.com.



Features

Welcome Page: Displays a greeting ("Welcome to IT Help Desk!") and a "Start" button to initiate the chat.
Interactive Chat: Uses AJAX for seamless navigation through 5 complaint categories and their sub-options.
Complaint Categories: Examples include "Network Issue", "Software Error", "Hardware Failure", "Account Access", and "Other".
Sub-Options: Each category branches into specific issues (e.g., "Network Issue" → "Slow Connection", "No Connection").
Report Submission: Complaints are processed and emailed to assignmentdbweb2@gmail.com with details like issue type and timestamp.
Responsive Design: Full-page background and mobile-friendly layout (CSS).
Secure Backend: Uses CakePHP’s CSRF protection and input sanitization to prevent attacks.

Database Schema
The sql/init.sql defines:

users: Stores client and agent information (id, username, email, password, role).
complaints: Tracks complaints (id, user_id, category, sub_option, status, created_at).
chat_messages: Logs chat interactions (id, complaint_id, sender_id, message, sent_at).

Contributing
We welcome contributions from the team! Follow these guidelines:

Branching: Create feature branches (git checkout -b feature/add-complaint-form).
Commits: Write clear commit messages (e.g., "Add AJAX for sub-option loading").
Pull Requests: Submit PRs with detailed descriptions and link to related issues.
Coding Standards: Follow CakePHP conventions and PSR-12 for PHP.
Issues: Report bugs or suggest features via GitHub Issues.

Example Workflow

Clone the repo and create a branch:git checkout -b feature/new-complaint


Make changes, commit, and push:git add .
git commit -m "Add new complaint category"
git push origin feature/new-complaint


Open a pull request on GitHub for review.

Deployment
To deploy the application:

Upload the project to a server (e.g., Heroku, AWS, or shared hosting).
Configure the database and .env on the server.
Set up email SMTP (e.g., Gmail with an App Password).
Ensure the server supports PHP 7.4+ and MySQL.
Test the complaint submission to verify email delivery.

Notes

Email Setup: Use an App Password for Gmail SMTP due to security restrictions.
AJAX: The chat relies on AJAX for dynamic loading of complaint options. Check webroot/js/chat.js for implementation.
CSS: The full-page background is defined in webroot/css/style.css (e.g., background-size: cover).
Security: Input sanitization and CSRF tokens are implemented to align with best practices.


Thank you for visiting our IT Help Desk Complaint System repository!
