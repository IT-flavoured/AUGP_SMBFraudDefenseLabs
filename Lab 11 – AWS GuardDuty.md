# Lab 11 – AWS GuardDuty

### *GuardDuty prices are based on the number of analyzed AWS CloudTrail events and S3 logs. There will also be costs incurred from S3 protection or EKS protection, if configured.*

### *GuardDuty comes with a 30 day free trial which allows you access to all services and detection findings.*

### *If signed in as XYZ-Admin, sign out from the AWS Console*

1.  Sign in to the AWS Management Console, as Root user (Root): <https://console.aws.amazon.com/>
2.  Check email for the alarm setup in the previous lab
3.  Go to **GuardDuty** console
4.  **Ensure you are in the region with EC2 instance running from the previous lab**
5.  Click **Get Started**
6.  Click **Enable GuardDuty**
7.  After some time after initial setup, you should be able to explore **Findings**

### *Disable GuardDuty by going into the Settings on the GuardDuty console, and clicking on Disable button on the Disable GuardDuty section!*

### *After finishing with the labs, remember to clean up the environment, to prevent unnecessary costs. Services used, for easier cleanup navigation:*

- **IAM**
- **EC2**
- **CloudTrail**
- **S3**
- **CloudWatch**
- **Amazon SNS**
- **GuardDuty**
