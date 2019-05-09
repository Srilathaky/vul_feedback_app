* This app can be used to demonstrate the following vulnerabilities: 
	* SQL Injection
	* XSS - Reflective and Persistent
	* Path Traversal 	

# Business Details
It is an app where user can provide review for hotels. The business revolves around our personal contacts with food critics whose review comments and ratings are highly valued.
The application login is on invite-only basis to food critics.
Currently we have a venture capitalist investment, but with no income.
The future of the business lies in attracting hotels once we have a successful database of reviews and ratings. These hotels would publish ads on our website in the future, and we shall thus earn revenue.

* So, there are 2 very critical assets for the business today:
	1. The fund from the venture capitalist
	2. The current database and relationship with food critics

# Setup
You need [docker](https://docs.docker.com/engine/installation/) installed in the machine. 
After cloning the repo, you can run ```docker-compose up``` and that should set up the application.

# Dependencies Status
[![Dependency Status](https://gemnasium.com/badges/github.com/jaydeepc/vul_feedback_app.svg)](https://gemnasium.com/github.com/jaydeepc/vul_feedback_app)


# Setup without docker (for MAC)
1. Install mysql if mysql is not installed(mysql can be installed using brew: `brew install mysql`).

2. Start the mysql server by running `mysql.server start` command in the terminal.

3. Host the mysql locally with username `mysql -h localhost -u root`

4. Run the following commands on terminal where mysql is ready
    `create database Feedback`;
    `use Feedback`;
    `source "vul_feedback_app" repository path/db/db.sql`
    
5. Two tables reviews and users will be created inside Feedback database.

6. Navigate to the "vul_feedback_app" repository path and run the following commands
    `pyvenv test_feedback`
    `source test_feedback/bin/activate`
    

7. Run the following commands
    `pip install -r requirements.txt`
    
8. In app.py file, change "app.config['MYSQL_DATABASE_HOST'] = 'db_server'" to app.config['MYSQL_DATABASE_HOST'] = 'localhost'

9. Run the command `python app.py`.

10. Access the application "http://localhost:5000/home".
