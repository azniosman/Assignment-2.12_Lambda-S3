# Assignment-2.12_Lambda-S3
Module 2.12 Assignment

## Answers

1.  **What is the purpose of the execution role on the Lambda function?**
    * The execution role grants the Lambda function permissions to access other AWS services. For example, if the Lambda function needs to read from or write to an S3 bucket, it requires permissions within its execution role.

2.  **What is the purpose of the resource-based policy on the Lambda function?**
    * The resource-based policy grants permissions to other AWS services or accounts to invoke the Lambda function. For example, if an S3 bucket is configured to trigger the Lambda function when a new object is created, the S3 service needs permission to invoke the function, and that permission is given by the resource based policy.

3.  **If the function is needed to upload a file into an S3 bucket, describe:**
    * **What is the needed update on the execution role?**
        * The execution role needs an IAM policy that grants `s3:PutObject` permission on the target S3 bucket.
    * **What is the new resource-based policy that needs to be added (if any)?**
        * No new resource-based policy is needed in this scenario. The resource-based policy is for services that invoke the lambda. The lambda itself invoking another service does not need it.
