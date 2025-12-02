1. Project info:
   Project name: ToDo App
   Group no.: 41B
   Students’ names(SID): LO Ching(14103940), LEUNG Siu Lei(14196090)
   
2. Project file intro:
- server.js: contain the server basic function, like the database connection,error handle ,routes and home page when the open the server  
- package.json: use bcryptjs,body-parser,connect-mongo,cookie-parser,dotenv,ejs,express,express-session,mongoose dependencies
- public: use css file to the basic webpage UI
- views/:
  calendar.ejs: users can view all tasks in the calendar
  edit-task.ejs: user can edit their exist tasks in here by change the status, priority and dueDate in the task. User can choose to delete their task in this page
  error.ejs: 
  index:the home page to introduce the basic function to the new user, for example introduce the function on manage task
  login.ejs: users which already have account can login to their account, new users can click the button to register their account
  new-task.ejs:users can create a new task in here. 
  register.ejs: new users can their own account,It have a vaidation function to confirm the passwors is correct
  tasks.ejs: users can manage their account and filter their task
  time.ejs: users can use timer in here
  partials/header.ejs:contain the the login function and home page short cut key for user better use
  
- models/:
  User.js: store the user require information like username, password and give some restriction like the digit of the password and unique user information
  Task.js:store the task information like title ,description,dueDate.priority,status and related user.It also contain the choice like pending, in-progress, completed in status
  

3. The cloud-based server URL (your server host running on the cloud platform) for testing:
https://comp3810sef-group41b.onrender.com

4. Operation guides (like a user flow) for your server
- Use of Login/Logout pages:
 Login from Home Page
     On the home page, click the Login button
     Enter your username and password
     Click the login button to access the system
Register New Account
   If you don't have an account:
   Click the Register button
   Fill out the registration form:
   Username: Must be 3-30 characters long
   Password: Must be at least 6 characters long
   Confirm Password: Re-enter the same password for verification
   After successful registration, you'll be automatically logged in
Task Page Features
   After successful login:
   You'll be redirected to the Task Management Page
   The top-right corner displays: "Welcome, [Your Username]"
   Next to it is the Logout button
   Click Logout to securely exit the system
 
- Use of your CRUD web pages: which button or UI is used to implement create, read, update, and delete?

//Create and read
After logging in, the dashboard displays an "Add Your First Task" button. Users can click this button to open a form for creating a new task, where they enter details such as Title* (required), Description, Due Date, Priority, and Status. At the bottom of the form, an "Add Task" button submits the entry, successfully creating the task. 

Users can also create additional tasks by clicking the "+ Add New Task" button, located next to the calendar and timer buttons.

//Update
The task then appears in the "My Tasks" page. To edit any details, users click the "Edit" button next to the task, modify the desired information in the form, and click the "Update Task" button at the bottom. The changes are saved, and the updated task is reflected immediately in the list.

//Delete
To delete a task, users click the "Delete" button. A confirmation dialog appears with the message "Are you sure you want to delete this task?" Clicking "Yes" permanently removes the task from the list.


- Use of your RESTful CRUD services:
  
//Login
curl -c cookies.txt -X POST "https://comp3810sef-group41b.onrender.com/auth/login" \
  -H "Content-Type: application/json" \
  -d '{"username": "123456","password":"123456"}'

//Get 
curl -b cookies.txt "https://comp3810sef-group41b.onrender.com/api/tasks" | jq .

//Post (Create a new task)
TASK_ID=$(curl -b cookies.txt -X POST "https://comp3810sef-group41b.onrender.com/api/tasks" \
  -H "Content-Type: application/json" \
  -d '{"title":"Test Task","description":"Created for demo","dueDate":"2025-11-26","priority":"high","status":"pending"}' \
  | jq -r '.data._id')

//Put(Update the task)
curl -b cookies.txt -X PUT "https://comp3810sef-group41b.onrender.com/api/tasks/$TASK_ID" \
  -H "Content-Type: application/json" \
  -d '{"title":"Updated SUCCESS!","status":"completed","priority":"low"}'

//Delete
curl -b cookies.txt -X DELETE "https://comp3810sef-group41b.onrender.com/api/tasks/$TASK_ID"
