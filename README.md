# POSS107G09

## Project Title: Multimedia Education Interactive Application

## Group Introduction
We will list the game clearly and some fully link for interactive teaching material provide users to use.

 

The problem we may face is that the materials may be not too much and the open source can only provide users for online using, can’t download it.

 

The functionality of the system: We can use this web application to let the users who learn about multimedia feel more interesting and satisfying in learning.

### Authors

* **Jhang Guan-Yi** - *IIT-404840455*
* **Chen Chun** - *IIT-404840158* 
* **Chen Tse-Jung** -IIT-404840216*
* **Chang Hao-Hsun** - *IIT-404850488*

###Getting Started
1. Setting Up Apache
Update and install apache in your local package by using this command on the terminal:

$ sudo apt update
$ sudo apt install apache2
Afterwards you can check whether Apache is running on your system by typing this command:

$ sudo systemclt status apache2
2. Installing MariaDB
Install mariadb-server from the command line:

$ sudo apt install mariadb-server
Check whether mariadb is running on your system:

$ sudo systemclt status mariadb
Then run the mariadb secure installation:

$ sudo mysql_secure_installation
Then just answer (Yes) to all questions.

3. Setting up the Database
After finishing installtion of MariaDB, you need to set up the database. First login to root user:

$ mysql -u root -p
root user default password is "empty" so just press enter afterwards. Then run the .sql script which you can find here and execute it with this line of code

$ mysql> source location\to\sql\script;
Then a user called admin should be available on your mariadb with privileges of the root user and the password of admin. Then just log out and login with the admin user.

$ mysql -u admin -p
Then create a databse called user with the tables accounts and tasks

mysql> CREATE DATABASE user;
mysql> USE user;
Create table accounts:

mysql> CREATE TABLE accounts (
  user_id MEDIUMINT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(100),
  pass VARCHAR(100),
  email VARCHAR(100)
  );
Create table tasks:

mysql> CREATE TABLE tasks (
  id MEDIUMINT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  description VARCHAR(100),
  user_id MEDIUMINT NOT NULL
);
Then you need to add a foreign key from accounts.user_id to the tasks tasks.user_id:

mysql> ALTER TABLE tasks
  ADD FOREIGN KEY (user_id) REFERENCES accounts (user_id);
And now you are done, and your db is ready to go!

4. Clone Repository to Apache root/folder
Clone this repository.
Put everything(copy and replace) under /var/www/html/*.
Done!
How It Works
Utilizing Linux as our host machine, we coded in PHP, HTML, CSS, and JS for the to-do list application.
A SQL database was established using MariaDB to store user accounts and users' tasks.
Apache 2 was used as the web server for our web application.
Contributing Guidelines
This is the final version of our project but we would appreciate feedback of any kind that will help us improve in any aspect of our execution of this project.

