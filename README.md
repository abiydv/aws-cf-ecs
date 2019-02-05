# AWS ECS Fargate Cluster
[![CodeFactor](https://www.codefactor.io/repository/github/abiydv/aws-cf-ecs/badge)](https://www.codefactor.io/repository/github/abiydv/aws-cf-ecs)

![cli](https://github.com/abiydv/ref-docs/blob/master/images/logos/aws-cli_small.png)
![cf](https://github.com/abiydv/ref-docs/blob/master/images/logos/aws-cf_small.png)
![iam](https://github.com/abiydv/ref-docs/blob/master/images/logos/aws-iamrole_small.png)
![as](https://github.com/abiydv/ref-docs/blob/master/images/logos/aws-autoscaling_small.png)
![cwe](https://github.com/abiydv/ref-docs/blob/master/images/logos/aws-cwevent_small.png)
![ecsf](https://github.com/abiydv/ref-docs/blob/master/images/logos/aws-ecs-fargate_small.png)
![elb](https://github.com/abiydv/ref-docs/blob/master/images/logos/aws-elb_small.png)
![cw](https://github.com/abiydv/ref-docs/blob/master/images/logos/aws-cw_small.png)


Use this template to create a ECS (Fargate backed) cluster with load balancer, IAM role, autoscaling policies etc.

## Prerequisites
Create the VPC using [vpc-stack]() template. This template reads the exported values from the vpc-stack. 
It launches the load balancer in public subnets and ECS Containers in the private subnets.

## How to use
Checkout the repository and execute from cli. Remember to select the correct profile
```
aws cloudformation validate-template --template-body file://ecs-stack.yaml \
  --profile aws-dev-account --region us-east-1 
```
This should display the parameters - validating the template syntax is fine. Next, create the stack

```
aws cloudformation create-stack --stack-name ecs-stack --template-body file://ecs-stack.yaml \
  --profile  aws-dev-account --region us-east-1
```
Or, copy the template and create the stack from Cloudformation console.

## Alternative
You could also create the same set of resources using Terraform, if you prefer. Take a look at my [Terraform repo](https://github.com/abiydv/terraform/tree/master/ecs)

## Contact
Drop me a note or open an issue if something doesn't work out.

Cheers! :thumbsup:
