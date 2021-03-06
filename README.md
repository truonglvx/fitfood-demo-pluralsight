This is a proof-of-concept example for tying several APIs together, based on Jeremiah Cohick's fitbit-hapi-demo.

It uses:
- Fitbit
- Twilio (to send SMS's to remind you to step it up when you're lagging)

For the OAuth piece:
This is a proof of concept example for using the Fitbit Web API. It demonstrates:
- Obtaining consent from a user to make requests to the Fitbit Web API using OAuth 2.0 Authorization Code Flow
- Subscribing to changes in the user's activity data
- Receiving notifications when the user's activity data is updated

This example app uses NeDB, a flat-file database similar to Mongo. It's meant to be easy to demo, not highly scalable.

This example assumes you're using Node.js 4.2.x

# To run on Modulus:
- Download the modulus toolkit using `npm install -g modulus`
- `modulus signup`
- `modulus login` from the root directory of the repository
- `modulus project create` to create a new project.  Name it as you wish.
- `modulus deploy` from the root directory of the repository to deploy the code, which will give you your modulus server name.

## Create a new application in Fitbit
- Visit https://dev.fitbit.com/apps
- Create a new application
- Set your OAuth redirect URI to: your-modulus-server-here/signin
- Set your subscriber endpoint URI to: your-modulus-server-here/webhook-receiver

## Set environment variables on Modulus
Set the environment variables using the instructions at http://help.modulus.io/customer/portal/articles/1701180-using-environments-variables
- FITBIT_OAUTH2_CLIENT_ID
- FITBIT_OAUTH2_CLIENT_SECRET
- COOKIE_PASSWORD

## Get a Twilio account from www.twilio.com, and set the following variables in modulus:
- TWILIOSID
- TWILIOAUTHTOKEN
- TWILIOPHONENUMBER

## Set your phone number for SMS Messages in Modulus
- USERPHONENUMBER

(PORT and CLOUD_DIR will be automatically added by Modulus)

