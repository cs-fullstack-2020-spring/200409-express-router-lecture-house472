# 20-04-09 Express Router Lecture


[Resource](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/routes#Routes_primer)


### Set Up
- Create an index.js file
- Generate the `package.json` file by running `npm init` in the terminal
- Install express and nodemon by running `npm install nodemon express` in the terminal
- Import the express module using the `require()` method
- Create a server called app using the `express()` method
- Allow that server to listen on port 8000 using the `listen()` method

### Review of HTTP Requests
- Create a collection in Postman called `200409`


- Create a get method that sends the string `[PLANT_ID] has been accessed via get request` at the path `localhost:8000/flowers/successMessage/[PLANT_ID]`
- Create, test, and save route in 200409 Postman collection


- Create a post method that send the string `[PLANT_ID] has been accessed via post request` at the path `localhost:8000/flowers/successMessage/[PLANT_ID]`
- Create, test, and save route in 200409 Postman collection


- Create a get method that sends the string `[PLANT_ID] has been accessed via get request` at the path `localhost:8000/trees/successMessage/[USERNAME]`
- Create, test, and save route in 200409 Postman collection


- Create a post method that send the string `[PLANT_ID] has been accessed via post request` at the path `localhost:8000/trees/successMessage/[USERNAME]`
- Create, test, and save route in 200409 Postman collection

### Express Router
`express.Router` middleware as it allows us to group the route handlers for a particular part of a site together and access them using a common route-prefix.
#### Reorganizing your existing routes to route modules
- Create a directory called `routes`
- In the `routes` directory create a JS file called `flowers.js` to hold flowers routes
- In the `routes` directory create a JS file called `trees.js` to hold plants routes
- Move routes from `index.js` to appropriate JS files and remove the `trees` or `flowers` part of the path
- Add `let express = require('express');` and `let router = express.Router();` to the top of each file
- Replace `app` with `router` for the routes in each file
- Add `module.exports = router;` to the bottom of each file


#### Updating the entry point file
- Import the flower and tree router modules at the top of the entry point file using this syntax
    - `let MODULE_NAME = require('./MODULE_NAME.js');`
- Add the routing middleware for each module using this syntax
    - `app.use('/PATH_NAME', MODULE_NAME);`
    