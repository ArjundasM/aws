#AWS LAMBDA FUNCTION TO START OR  STOP AWS EC2 INSTANCE

##Reasons for automatic start/stop

- Primarly to reduce cost
- We can able to start/stop instance within a certian time frame without manual trigger.


##Services involved in this scenario

1.IAM
2.Ec2

- Make sure one/more instances are running.
- Note down instance-IDs of the instances.
- Note down the aws region which deployed the instances

3.CloudWatch
- Create CloudWatch Event trigger
- Rule-->**Create new rule***
- Enter ***Rule name***
- Enter ***Rule description***
- Select rule type:***Schedule expression***
  Set cron or value like follows:

###Rate expressions
***Syntax***
```rate(value unit)```
Valid values: minute | minutes | hour | hours | day | days
Example: rate(5 minutes)
***Note***
```
If the value is equal to 1, then the unit must be singular. Similarly, for values greater than 1, the unit must be plural. For example, rate(1 hours) and rate(5 hour) are not valid, but rate(1 hour) and rate(5 hours) are valid.
```

###Cron Exoressions
***Syntax***
```cron(fileds)```

***Fileds***

|Field	         |Values	  |Wildcards     |
|---             |---|---|
|Minutes         |0-59            |, - * /       |
|Hours           |0-23            |, - * /       |
|Day-of-month    |1-31            |, - * ? / L W |
|Month           |1-12 or JAN-DEC |, - * /       |
|Day-of-week     |1-7 or SUN-SAT  |, - * ? L #   |
Year            1970-2199       , - * /

4.Lambda






