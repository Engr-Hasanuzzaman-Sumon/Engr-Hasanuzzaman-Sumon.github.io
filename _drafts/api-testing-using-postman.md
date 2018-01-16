---
layout: post
title:  API testing using Postman
categories: testing
subcategory: Intermediate
---
All most every web developer or web tester are familiar with [Postman](https://www.getpostman.com/).
Postman is a Chrome add-on and Mac application which is used to fire requests to an API.
It is very lightweight, fast and easy to use. Using this tool we can make different kinds of HTTP requests – GET, POST, PUT, PATCH and DELETE.

In this post, I am going to show some features of *Postman* that I am using in my everday life.

1. Collection
  we can create Postman's collection that will contain all the related apis under one folder. 
  For every projct I create new collection.

postman-main

Variables
There are two types of variables – global and environment. Global variables are for all requests, environment variables are defined per specific environment which can selected from a drop-down or no environment can be selected. Environments will be discussed in details later in current port. Global variables are editable by small eye-shaped icon in the top right corner. Once defined variables can be used in request with format surrounded by curly brackets: {{VARIABLE_NAME}}.

postman-globals

Pre-Request Script
Postman allows users to do some JavaScript coding with which to manipulate the data being sent with request. One such example is when testing and API with security as explained in How to implement secure REST API authentication over HTTP post – SHA256 hash (build from apiKey + secretKey + timestamp in seconds) is sent as request parameter with the request. Calculating SHA256 hash is done with following pre-request script and then stored as global variable token.

1
2
3
4
5
var timeInSeconds = parseInt((new Date()).getTime() / 1000);
var sigString = postman.getGlobalVariable("apiKey") + 
    postman.getGlobalVariable("secretKey") + timeInSeconds
var token = CryptoJS.SHA256(sigString);
postman.setGlobalVariable("token", token);
Here CryptoJS library is used to create SHA256 hash. All available libraries in Postman are described in Postman Testing Sandbox page. Global variable {{token}} is then send as token request parameter.

postman-pre-request-script

Environments
Code shown above is working fine with just one set of credentials because they are stored as global variables. If you need to switch between different credentials this is where environments come in play. By switching environment and with no change in the request you can send different parameters to API. Environments are managed from Settings icon in the top right corner which opens menu with “Manage Environments” link.

postman-environments

Postman supports so called shared environments, which means whole team can use one and the same credentials managed centrally. It requires sign in and some plan though, but might be good investment in the long run.

In order to use environments pre-request script has to be changed to:

1
2
3
4
var timeInSeconds = parseInt((new Date()).getTime() / 1000);
var sigString = environment.apiKey + environment.secretKey + timeInSeconds
var token = CryptoJS.SHA256(sigString);
postman.setEnvironmentVariable("token", token);
Both apiKey and secretKey are read from environment. Environment can be changed from top right corner.

Nota bene: There is specific behaviour (I would not call it bug as it makes sense) in Postman. If select “No Environment” and fire request above Postman will automatically create environment with name “No Environment”. This is because it actually needs an environment to store variable into. This might be very confusing first time.

Post-Request Script
There is no such term defined in Postman. The idea is that in many cases you will need to do something with the response and extract variable from it in order to use it at later stage. This can be done in “Tests” tab. Example given bellow is to take all persons with API call and then to process response and at random select one id which is stored as global variable and then used in next request. You can put whatever JavaScript code you like in order to fulfil your logic.

1
2
3
4
var jsonData = JSON.parse(responseBody)
var size = jsonData.length
var index = parseInt(Math.random() * size)
postman.setGlobalVariable("userId", index);
postman-post-request

Then in subsequent request you can use GET call to URL: http://localhost:9000/person/get/{{userId}}

Tests
After response is received Postman has functionality to make verifications on it. This is done in “Tests” tab. Bellow is example on different verifications. Most interesting part is in case of JSON response it can be parsed to an array and then elements accessed by index and value jsonData[0].id or even iterated as shown bellow. Format is: tests[“TEST_NAME”] = BOOLEAN_CONDITION.

1
2
3
4
5
6
7
8
9
10
11
12
13
14
tests["Status code is 200"] = responseCode.code === 200;
 
tests["Response time is less than 200ms"] = responseTime < 200;
 
var expected = "email1@email.na"
tests["Body cointains string: " + expected] = responseBody.has(expected);
 
var jsonData = JSON.parse(responseBody);
var expectedCount = 4
tests["Response count is: " + expectedCount] = jsonData.length === expectedCount;
 
for(var i=1; i<=expectedCount; i++) {
    tests["Verify id is: " + i] = jsonData[i-1].id === i;
}
postman-test-response

postman-test-results

Nota bene: if you use responseTime verification you have to know that it measures just the TTFB (time to first bite) it does not measure time needed to transfer the data. If you have API with big responses or network is slow you may fire the request, wait a lot and then Postman shows very small response time which might be confusing.

Run from command line
In order to run Postman tests in command line as part of some CI process there is separate tool called Newman. It requires NodeJS to be installed and runs on NodeJS environment. It is very well described in How to write powerful automated API tests with Postman, Newman and Jenkins.

Code reuse between requests
It is very convenient some piece of code to be re-used between request to prevent copy/paste it. Postman does not support yet code re-use between requests. Good thing is that there is workaround for this. It is possible to do it by defining a helper function with verifications which is saved as global variable in first request from your test scenario:

1
2
3
4
5
6
7
8
9
10
11
12
13
postman.setGlobalVariable("loadHelpers", function loadHelpers() {
    let helpers = {};
 
    helpers.verifyCount = function verifyCount(expectedCount) {
        var jsonData = JSON.parse(responseBody);
        tests["Response count is: " + expectedCount] 
            = jsonData.length === expectedCount;
    }
 
    // ...additional helpers
 
    return helpers;
} + '; loadHelpers();');
Then from other requests helpers are taken from global variables and verification functions can be used:

1
2
var helpers = eval(globals.loadHelpers);
helpers.verifyCount(4);
See more in Reusing pre-request scripts across requests in a collection issue thread.
