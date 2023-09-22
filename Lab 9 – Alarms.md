# Lab 9 – Alarms

### *At first we will setup a billing alarm using AWS Budgets*

### *If signed in as XYZ-Admin, sign out from the AWS Console*

1.  Sign in to the AWS Management Console, as Root user (Root): <https://console.aws.amazon.com/>
2.  Go to **Billing** console
3.  On the left side of the screen, proceed to the **Billing preferences**

### *If Receive CloudWatch billing alerts is enabled (status Delivered) it cannot be disabled – instruction below:*

1.  On the **Alert preferences** section, ensure that **Receive CloudWatch billing alerts** is enabled (set to **Delivered**)
    1.  If not, click **Edit** and check **Receive CloudWatch billing alerts**
    2.  Click **Save preferences**
2.  On the left side of the screen, proceed to the **Budgets**
3.  Click on the **Create a budget**
4.  On the **Budget setup** section, ensure **Use a template (simplified)** is selected
5.  On the **Templates** section, select **Monthly cost budget**
6.  Proceed with the instructions based on the information below:
    1.  Budget name: **XYZ-Monthly 5 USD Budget**
    2.  Enter your budgeted amount (\$): **5.00**
    3.  Email recepients: **enter a valid email address of your choice**
    4.  Click **Create budget**

### *The alarm related to billing can be also setup using CloudWatch Alarm. Instead we will provide instructions of CloudWatch Alarm based on the Root Account usage, according to the configured CloudTrail*

1.  Go to **CloudWatch** console
2.  On the left side of the screen, click **Logs**, then click **Log groups**
3.  Click **xyz-cloud-watch-root-usage-alarm** hyperlink, log group previously created
4.  Click **Actions** and select **Create metric filter**
5.  In the Filter pattern textbox enter the text below:

```
{ $.userIdentity.type = "Root" && $.userIdentity.invokedBy NOT EXISTS && $.eventType != "AwsServiceEvent" }
```

1.  Click **Next**
2.  Proceed with the instructions based on the information below:
    1.  Filter name: **XYZ-RootUsage**
    2.  Metric namespace: **XYZ-CloudTrailMetrics**
    3.  Metric name: **XYZ-RootUsageCount**
    4.  Metric value: **1**
    5.  Click **Next**
    6.  Review the information and click **Create metric filter**
3.  Ensure **Metric filters** tab is selected
4.  Select **XYZ-RootUsage** metric filter and click **Create alarm**
5.  On the **Conditions** section, select:
    1.  Whenever XYZ-RootUsageCount is... **Greater/Equal**
    2.  than… **1**
6.  Click **Next**
7.  Under **Select a notification to the following SNS topic** select **Create new topic**
8.  Proceed with the instructions based on the information below:
    1.  Create a new topic… **XYZ-RootUsageAlarmTopic**
    2.  Email endpoints that will receive the notification… **enter a valid email address of your choice**
    3.  Click **Create topic**
    4.  Click **Next**
    5.  Alarm name: **XYZ-RootUsageAlarm**
    6.  Click **Next**
    7.  Review the information and click **Create alarm**

### *You will receive an email by AWS SNS to confirm the subscription.*

### *After confirmation to the alarm subscription, you will receive an email alert for root usage, after logging in as root user. For testing purposes we will use Root user in the next section.*
