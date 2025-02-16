# wd037RecapWeek
WBS Coding RecapWeek - Full Stack App: MongoDB, ReactJS, Tailwind CSS, JSON Web Tokens

Recap Week
Day 01
Scaffold backend REST API with ExpressJS
The API will have a single resource called ducks (for today). Learning goals for this step are:

Environment variables
Routers → express.Router()
Controllers
Models → Mongoose
CRUD
Error handling
Async handlers (optional)
Git (local) and GitHub (remote) setup
Deployment
Step by step on how we achieved this:
Installed express, nodemon, dotenv, mongoose and express-validator
Created a index.js file with a basic scaffold for our server
Created a new MongoDB database on MongoDB Atlas
Instantiated a connection in our db folder, exported and called it on server.js
Created a mongoose duck schema and model
Set a route for ducks in our api
Created controller functions to enable CRUD operations for our duck documents
Created a middleware to enable error handling
Created a middleware to validate incoming data (body and params)
Day 02
Scaffold frontend React application
Goal is to scaffold a front end SPA with React to interact with our API Learning goals for this step are:

Using Vite
Revisiting hooks
Routing with React Router DOM
Styling is done with Tailwind but learning it is not a necessity for these sessions
Network requests with Axios → better error handling
Components: NavBar, Layout, RubberDuckCard
Pages: Home, addDuck CreateDuck component → POST to backend API
Deployment
Step by step on how we achieved this:
We created a new app scaffold with Vite, and installed react-router-dom, axios, react-toastify and tailwindcss
Wrapped our App component with a Router component, and created our first routes (Home and AddDuck)
Created a NavBar component and a Layout component to wrap our routes
In our Home component we created a useEffect hook to fetch all ducks from our API
Created a RubberDuckCard component to display each duck
In our AddDuck component we created a useState hook to handle the form data, and a handleSubmit function to POST the data to our API
Deployed our app to Netlify
The remainder of the app was added at a later point, and is not part of the recordings. Feel free to check the remaining code!

Day 03
Backend Authentication Implementation with JWT
The goal is to use JWT to authenticate users and protect routes on our server Learning goals for this step are:

Create the User model
Implement authentication endpoints
/signup → returns token
signin → returns token
me → returns user (owner of token)
Modify Duck model (to refer to User)
Step by step on how we achieved this:
Installed relevant dependencies: bcrypt, jsonwebtoken and cookie-parser
Created a new mongoose schema for users
Established a route for users in our api, split into subroutes for registration, login and getting a single user
Created controllers to register an user, to login the user, and to get a single user
Used bcrypt to salt and hash the password before saving it to the database, and to compare passwords on login
Used jsonwebtoken to create a token on login and registration, and return that to the client in a cookie.
Created a middleware to verify the token and protect the single user route
Altered the duck schema to include a reference to the user that created it
Altered cors setup to allow cookies from different origins

Day 04
Frontend Authentication Implementation with JWT
The goal is to use JWT to authenticate users and protect routes on our client Learning goals for this step are:

Implement sign up and sign in features
Send cookie with token for verification
Setup authentication state
“Session” persistance
Authenticated vs Public UI (Conditional render)
Protected routes with React Router DOM
Step by step on how we achieved this:
Did a few touchups on our backend:
Enabled cors to accept credentials, and enabled sameSite and secure properties on our cookies
Added a logout route and controller to clear cookies
Fleshed out the handleSubmit function of our Login and Register components to send the data to the backend and receive a cookie
Added an useEffect hook to our App component to request the backend and verify the token on page load and on login or register
Upon success of the token's verification, we toggle an authenticated state to true, and store the user's data in another state
Based on the authentication state, we toggle our navbar to display different links
Added a protected route to our AddDuck component, so that only authenticated users can access it, and now have our addDuck send as owner the logged user's id.
Enabled redirection for routes that should not be accessible if the user is logged in (register and login)
Added a logout button to our navbar, which clears the cookies and resets all authentication states

Day 05

Using the ContextAPI to manage state
The goal is to use Context for better state management of global logic on our application Learning goals for this step are:

About
forgerlil/wd037RecapWeek at day-05
