# Development with AWS Services

## AWS Lambda

* A lambda ARN alias is a unique ARN that you can use to point to a particular version of a lambda function. (e.g. you could have a `helloworld:PROD` alias.)
* Event sources can be routed to an alias, allowing you to leverage a new version of your lambda function without changing the event source configuration
