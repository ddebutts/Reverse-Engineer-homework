Server.js - this file has the requirements for the npm packages. Describes the port configuration information. Uses sessions to track login status. Requires the routes.  Then uses sequelize to sycn the database and log a message that the server is up.

Package.json - describes the packages and versions being used.

package-lock.json - describes requirements for packages in package.json.

html-routes.js - describes the routes for members.  Sign up, Login, or if authenticated members pages.

api-routes.js - contains get and post actions for login, signup, logout, and for when the user is not logged in.  uses passport to determine authentication.  

signup.html - inputs for email and password with a submit button. includes a link to the login page if already a member.

login.html - inputs for email and password with a login button. includes a link to the signup page if not already a member.

members.html - page displays a welcome message and show the users email address.  This pageis loaded after authentication.

style.css - Sets the margin-top for login and signup forms to 50px.

signup.js - gets references to the form and inputs. validates inputs are not blank when submit is clicked. Then calls signupuser function. completes a post to singup route and  redirects them to the members page if no errors.  Alert messages are coded for any login error in the .catch.

members.js - does a get to determine user logged in and updates the HTML page.

login.js - gets references to the form and inputs. validates inputs are not blank when login is clicked. If email and pw are calls loginuser function and if no error redirect them to members page.

Public folder - makes all the static resources available.

node_modules - contains all npms and their dependencies.

Models\user.js - used to configure the user table which will be built when the app starts via sequelize.  the columns are email and user.  This one contains a hook that will hash he user's pw.

Models\index.js - part of sequelize that executes the models.

passport.js - requires passport defines a local strategy for passport. Checks to see if user is exists and if not return message incorrect email.  If user is good but password is wrong send message incorrect password. Not sure how last section works but it serializing and deserializing the user to for authentication purposes.

config.json - stores information for database connections to dev, prod, and test.

isAuthenticated.js - this is middleware for restricting routes a usr is not allowed to visit if not logged in.

This feels like a lot of code to have a signup page, login page and member page where routes are dictated by membership and if logged in.