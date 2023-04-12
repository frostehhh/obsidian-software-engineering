https://github.com/acantril/learn-cantrill-io-labs/tree/master/00-aws-simple-demos/aws-dynamodb-lambda-trigger

DynamoDB has an enabled stream that allows other entities to listen to table updates. In this demo, we have a trigger configured that'll invoke a Lambda function. This lambda function uses SNS to publish via the Adoption-Alerts topic where we have one subscriber which is a personal email