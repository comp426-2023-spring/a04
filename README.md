# a04 Stand up an API

This assignment will help you stand up a web API using Express and the module that you produced for a03.

Make sure to consult the appropriate documentation as you work through the assignment instructions.

## DO NOT CLONE THIS TEMPLATE REPOSITORY DIRECTLY

Use the GitHub classroom link instead: https://classroom.github.com/a/CtRcwZji

If you clone the template repo directly, it will not be added to the organization as an individual repo associated with your account and you will not be able to push to it. This repository should only be used for assignment issues.

## Instructions

In this assignment, you are going to convert the functions that you wrote for a03 to emulate rolling dice and then do things with the resulting information.
The focus of the assignment is not necessarily on creating basic API endpoints in Node using Express.js.

The instructions for this are fairly sparse because I want you to be creative in how you approach this.
There are a only a few things that you will have to do very specifically in order to make this work, but beyond that, HOW you do this is really up to you. 

### List of requirements for submission

1. `server.js` file that takes an arbitrary port number as a command line argument (i.e. I should be able to run it with `node server.js`. The port should default to 5000 if no argument is given.
2. Default API endpoint that returns `404 NOT FOUND` for any endpoints that are not defined.
3. Check endpoint at `/app/` that returns `200 OK`.
4. Endpoint `/app/roll/` that returns JSON for a default roll of two six-sided dice one time. Example output might look like: ``.
5. Endpoint `/app/roll/` should accept either JSON or URLEncoded data body for `sides`, `dice`, and `rolls`. Example URLEncoded string for data body: `?sides=6&dice=2&rolls=1`. Example JSON data body: `{"sides":6,"dice":2,"rolls":1}`.
6. Endpoint `/app/roll/:sides/` that returns JSON for a default number of rolls and dice with whatever number of sides is specified in the parameter. For example, `/app/roll/6/` should return JSON for two six-sided dice, rolled one time, whereas `/app/roll/10/` should return JSON for two ten-sided dice, rolled 1 time. The format of the resulting JSON should always look like: `{"sides":10,"dice":2,"rolls":1,"results":[6]}`.
6. Endpoint `/app/roll/:sides/:dice/` that returns JSON for a default number of rolls with whatever number of sides and dice specified in the parameters. For example, `/app/roll/6/2/` should return JSON for two six-sided dice, rolled one time, whereas `/app/roll/10/3/` should return JSON for three ten-sided dice, rolled 1 time. The format of the resulting JSON should always look like: `{"sides":10,"dice":3,"rolls":1,"results":[27]}`.
7. 6. Endpoint `/app/roll/:sides/:dice/:rolls/` that returns JSON for the specified number of rolls with whatever number of sides and dice specified in the parameters. For example, `/app/roll/6/2/1/` should return JSON for two six-sided dice, rolled one time, whereas `/app/roll/10/3/8/` should return JSON for three ten-sided dice, rolled 1 time. The format of the resulting JSON should always look like: `{"sides":10,"dice":3,"rolls":8,"results":[6,13,30,17,16,27,4,29]}`.
8. ALL endpoints should return HTTP headers including a status code and the appropriate content type for the response.
9. All of this should be in a Node package with `"main"` set to `server.js`.
10. The test script defined in `package.json` should be set to `"node server.js --port=5555"`
