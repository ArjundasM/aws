# AWS LAMBDA FUNCTION TO START OR  STOP AWS EC2 INSTANCE

## Reasons for automatic start/stop

- Primarly to reduce cost
- We can able to start/stop instance within a certian time frame without manual trigger.


## Services involved in this scenario

### 1.IAM

### 2.Ec2

- Make sure one/more instances are running.
- Note down instance-IDs of the instances.
- Note down the aws region which deployed the instances

### 3.CloudWatch

- Create CloudWatch Event trigger
- Rule-->**Create new rule***
- Enter ***Rule name***
- Enter ***Rule description***
- Select rule type:***Schedule expression***
- And enable the trigger.

Use following link to create custom expressions:
[a link](https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/ScheduledEvents.html)


