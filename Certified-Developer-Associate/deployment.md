# Deployment

# Elastic Beanstalk

## Configuration
Configuration options are applied from multiple sources with the following precedence, from highest to lowest:
  1. Settings applied directly to the environment
  2. Saved configurations-- settings for any options that are not applied directly to the environment are loaded from a saved configuration, if specified.
  3. Configuration files (.ebextensions) - Run in alphabetical order
  4. Default values

# Lambda

* A lambda version is a unique snapshot of the lambda code with its own ARN.
* Users can continue to use an existing version of the lambda while you make new versions.
* A qualified ARN (e.g. `arn:aws:lambda:aws-region:acct-id:function:helloworld:$LATEST`) refers to a particular version
* An unqualified ARN doesn't include any version information, so you can use this if you're not leveraging versioning. (e.g. `arn:aws:lambda:aws-region:acct-id:function:helloworld`)
* An alias can only point to a qualified ARN

# Serverless Application Model (SAM)

## Automating Deployments

* Deploys new version of your lambdas and creates aliases that point to the new versions
* Gradually shifts traffic to new version until satisfied it's working, or you can roll back
  - Canary: Shift traffic in two increments; A small amount at first then a delay before the rest.
  - Linear: Traffic is shifting in equal increments with equal delays between each increment
  - All-at-once: Fuck it, let's just do it and be legends
* Define pre-traffic and post-traffic test functions
* Rolls back the deployment if CloudWatch alarms
