# CarShare

A full-featured PHP web application for carpooling and trip management. Users can sign up, create and join trips, manage profiles, and interact with a responsive and user-friendly interface.

## 🚗 Overview

CarShare allows users to efficiently share rides, manage trips, and collaborate on travel plans. The application supports user authentication, profile management, trip creation and editing, and note-taking features, all built with PHP, JavaScript, and Bootstrap for styling.

---

## 🔧 Features

- User registration and login system
- Password reset and email activation workflow
- Create, edit, and delete trips
- View trip details dynamically
- User profile with picture upload
- Notes creation and management
- Responsive UI using Bootstrap 3
- Google Maps integration for trip routes (map.js)
- AJAX-powered interactions for smooth user experience

---

## 🗂️ Project Structure

carshare/
├── index.php
├── signup.php
├── login.php
├── logout.php
├── mainpageloggedin.php
├── profile.php
├── profile.js
├── javascript.js
├── map.js
├── mytrips.js
├── css/
│ ├── bootstrap.css
│ └── bootstrap-theme.css
├── profilepicture/
├── uploads/
├── connection.php
├── activatenewemail.php
├── forgot-password.php
├── resetpassword.php
├── storeresetpassword.php
├── addtrips.php
├── updatetrips.php
├── deletetrips.php
├── gettripdetails.php
├── gettrips.php
├── createnote.php
├── deletenote.php
├── loadnotes.php
├── remember.php
├── updateemail.php
├── updatepassword.php
├── updatepicture.php
├── updateusername.php
├── notes.txt # Database schema and API key
└── README.md



---

## 🗄️ Database Schema

The following tables are required for the application and are defined in `notes.txt`:

```sql
CREATE TABLE `users` (
  `user_id` int(11) NOT NULL AUTO_INCREMENT,
  `first_name` char(30) NOT NULL,
  `last_name` char(30) NOT NULL,
  `username` varchar(30) DEFAULT NULL,
  `email` varchar(50) DEFAULT NULL,
  `password` varchar(64) DEFAULT NULL,
  `activation` char(32) DEFAULT NULL,
  `activation2` char(32) DEFAULT NULL,
  `gender` char(6) DEFAULT NULL,
  `phonenumber` char(15) DEFAULT NULL,
  `moreinformation` varchar(300) DEFAULT NULL,
  `profilepicture` varchar(55) DEFAULT NULL,
  PRIMARY KEY (`user_id`)
);

CREATE TABLE forgotpassword (
  `id` INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  user_id int(11) NOT NULL,
  rkey char(32) NOT NULL,
  time int(11) NOT NULL,
  status varchar(7) NOT NULL
);

CREATE TABLE rememberme (
  `id` INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  authentificator1 char(20),
  f2authentificator2 char(64),
  user_id int(11),
  expires datetime
);

CREATE TABLE carsharetrips (
  trip_id INT(4) NOT NULL PRIMARY KEY AUTO_INCREMENT,
  user_id INT(4),
  departure CHAR(30),
  departurecoord CHAR(30),
  destination CHAR(30),
  destinationcoord CHAR(30),
  price CHAR(10),
  seatsavailable CHAR(2),
  regular CHAR(1),
  date CHAR(20),
  time CHAR(10),
  monday CHAR(1),
  tuesday CHAR(1),
  wednesday CHAR(1),
  thursday CHAR(1),
  friday CHAR(1),
  saturday CHAR(1),
  sunday CHAR(1)
);

🔑 Google Maps API Key
You will need to add your own Google Maps API key in map.js for route visualization:


// Replace the placeholder with your actual API key:
const apiKey = 'YOUR_GOOGLE_MAPS_API_KEY';

💻 Technologies Used
Backend: PHP 7+
Frontend: HTML5, CSS3, JavaScript (Vanilla), Bootstrap 3
Database: MySQL
APIs: Google Maps API

🚀 Getting Started
Installation & Setup
Clone the repository:

git clone https://github.com/luckaty/carshare.git
Import the database schema from the SQL commands above.
Configure your database connection in connection.php.
Place the files in your web server directory.
Open index.php to get started.

🙋‍♂️ Contact
Developed and maintained by luckaty
