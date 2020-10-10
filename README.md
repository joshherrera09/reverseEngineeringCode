# Unit 14 Sequelize Homework Reverse Engineering Code

## Config

### Middleware

-- isAuthenticated.js --

    Restricts routes if the user is not logged in, if they are logged in it continues with the request.

#### config.json

    Connection configure, to connect to the database in mysql

#### passport.js

    Passport is the authentication mddleware used for password and email, if there is no user with the emailand password entered, they are not authenticated.

### Models

-- index.js --

    This file is connected to the database, and storing/logging the users info into the database

--user.js --

    Here they are using bcrypt which is used to help hash passwords.  As well as a function that defines what information will be stored into the database to define each User.  

### Public

#### js

-- login.js -- 

    First assigning variables to the html elements to use in the functions later when buttons are clicked and info is put into the input sections.

    The loginForm.on("submit", ....) this is used to verify that the user entered both emai land password.

    loginUser() function, is used to do a POST call to the api/login route and redirect the user to the members page.

-- members.js --

    A function to do a GET call to load the users info onto the page.

-- signup.js --

    signup.js creates functionality for the signup.html file.  Email/password validation happens after the user enter their info.  If validated, the signUpUser function redirects to the members page.

### Routes

-- api-routes.js --

    Our api-routes file starts by requiring passport for password validation, and our models files to help render user info.  

    These are are routes to determine where to send the user, first login, signup (if user does not have vaild email and password yet), and logout.

-- html-routes.js --

    Our html-routes file determines what page to display to the user.  After login.html, if the user has a profile they are sent to the members.html page otherwise they are sent to the signup.html


-- package.json --

    This file is where any dependencies that we have installed are logged.

-- server.js -- 

    At the top we are requiring all of our installed npm packages. Then we set up a PORT to run the application on.  By using "process.env.PORT || 8080" this allows the application to run on the local PORT the user has set up OR 8080.

    It requires our routes.

    It ends by setting up our listener for the server.
