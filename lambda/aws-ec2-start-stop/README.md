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

  Set cron or value expressions like follows:

Rate expressions
================

***Syntax***

```rate(value unit)```

Valid values: minute | minutes | hour | hours | day | days

Example: rate(5 minutes)

Cron Exoressions
================

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
|Year            |1970-2199       |, - * /       |

* The , (comma) wildcard includes additional values. In the Month field, JAN,FEB,MAR would include January, February, and March.

* The - (dash) wildcard specifies ranges. In the Day field, 1-15 would include days 1 through 15 of the specified month.

* The * (asterisk) wildcard includes all values in the field. In the Hours field, * would include every hour. You cannot use * in both the Day-of-month and Day-of-week fields. If you use it in one, you must use ? in the other.

*  The / (forward slash) wildcard specifies increments. In the Minutes field, you could enter 1/10 to specify every tenth minute, starting from the first minute of the hour (for example, the 11th, 21st, and 31st minute, and so on).

* The ? (question mark) wildcard specifies one or another. In the Day-of-month field you could enter 7 and if you didn't care what day of the week the 7th was, you could enter ? in the Day-of-week field.

* The L wildcard in the Day-of-month or Day-of-week fields specifies the last day of the month or week.

* The W wildcard in the Day-of-month field specifies a weekday. In the Day-of-month field, 3W specifies the day closest to the third weekday of the month.

* The # wildcard in the Day-of-week field specifies a certain instance of the specified day of the week within a month. For example, 3#2 would be the second Tuesday of the month: the 3 refers to Tuesday because it is the third day of each week, and the 2 refers to the second day of that type within the month.

***Limits***

* You can't specify the Day-of-month and Day-of-week fields in the same cron expression. If you specify a value (or a *) in one of the fields, you must use a ? (question mark) in the other.

* Cron expressions that lead to rates faster than 1 minute are not supported.

4.Lambda






