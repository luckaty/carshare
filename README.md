# Carshare

Carshare is a PHP and MySQL-based web application that allows users to share car trips by posting and booking rides. It provides user authentication, trip management, and profile customization features.

---

## Table of Contents

- [Features](#features)  
- [File Structure](#file-structure)  
- [Database Schema](#database-schema)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Contributing](#contributing)  
- [License](#license)  

---

## Features

- User registration, login, and profile management  
- Password reset and email activation  
- Create, update, delete, and view car trips  
- Search and filter trips by destination and date  
- Profile picture uploads  
- Persistent login with "Remember Me" functionality  

---

## File Structure


---

## Database Schema

The project uses the following MySQL tables:

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

Installation
  1. Clone the repository
  git clone https://github.com/luckaty/carshare.git
  cd carshare
  2. Set up your web server (Apache/Nginx) with PHP and MySQL support.
  3. Create a MySQL database and import the schema from the SQL tables above.
  4. Update connection.php with your database credentials.
  5. Upload the project files to your server's web root or run locally with a local server (XAMPP, MAMP, etc.).

## Usage

- Register a new account via the signup page.
- Activate your account via the email link.
- Log in and create car trips to share.
- View, update, or delete your trips.
- Search for available trips posted by others.
- Update your profile and upload a profile picture.
- Use the “Remember Me” option to stay logged in.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests for improvements and bug fixes.


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


