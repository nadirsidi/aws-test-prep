# Development with AWS Services

## AWS Lambda

* A lambda ARN alias is a unique ARN that you can use to point to a particular version of a lambda function. (e.g. you could have a `helloworld:PROD` alias.)
* Event sources can be routed to an alias, allowing you to leverage a new version of your lambda function without changing the event source configuration

## API Gateway

* Stage variables are name-value pairs that you can define as configuration attributes associated with a deployment state of a REST API. They act like environment variables and can be used in your API setup and mapping templates.
* For example, you can have different versions of your API hit different backend web services as configured by stage variables (example.com vs. beta.example.com)
* Stage variables can also pass configuration parameters through to Lambda, e.g. read from a different DynamoDB table in a lower environment. 
