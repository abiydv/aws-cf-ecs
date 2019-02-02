# AWS ECS Fargate Cluster
Use this template to create a ECS (Fargate backed) cluster with autoscaling policies.

## Prerequisites
Create the VPC using [vpc-stack](../vpc/) template. This template reads the exported values from the vpc-stack. 
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
