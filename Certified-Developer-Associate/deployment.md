# Deployment

# Lambda

* A lambda version is a unique snapshot of the lambda code with its own ARN.
* Users can continue to use an existing version of the lambda while you make new versions.
* A qualified ARN (e.g. `arn:aws:lambda:aws-region:acct-id:function:helloworld:$LATEST`) refers to a particular version
* An unqualified ARN doesn't include any version information, so you can use this if you're not leveraging versioning. (e.g. `arn:aws:lambda:aws-region:acct-id:function:helloworld`)
* An alias can only point to a qualified ARN
