# Notes on Security

## API Gateway

* **AWS Web Application Firewall (WAF)** allows you to filter web requests based on IP address, geographic area, request size and/or string or regex patterns. These conditions can be put on the HTTP headers or the body of the request.

* The API Gateway resource policy allows you to control what principals can invoke the API (typically IAM user or role). They can also restrict by IP address and VPC. This is similar to the S3 bucket policy.

## AWS Systems Manager Parameter Store
* Secure, hierarchial storage for configuration data management and secrets management. Store plaintext or encrypted data.

## Amazon RDS

### Encryption
* RDS for Microsoft SQL Server support Transparent Data Encryption (TDE)-- automatic encryption on write and decryption on read
