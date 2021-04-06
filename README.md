1. Set up SSH keys using `ssh-keygen -t rsa`. 

   Print out the result using `cat directory/fileName.pub`. 

   Use the printed SSH key to establish connection with your github account, through the security settings in your github account. 

   Finally, clone your git repository to Cloud9 environment. 

   Note: The `directory/fileName.pem` is the public key file in the output of the SSH key generation process. And you have to save the printed result. 

2. Create a IAM role through the IAM web service with Administrator Access to allow AWS Lambda to call other services on your behalf. 

   Here is how to create a AWS SAM Service. In the cloud9 console, type the commands below and follow the instructions at each step according to the output. 

   a. `sam init`

   Choices: AWS Quick Start Templates, Image, python3.8-base 

   b. `sam build`

   c. `sam local build`

   d. `sam deploy --guided`

   e. `sam local invoke`: to test the function. 

   f. `sam local start-api`: to test the api. 

   But you don't have to create an entire SAM service, you could just create a AWS Lambda function directly from the AWS Lambda website. You could see that function in your cloud9 environment. 

3. Create a Simple Queue Service called producer through the AWS management console, which could send and receive messages. 

4. Create a table using DynamoDB, which could scale automatically. 

   This table should be called "fang" according to the code. 

5. Set up Trigger for the Lambda Function at 1 minute rate through the lambda function website. Set the trigger to be the CloudWatch Event. 

   By this step, we have already set up the CloudWatch Timer, Producer Lambda Function, DynamoDB database, and Simple Queue Service. Next, we will build the consumer lambda function. 

6. Build the Consumer Lambda function and add the Simple Queue Service created before as the trigger for the function. Then, we could observe that the messages that comes to the producer SQS has been drained very quickly.  

7. Check the Results in S3 bucket. 
