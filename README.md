# Project Daylily: A Setp Function Demo using SNS (Simple Notification Service) and Wait state.

This is a simple demo of an AWS Step function using SNS (Simple Notification Service) and Wait state.

## Description

This sample project creates a step function with a task timer. It implements an AWS Step Functions state machine that implements a ```Wait``` state, and uses an AWS Step function task that sends an Amazon Simple Notification Service (Amazon SNS) notification. A ```Wait``` state is a state type that waits for a trigger to perform a single unit of work.

The entire stack is created using Serverless Framework (https://serverless.com).

![Project Daylily - Design Diagram](https://subhamay-projects-repository-us-east-1.s3.amazonaws.com/0086-daylily/daylily-architecture-diagram.png?)

![Project Daylily - Services Used](https://subhamay-projects-repository-us-east-1.s3.amazonaws.com/0086-daylily/daylily-services-used-sls.png?)

![Project Daylily - Workflow](https://subhamay-projects-repository-us-east-1.s3.amazonaws.com/0086-daylily/daylily-step-function.png?)

### Prerequisite

* Install node.js and serverless framework (If you don't have Node.js on your machine, install it first)
```
npm install -g serverless
```

* Install the serverless-step-functions plugin
```
npm install --save-dev serverless-step-functions
```
* Create a S3 bucket to be used as serverless deployment bucket and update the provider section in the serverless.yml.

### Installing

* Clone the repository.
```
git clone https://github.com/subhamay-cloudworks/0086-daylily-sls.git
```

* Modify provider section the serverless.yml file
```
provider:
  name: aws
  stackName: daylily-sls-stack
  deploymentBucket:
    name: <Your Serverless Deployment Bucket Name>
    serverSideEncryption: AES256
  runtime: python3.9
  stage: devl
  region: us-east-1
```

* Create a KMS Key in the region where you intend to deploy the stack and update the parameter section of the serverless.yml file

* Run the following command to deploy the stack
```
sls deploy --verbose
```

* Run the following command to delete the stack
```
sls remove --verbose
```

### Executing program

* Go to the Step Function Console and use the sample input and start the execution
```
{
    "waitSeconds": 10,
    "Message": "Testing Step Function - Task Timer (Lambda, Amazon SNS)"
}
```

## Help

Post message in my blog (https://blog.subhamay.com)

## Authors

Contributors names and contact info

Subhamay Bhattacharyya  - [subhamay.aws@gmail.com](https://blog.subhamay.com)

## Reference
https://docs.aws.amazon.com/step-functions/latest/dg/sample-project-transfer-data-sqs.html

## Version History

* 0.1
    * Initial Release

## License

None

## Acknowledgments
[AWS] (https://docs.aws.amazon.com/step-functions/latest/dg/task-timer-sample.html)

