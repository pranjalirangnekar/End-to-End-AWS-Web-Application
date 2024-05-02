Architected and Built an End-to-End AWS Web Application from Scratch

When I first started exploring cloud computing and various cloud platforms the first one to attract my attention was AWS- Amazon Web Services.

When I started exploring and working on AWS it was sometimes hard to know how to put all the “pieces” together — how to use the various services to create an application that could be used in the real world.

I designed and built a simple web application from scratch.


I picked up five different services available in AWS— Amplify, Lambda, IAM, API Gateway, and DynamoDB and worked on them.


So for this project, I built a website called Power of Maths where we could calculate the exponential values of any given and store those respective values in a database and this case DynamoDB.

STEP1:

A way to create /host a webpage


Creating an HTML page on a local machine and using amplify to host and deploy the web page

i. create a basic index html page

ii. Zip it

iii. Open As AMPLIFIER

iv. Host a new web app without git host

v. add the created zip file into the

vi. Save and deploy


vii. Now we have a live web page users can navigate to

Step 2: A way to do some math aka creating a math function.


I. got to the lambda function

ii. Create a python function and host it


Iii. create a test function to test our math function


iv. Now test it


Now so far we have a simple web page hosted on the amplifier and a lambda function in python to have a simple math function

STEP3:

A way to invoke the math function

Now for this, we are going to use API getaway


I. create an API

ii. Create a method of API

iii. Create a method of the lambda function.


iv. Enable CORS on the post


v. deploy the API

vi. Save the invoke URL (https://fyjrs0nqse.execute-api.ap-south-1.amazonaws.com/dev)

The flow of how this will work:


Let's test if this is working:


STEP 4:

Somewhere to store the math functions aka creating a database and also handle permissions.

We will be using DynamoDB


And for the permissions, we will be using IAM user


i. Create a table in dynamo db


ii. Go to additional info and save the ARN link

(arn:aws:dynamodb:ap-south-1:339403215164:table/powerofmathdatabse)

Now for permissions

i. Go to the lambda function and go to configure

ii. Go to the role name

iii. Add permissions

iv. Go to JSON and add Execution Role Policy

This is to allow various actions on dynamo db

v. Add arn


vi. Review policy

Now let’s update the lambda function to go directly to the database


Checking our table in dynamo db we can see our test value is saved


Now we need a connector between the amplifier and API getaway

i. We need to update the index.html page

ii. Add the API getaway link in the index page

iii. Now again zip the HTML file

iv. Now change it in the amplifier


Now as we see our web page has been updated and we are getting our results.


Now checking our database in dynamo db


It has stored all the values we have tried to run let’s just say to the power of 8 for something different when we click this 
calculate button that script here on our HTML page is going to call API gateway that’s then going to trigger the lambda function which
does the calculation that gets written to the database and then we’re going to get a message returned to us in the browser through API 
gateway so here we go calculate and the result is 256. all right that’s our completed application did.
