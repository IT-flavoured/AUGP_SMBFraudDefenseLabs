# Lab 7 – CloudTrail

### *By default, CloudTrail will store events for the last 90 days in Event History. However, it is a security best practice to store events in a permanent, on-going record in a Trail.*

### *If signed in as XYZ-User, sign out from the AWS Console*

1.  Use the saved **Sign-in URL for IAM users in this account** link in your browser and log in using **XYZ-Admin** credentials. If created according to the lab instructions, use the information below:
    1.  IAM user name: **XYZ-Admin**
    2.  Password: **P@ssw0rd-SMBFraudDefense**
2.  In the top right corner ensure **Europe (Ireland) eu-west-1** region is selected

### *We suggest to periodically check and ensure in which region you are operating. Remember that among others IAM, Trusted Advisor services are global, and S3 service is global with region selected on the S3 bucket level.*

3.  Go to the **CloudTrail** console
4.  On the left side of the screen click **Trails** and then click **Create trail**

### *If this is the first CloudTrail on the account, clicking Create a trail button will lead to quick trail setup. We will skip that and go through the full creation.*

5.  Proceed with the instructions based on the information below:
    1.  Trail name: **XYZ-Trail**
    2.  Storage location: **Create new S3 bucket**
    3.  Trail log bucket and folder: leave default value
    4.  Log file SSE-KMS encryption: ensure **Enabled** is checked
    5.  Ensure **New** is selected
    6.  AWS KMS alias: **XYZ-CloudTrailKey**
    7.  Log file validation: ensure **Enabled** is checked
    8.  CloudWatch Logs: check **Enabled**
    9.  Ensure **New** is selected
    10. Log group name: modify default value to **xyz-cloud-watch-root-usage-alarm**
    11. Ensure **New** is selected
    12. Role name: **XYZ-CloudTrailRoleForCloudWatchLogs**
    13. Click **Next**
    14. Event type: ensure only **Management events** is checked
    15. Management events: ensure **Read** and **Write** are checked
    16. Click **Next**
    17. Review the information and click Create trail
