# AWS LAMBDA FUNCTION TO START OR  STOP AWS EC2 INSTANCE

## Reasons for automatic start/stop

- Primarly to reduce cost
- We can able to start/stop instance within a certian time frame without manual trigger.


## Services involved in this scenario

### 1.IAM

- Create an IAM role for lambda function to access ec2 resources

### 2.Ec2

- Make sure one/more instances are running.
- Note down instance-IDs of the instances.
- Note down the aws region which deployed the instances

### 3.Lambda

- Create a function ***Author from scratch***
- Enter function name
- Select Runtime: Python.X
- Under Permissions:***Select existing role*** and select Previously created IAM role.
- Set ***Time out*** to 20s
- Remove auto generated code and add the ***start/stop-aws-ec2-instance.py** as Function code 

### 4.CloudWatch

- Create CloudWatch Event trigger
- Rule-->**Create new rule***
- Enter ***Rule name***
- Enter ***Rule description***
- Select rule type:***Schedule expression***
- And enable the trigger.

Use this link to create custom expressions:[link](https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/ScheduledEvents.html)
