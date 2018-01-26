# node-google-oauth2-jwt
sample nodejs api with mongodb database and passportjs for authentication using passport-google-oauth20 and jwt tokens.


## Prerequisites

* Obtain credentials from google. [Follow these instructions if you need help](https://youtu.be/9x66l93iEW0?t=1m4s)

* You will also need a mongoDB database to save users. [Instructions for a free mlab database ](https://youtu.be/ySFXduSdpxs)

* Edit google and mongodb credentials in ```config/keys.js``` file.

```javascript
module.exports = {
    google: {
        clientID: '',
        clientSecret: ''
    },
    mongo: {
        mongodbUri: ''
    }
};
```

```javascript 
npm install
```
```javascript 
npm start
```


## How it works

Use [Postman](https://www.getpostman.com/) or any other api testing tool for the following section. 

First we are going to make a GET request to our google authentication endpoint ```/auth/google``` which will redirect the user to the google login page. After google successfully authenticates the user it will redirect to our callback endpoint with the user's profile information such as googleId, email etc... now we can save the user in the database or retrieve existing user info and redirect to our auth-success endpoint ```/auth-success``` where we issue a jwt token.

We can verify the token validity by making a GET request to the ```/verify``` endpoint. Don't forget to add the attach the authorization header to the request.

![](https://github.com/gasparrobi/node-google-oauth2-jwt/blob/master/postman.png?raw=true)


## Useful beginner resources


[mongoDB youtube tutorial](https://youtu.be/pWbMrx5rVBE)

[mongoose docs](http://mongoosejs.com/docs/)

[passportjs-google-oauth2-strategy youtube tutorial](https://www.youtube.com/watch?v=sakQbeRjgwg&list=PL4cUxeGkcC9jdm7QX143aMLAqyM-jTZ2x)

[passport-jwt youtube tutorial](https://youtu.be/7nafaH9SddU)
