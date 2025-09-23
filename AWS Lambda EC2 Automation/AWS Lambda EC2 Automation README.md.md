#**AWS Lambda EC2 Automation Lab**##

##**Overview**##

In this lab, I created and configured AWS Lambda functions to automate the management of EC2 instances. I used Python to write functions that can stop, start, and monitor EC2 instances, integrated IAM roles for proper permissions, and set up Amazon EventBridge triggers to schedule automated instance management.

**What I Did**

**Creating the Lambda Function**

· Created a Lambda function from scratch using the AWS Management Console
· Set the runtime to Python 3.10 and configured x86_64 architecture
· Named the function to describe its purpose (e.g., EC2 instance management)
· Configured basic IAM roles with necessary EC2 permissions

**Configuring Permissions**

· Attached the AmazonEC2FullAccess policy to the Lambda execution role
· Verified the IAM role had proper permissions to interact with EC2 instances
· Modified role permissions through the IAM console when needed

**Writing Python Code**

· Wrote Python code using the boto3 library to interact with EC2 instances
· Created functions to:
  · Stop specific EC2 instances by instance ID
  · Start specific EC2 instances by instance ID
  · List all instances and their current states
  · Automatically start any stopped instances
· Deployed the code and tested it using Lambda's test functionality

**Testing the Function**

· Executed the Lambda function to stop running EC2 instances
· Verified instance state changes in the EC2 console
· Modified the code to start instances and tested again
· Extended functionality to handle multiple instances simultaneously

**Adding EventBridge Triggers**

· Created a new Lambda function specifically for scheduled automation
· Added an EventBridge (CloudWatch Events) trigger
· Created a new rule named StartEC2_in_5_Minutes with a schedule expression
· Configured the rule to trigger every 5 minutes
· Set up the rule description to document its purpose

**Automated Instance Management**

· Stopped a running EC2 instance to test the automation
· Verified that the Lambda function automatically started the stopped instance within 5 minutes
· Confirmed the system could handle multiple instances and their states
· Validated that the scheduled trigger worked reliably

**Key Features**

· Automated EC2 Management: Stop and start instances on demand or on a schedule
· Event-Driven Execution: Used EventBridge to run Lambda functions periodically every 5 minutes
· Multi-Instance Support: Code can handle one or multiple EC2 instances simultaneously
· State Monitoring: Function checks instance states and takes appropriate actions
· CloudWatch Integration: All function executions are logged for monitoring and debugging

This project demonstrates practical AWS serverless automation for infrastructure management, providing a foundation for more complex cloud operations workflows.