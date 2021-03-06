# Configuring AWS Lambda Functions<a name="lambda-configuration"></a>

You can use the AWS Lambda API or console to configure settings on your Lambda functions\. [Basic function settings](resource-model.md) include the description, role, runtime, and role that you specify when you create a function in the Lambda console\. You can configure more settings after you create a function, or use the API to set things like the handler name, memory allocation, and security groups during creation\.

To keep secrets out of your function code, store them in the function's configuration and read them from the execution environment during initialization\. [Environment variables](env_variables.md) are always encrypted at rest, and can be encrypted in transit as well\. Use environment variables to make your function code portable by removing connection strings, passwords, and endpoints for external resources\.

[Versions and aliases](versioning-aliases.md) are secondary resources that you can create to manage function deployment and invocation\. Publish versions of your function to store its code and configuration as a separate resource that cannot be changed, and create an alias that points to a specific version\. Then you can configure your clients to invoke a function alias, and update the alias when you want to point the client to a new version, instead of updating the client\.

To use your Lambda function with AWS resources in an Amazon VPC, configure it with security groups and subnets to [create a VPC connection](vpc.md)\. Lambda uses [elastic network interfaces](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_ElasticNetworkInterfaces.html) \(ENIs\) to create the connection, so you need to ensure that your account has enough ENI capacity to handle the number of connections made as your function scales up under load\.

**Topics**
+ [Basic AWS Lambda Function Configuration](resource-model.md)
+ [AWS Lambda Environment Variables](env_variables.md)
+ [AWS Lambda Function Versioning and Aliases](versioning-aliases.md)
+ [Configuring a Lambda Function to Access Resources in an Amazon VPC](vpc.md)