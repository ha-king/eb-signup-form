# Elastic Beanstalk SignUp Form (Express)

This webform uses the [Express](https://expressjs.com/) framework and [Bootstrap](http://getbootstrap.com/) to build a simple, scalable customer signup form that is deployed to [AWS Elastic Beanstalk](http://aws.amazon.com/elasticbeanstalk/). The application stores data in [Amazon DynamoDB](http://aws.amazon.com/dynamodb/) and publishes notifications to the [Amazon Simple Notification Service (SNS)](http://aws.amazon.com/sns/) when a customer fills out the form.

## Features
### Themes
The code includes several Bootstrap themes from [bootswatch.com](http://bootswatch.com/). You can dynamically change the active theme by setting the THEME environment variable in the [Elastic Beanstalk Management Console](https://console.aws.amazon.com/elasticbeanstalk):

![](misc/theme-flow.png)

Installed themes include:

* [amelia](http://bootswatch.com/amelia)
* [default](http://bootswatch.com/default)
* [flatly](http://bootswatch.com/flatly)
* [slate](http://bootswatch.com/slate)
* [united](http://bootswatch.com/united)

#### Ohio region only
### Installation Guide
1. <a href="https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=VPC-EBS-SignUp&templateURL=https://s3.us-east-2.amazonaws.com/infascination-public-ohio/cfn-templates/ec2-ebs-signup.template" target="_blank">![Launch](./img/launch-stack.png?raw=true "Launch")</a>
1. Click **Next** to proceed with the next step of the wizard.
1. Specify a name and all parameters for the stack.
1. Click **Next** to proceed with the next step of the wizard.
1. Click **Next** to skip the **Options** step of the wizard.
1. Check the **I acknowledge that this template might cause AWS CloudFormation to create IAM resources.** checkbox.
1. Click **Create** to start the creation of the stack.
1. Wait until the stack reaches the state **CREATE_COMPLETE**
1. Copy Bastion Host public IP from the KubeStack outputs tab

### Updating EBS
1. Run `eb deploy` to deploy to production

### Clean Up
1. Run `eb terminate --all` to clean up.
