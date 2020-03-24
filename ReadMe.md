1. Getting started:

prerequisites: node and npm
    these are available inside GCP cloud shell if you can't install them locally.

a. open two separate terminals: one in /internal, one in /external
b. run npm install in each terminal
c. run node server.js in the /internal terminal
d. run npm start in the /external terminal
e. navigate to http://localhost:8080

2. The sample app

Uses nodejs with the express web server on both server and client microservices.

The internal service receives REST requests on port 8082 and returns mock data.

The exteral service inserts json from the internal service into an html template in the Views folder
and returns it to the requestor on port 8080.

3. Dependencies

internal and external both use the following npm packages:

express: a web server
    https://www.npmjs.com/package/express
body-parser to convert json and form data in the request into parameters.
    https://www.npmjs.com/package/body-parser
mocha, chai and supertest (for unit testing)
    https://www.npmjs.com/package/mocha
    https://www.npmjs.com/package/chai
    https://www.npmjs.com/package/supertest
nyc for code coverage reporting
    https://www.npmjs.com/package/nyc


The exteral service uses the following additional libaries:

express-handlebars ( a templating library)
    https://github.com/ericf/express-handlebars
nock (for mocking the api call)
    https://www.npmjs.com/package/nock


4. Windows 
The external/package.json file uses linux-style syntax for environment variables.
Windows users will need to modify the code in order to run the sample locally, e.g.
    "start": "set SERVER=http://localhost:8082&& node server.js",
    "test": "set SERVER=http://localhost:8082&& nyc mocha"
These values should only be used for local testing, and not when deploying.