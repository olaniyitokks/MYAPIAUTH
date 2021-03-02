# API AUTHENTICATION

This exercise extensively explains and details my testing strategy against API's

## Getting Started

These instructions will explain how to install any dependencies, software, and access the public API i used for this exercise.

### Prerequisites
* Click the hyperlink to download and install <a href="https://www.postman.com/downloads/" target="_blank">Postman</a> (select bit size depending on computer 34/64bit......i will be using 64-bit for this exercise.)
* For this exercise i will be using <a href="https://rapidapi.com/community/api/open-weather-map/" target="_blank">'RapidAPI'</a> Public API.
* This Public API is free but new users would have to create a new an account to have access to the APIKey
* Navigate to "subscribe to test" on the webpage to signup and get full access to this API.
* This particular API allows you to get weather data in any location on the earth.


## Running the tests
#### Authenticating against an API and reusing the token
1. Launch/Open Postman Desktop App
2.  On the left tab of postman, Click 'create new collection' and name it. for this exercise i named mine 'TEST'
3. Paste THE API URL
![URL](https://github.com/olaniyitokks/APIAUTH/blob/main/URL.PNG)
4. Navigate to Authorization Tab, then click on the drop down ribbon to select API Key 
Authentication method determines type of authorization 
5. In our API, under headers we have our API keys
![authentication1](https://github.com/olaniyitokks/APIAUTH/blob/main/Authentication1.PNG)
6. Input the api key and value.......NOTE: The 'RAPIDAPI' API-key is unique to each subscribers on this public api....hence the token/key is re-useable!
![authentication](https://github.com/olaniyitokks/APIAUTH/blob/main/authentication.PNG)

#### Making GET/POST requests
>Continued.... from API Auth above
1. Check method (POST/PUT/GET/DELETE)...... for this exercise i will be using GET
![get1](https://github.com/olaniyitokks/APIAUTH/blob/main/get1.PNG)
2. Click the params tab and input the parameters relevant to this API from the public API
![get2](https://github.com/olaniyitokks/APIAUTH/blob/main/get2.PNG)
![get3](https://github.com/olaniyitokks/APIAUTH/blob/main/get3.PNG)
3. Click "SEND" to excute the Get Request and we get this information back from the public API:
![get_info1](https://github.com/olaniyitokks/APIAUTH/blob/main/get_info1.PNG)
![get_info2](https://github.com/olaniyitokks/APIAUTH/blob/main/get_info2.PNG)


#### Performing post request validation tests
>Continued from GET Requests above.
1. Using the same parameters and API-Key from the steps above i am going to attempt to perfom a POST request.
* this is to validate my test.....NB: This particular 'RAPIDAPI' API that i chose for this exercise is GET only. So in order to validate that i am going to test for POST REQUEST
2. Change from GET ---> POST request and input the API-key and value 
3. Since this API is GET only.....i shouldnt be able to do post requests
![post_info](https://github.com/olaniyitokks/APIAUTH/blob/main/post_info.PNG)


#### Ability to switch environments (dev/prod)
1. On the left tab of postman, 'Click Create New Environment,' and create 2 new environments.
* Name them DEV and PROD respectively.
![environment](https://github.com/olaniyitokks/APIAUTH/blob/main/environments.PNG)

2. To operate in these 2 environments i am going to assign and call variables for APIKey and the API baseURL in "PROD Environment"
![prod](https://github.com/olaniyitokks/APIAUTH/blob/main/prod.PNG)

4. In the Development environment i am going to assign variables to the APIkey only!
![dev](https://github.com/olaniyitokks/APIAUTH/blob/main/dev.PNG)
5. PROD environment with new assigned variables (BASEURL AND API-KEY) and GET request working
![prod_info](https://github.com/olaniyitokks/APIAUTH/blob/main/prod_info.PNG)
6. DEV environment with new assigned variable (API-KEY) and GET request working 
![dev_info](https://github.com/olaniyitokks/APIAUTH/blob/main/dev_info.PNG)

# Strategy
1. Verify correct HTTP status code.
2. Verify response payload: Check valid JSON body and correct field names, types, and values — including in error responses.
3.  Verify response headers
4.  Verify correct application state
5.  Verify basic performance sanity
6.  After all these checked out i went ahead with Basic positive tests like i did with my GET Request since the API is supposed to be GET only.
7.  Extended positive testing with optional parameters.
8.  Negative testing with valid input like i did by attempting a POST request on my GET ONLY Public API
9.  Negative testing with invalid input and destructive testing.
