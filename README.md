1. Project info:
   Project name: ToDo App
   Group no.: 41B
   Students’ names(SID): LO Ching(14103940), LEUNG Siu Lei(14196090)
   
2. Project file intro:
- server.js: contain the server basic function, like the database connection,error handle ,routes and home page when the open the server  
- package.json: use bcryptjs,body-parser,connect-mongo,cookie-parser,dotenv,ejs,express,express-session,mongoose dependencies
- public: use css file to the basic webpage UI
- views:
  calendar.ejs:
  edit-task.ejs: user can edit their exist tasks in here by change the status, priority and dueDate in the task. User can choose to delete     their task in this page
  index:the home page to introduce the basic function to the new user, for example introduce the function on manage task
  login.ejs: users which already have account can login to their account, new users can click the button to register their account
  new-task.ejs:users can create a new task in here. 
  register.ejs: new users can their own account,It have a vaidation function to confirm the passwors is correct
  tasks.ejs: users can manage their account and filter their task
  time.ejs: users can use timer in here
  header.ejs:contain the the login function and home page short cut key for user better use
  
- models:
  User.js: store the user require information like username, password and give some restriction like the digit of the password and    unique   user information
  Task.js:store the task information like title ,description,dueDate.priority,status and related user.It also contain the choice      like     pending, in-progress, completed in status
  

3. The cloud-based server URL (your server host running on the cloud platform) for testing:
https://comp3810sef-group41b.onrender.com

4. Operation guides (like a user flow) for your server
- Use of Login/Logout pages:
 
- Use of your CRUD web pages: which button or UI is used to implement create, read,
update, and delete?
- Use of your RESTful CRUD services: the lists of APIs? HTTP request types? Path URI?
How to test them? CURL testing commands?

2. Project file intro:
server.js: contain the server basic function, like the database connection,error handle, routes and home page when the open the server  
package. json: use bcryptjs, body-parser, connect-mongo, cookie-parser, dotenv,ejs,express,express-session, mongoose dependencies
public: use css file to the basic webpage UI
views/:
•	calendar.ejs:
•	edit-task.ejs: user can edit their exist tasks in here by change the status, priority and dueDate in the task. User can choose to delete their task in this page
•	index: the home page to introduce the basic function to the new user, for example introduce the function on manage task
•	login.ejs: users which already have account can login to their account, new users can click the button to register their account
•	new-task.ejs: users can create a new task in here. 
•	register.ejs: new users can their own account, It have a vaidation function to confirm the password is correct
•	tasks.ejs: users can manage their account and filter their task
•	time.ejs: users can use timer in here
•	header.ejs:contain the login function and home page short cut key for user better use
  
models/:
•	User.js: store the user require information like username, password and give some restriction like the digit of the password and unique user information
•	Task.js: store the task information like title, description, dueDate, priority, status and related user. It also contains the choice like pending, in-progress, completed in status

