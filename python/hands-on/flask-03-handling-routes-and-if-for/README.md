# Hands-on Flask-03 : Handling Routes and Templates with Flask Web Application and If and For Structure

Purpose of the this hands-on training is to give the students introductory knowledge of how to handle routes and use html templates within a Flask web application on Amazon Linux 2 EC2 instance. 

## Learning Outcomes

At the end of the hands-on training, students will be able to;

- install Python and Flask framework on Amazon Linux 2 EC2 instance

- build a simple web application with Flask framework.

- understand the HTTP request-response cycle and structure of URL.

- create routes (or views) with Flask.

- serve static content and files using Flask.

- serve dynamic content using the html templates.

- write html templates using Jinja Templating Engine.

## Outline

- Part 1 - Getting to know routing and HTTP URLs.

- Part 2 - Write a Web Application using If conditions and for loops

- Part 3 - Write a Web Application with Sample Routings and Templating on GitHub Repo

- Part 4 - Install Python and Flask framework Amazon Linux 2 EC2 Instance and Run the Hello World App on EC2 Instance

## Part 1 - Getting to know routing and HTTP URLs.

HTTP (Hypertext Transfer Protocol) is a request-response protocol. A client on one side (web browser) asks or requests something from a server and the server on the other side sends a response to that client. When we open our browser and write down the URL (Uniform Resource Locator), we are requesting a resource from a server and the URL is the address of that resource. The structure of typical URL is as the following.

![URL anatomy](./url-structure.png)

The server responds to that request with an HTTP response message. Within the response, a status code element is a 3-digit integer defines the category of response as shown below.

- 1xx -> Informational

- 2xx -> Success

- 3xx -> Redirection

- 4xx -> Client Error

- 5xx -> Server Error

## Part 2 - Write a Web Application using If conditions and for loops

- Create folder named `flask-03-handling-routes-and-if-for` within `my-repository` repo

- Create folder named `Flask_if_for_structure` within `flask-03-handling-routes-and-if-for` repo

- Create python file named `app.py`

```python
# Import Flask modules

# Create an object named app 

# Create a function named head which shows the massage as "This is my first conditions experience" in `index.html` 
# and assign to the route of ('/')

# Create a function named header which prints numbers from 1 to 10 one by one in `index.html` 
# and assign to the route of ('/')

# run this app in debug mode on your local.

```

## Part 3 - Write a Web Application with Sample Routings and Templating on GitHub Repo

- Create folder named `flask-03-handling-routes` within `flask-03-handling-routes-and-if-for` repo

- Create python file named `app.py`


```python
# Import Flask modules

# Create an object named app 

# Create a function named head which shows the message as "This is my conditions experience" in 'index.html'

# and assign to the static route of ('/')

# Create a function named header which prints numbers from 1 to 10 one by one 'index.html' 
# and assign to the static route of ('/')

# run this app in debug mode on your local.

```
- Add and commit all changes on local repo

- Push folders to remote repo `my-repository` on GitHub.

## Part 4 - Install Python and Flask framework Amazon Linux 2 EC2 Instance and Run the Hello World App on EC2 Instance

- Launch an Amazon EC2 instance using the Amazon Linux 2 AMI with security group allowing SSH (Port 22) and HTTP (Port 80) connections.

- Connect to your instance with SSH.

- Update the installed packages and package cache on your instance.

- Install `Python 3` packages.

- Check the python3 version

- Install `Python 3 Flask` framework.

- Check the versions of Flask framework packages (flask, click, itsdangerous, jinja2, markupSafe, werkzeug)

- Download the web application file from GitHub repo.

- Run the web application

- Connect the route handling and templating web application from the web browser and try every routes configured

- Open the static file `mytext.txt` context from the web browser

- Connect the route handling and templating web application from the terminal with `curl` command.

