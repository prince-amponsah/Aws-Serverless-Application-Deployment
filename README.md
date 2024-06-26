# Aws-Serverless-Application-Deployment
Deploying a web application on AWS using Serverless Services

A hands-on lab using aws services like Cloudfront, S3 Bucket, API Gateway, Lambda Functions and Dynamo DB

IAM ACTIONS TO TAKE: (
1. Create a service role Called ServerDynaLamb -
   i. Enable DynamoDBFullAccess - For Testing purposes - Apply the least privilage model when using the application in the public
   ii. Enable APIgate Full Privilages as well
Steps To Implement This Solutions:
1. Create 2 functions with Lambda
  i.  Retreieve Date from Dynamo DB Table - user the getStudents.py file
  ii. Insert Data to insert data into the Dynamo DB Table user the insertStudentsData.py file
Remember to deploy and run a test to comfirm its working ( Remember to attach the IAM Role we created so DynamoDB Doesn't reject the request.
3. Create a Dynamo DB Table
   i. Create a table in Dynamo DB - Preferable name it "StudentData" or anything you like to name it.
4. Create API Gateway - Give it a name of your choice:
   Select Eged-Optimized to help get the API accessed aroudn the world and not ONLY the region of the API(REGIONAL)
   i. Create 2 Methods -
     1. To Get From Dynamo DB Table through the GET Lambda Function ( GetData )
     2. POST - To send Data to the DynamoDB through the POST lambda funtion ( SendData)
  ii. Head to Resources and Enable CORS - Select POST and GET and Click Save
5. Create s3 Bucket in the same region as the other services
   Enable website hosting
   Head to permission and edit bucket policy to allow public access - Confirm and click save
   Head to bucket policy section and generate a policy to allow public read of the bucket data
   Upload the index.html and script.js files into the bucket
