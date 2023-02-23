# Scaler Interview Creation Portal

This is an open source project for creating a simple web app where admins can create interviews by selecting participants, interview start time and end time. The main purpose of this application is to eliminate the manual process of planning interviews and to make the process more efficient and organized.

## Demo

You can watch the demo of this project here:

[![Interview Creation Portal Demo](https://img.youtube.com/vi/BUHH9uyhB-4/0.jpg)](https://youtu.be/0iMfgwe9gy0)

## Built With

- HTML & CSS
- JavaScript
- NodeJS
- MySQL

## Features

- Create an interview by selecting participants, start time and end time
- Throw error with proper error message if any of the participants is not available during the scheduled time or if the number of participants is less than two
- View all upcoming interviews in an interviews list page
- Edit an already created interview with the same validations as on the creation page
- Send emails to participants on interview creation/modification

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.


To run this project you have to install NodeJS (npm) and MySQL server on your machine.

To setup the web server:

Go to the project directory and run the terminal command as follows:
```
cd server
npm install
```
To setup the MySQL database:

1. Create a Database/Schema name as "InterviewDB" or run the following SQL queries.
```
CREATE DATABASE InterviewDB;
```
```
USE InterviewDB;
```
2. Add two tables "users", to hold data of the available users and "interviews", to hold the data of the upcoming interviews. Run the following SQL query.
  ```
  CREATE TABLE users (
    name VARCHAR(100) NOT NULL,
    email_id VARCHAR(100) NOT NULL,
    PRIMARY KEY (email_id));
  ```
Add some random names with email addresses to the users tables. Run the following SQL query.
```
INSERT INTO users (name, email_id) VALUES ('Chandra', 'chandrasekhar.v.369@gmail.com');
INSERT INTO users (name, email_id) VALUES ('Krishna', 'gkrishnasai2003@gmail.com');
....
....
and so on..
```
Create the table interviews with fields id, email1, email2, startTime, endTime. Run the following SQL query.
```
CREATE TABLE interviews (
  id INT NOT NULL AUTO_INCREMENT,
  email1 VARCHAR(100) NOT NULL,
  email2 VARCHAR(100) NOT NULL,
  startTime DATETIME NOT NULL,
  endTime DATETIME NOT NULL,
  PRIMARY KEY (id));
```
You may or may not any data into the interviews table. The data will be added automatically when you scedule a new interview.

Change the following in ```server/dbServicejs``` if your MySQL server is setup on different port or has different credentials.
![MySQL credentials](https://i.paste.pics/9WL5X.png)

Now when everything is setup. Run the server:
```
cd server
nodemon app
```
If everything is successfull you will the see the text "app is running" and "db is connected" on your terminal.
Then open go to client and open index.html. 

Here is the screenshot of the working system / frontend.
![screenshot](https://i.paste.pics/LUNUA.png)

## Limitations

The application is currently limited to a local MySQL database, which means that any data added to the database can only be accessed from the local machine. To make the application available to anyone, a remote connection to the database needs to be setup, such as using Heroku or AWS.