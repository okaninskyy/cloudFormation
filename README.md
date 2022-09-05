## AWS Networking Fundamentals in CloudFormation
This is a sample of AWS CloudFormation template to learn how to declare specific AWS resources or solve a particular use case.



![Alt text](img/cloud_formation_task.jpg?raw=true "Title")



## Prepare to work with AWS CLI

#### install awscli:  
    pip3 install awscli --upgrade --user
#### configure awscli: 
    aws configure

## Usage

#### Create a key pair and download access key:
    aws ec2 create-key-pair --key-name MyKeyPair --query 'KeyMaterial' --output text > MyKeyPair.pem


## Building

#### Lets validate our template:
    aws cloudformation validate-template --template-body file://1.yml

#### Lets create stack:
    aws cloudformation create-stack --stack-name l1 --template-body file://1.yml

#### Lets create stack with parametrs
    aws cloudformation create-stack --stack-name l1 --template-body file://1.yml --parameters ParameterKey=KeyName,ParameterValue=MyKeyPair

#### Check if the stack we created via template is completed successfully
    aws cloudformation describe-stacks --stack-name l1
    aws cloudformation list-stack-resources --stack-name l1
    aws cloudformation describe-stack-resources --stack-name l1
    aws cloudformation describe-stack-events --stack-name l1

#### Lets clean 
    aws cloudformation delete-stack --stack-name l1


## Additional Resources
In the *AWS CloudFormation User Guide*, you can view more information about the following topics:

- Learn how to use templates to create AWS CloudFormation stacks using the [AWS Management Console](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-create-stack.html) or [AWS Command Line Interface (AWS CLI)](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-cli-creating-stack.html).
- To view all the supported AWS resources and their properties, see the [Template Reference](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-reference.html).
