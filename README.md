https://catalog.workshops.aws/well-architected-security/en-US/3-detection/10-autonomous-monitoring-of-cryptographic-activity-with-kms

# Web App features
Infrastructure
* Deploy in ECS
* Autoscale through ALB by registering the IP of ECS tasks to the target group
* Assest stored in ECR
* RDS Backend 
* Symmetric Keys created in KMS

Monitoring
* Enable CloudTrail to monitor user Activities
* Store the CloudTrail logs to CloudWatch Log Groups
* Filter the logs by CloudWatch metrics filter
* Alarm by CloudWatch Alarm when KMS access failed

App
* Node.js and Express.js
* RDS secrets stored in Secret Manager
* Call Encrypt API
    * Read RDS DB Secrets from Secret Manager
    * Encrypt data with KMS Symmetric Keys
    * Store encrypted data in RDS
* Call Encrypt API
    * Read RDS DB Secrets from Secret Manager
    * Decrypt data with KMS Symmetric Keys
    * Return decrypted data to user

# Todos
- create better readme
- re-architect to serverless with lambda and dynamo
- re-write the code to follow ES2017 async/await
- convert CF to TF
- build generic pipeline