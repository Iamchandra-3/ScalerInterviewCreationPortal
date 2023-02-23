# Interview-Creation-Portal

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
INSERT INTO users (name, email_id) VALUES ('Arin', 'arin.nigam@gmail.com');
INSERT INTO users (name, email_id) VALUES ('Deepshi', 'deepshisharma123@gmail.com');
INSERT INTO users (name, email_id) VALUES ('Kirti', 'kirti.godani837@gmail.com');
INSERT INTO users (name, email_id) VALUES ('Govind', 'govindmh14@gmail.com');
INSERT INTO users (name, email_id) VALUES ('Kushagra', 'kushagra98@live.com');
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
![screenshot](https://i.paste.pics/9WLA9.png)
