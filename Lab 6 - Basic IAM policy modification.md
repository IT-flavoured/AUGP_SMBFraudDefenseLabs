# Lab 6 – Basic IAM policy modification

1.  Use the saved **Sign-in URL for IAM users in this account** link in your browser and log in using **XYZ-Admin** credentials. If created according to the lab instructions, use the information below:
    1.  IAM user name: **XYZ-Admin**
    2.  Password: **P@ssw0rd-SMBFraudDefense**
2.  Go to the **IAM** console
3.  On the left side of the screen, proceed to the **Users**
4.  Click on **XYZ-User** hyperlink
5.  Click on **Security credentials** tab
6.  In the **Multi-factor authentication (MFA)** section, click on **Assign MFA** device and proceed with instructions.

### *If you do not want to setup the MFA for the XYZ-User, remember to remove the condition requiring MFA from the JSON policy below. Although we suggest testing this condition first, and then modifying the policy to remove it.*

7.  On the left side of the screen, proceed to the **Policies**
8.  Click **Create policy**
9.  Click **JSON**
10.  Copy and paste the JSON policy below into the **Policy editor**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "ec2:*",
            "Resource": "*",
            "Condition": {
                "Bool": {
                    "aws:MultiFactorAuthPresent": "true"
                },
                "ForAllValues:StringLike": {
                    "ec2:InstanceType": [
                        "t2.*"
                    ],
                    "aws:RequestedRegion": [
                        "eu-west-1"
                    ]
                }
            }
        }
    ]
}
```

### *The policy allows using all actions for EC2 service, with conditions:*

### *Requirement of MFA usage*

### *Requirement for EC2 instance type: “t2.micro”*

### *Requirement for the Region: “eu-west-1”*

11.  Click **Next**
12.  Fill the Policy name textbox: **EC2_AllActions_WithConditions**
13.  **Skip description field** – although it is essential to describe the policy with such a vague name. You can fill this field with the short description above
14.  Click **Create policy**
15.  On the left side of the screen, proceed to the **User groups**
16.  Click on **XYZ-Users** hyperlink
17.  Click on **Permissions** tab
18.  Click on **Add permissions** and then **Attach policies**
19.  Find the recently created policy using the search bar: **XYZ-EC2_AllActions_WithConditions**
20. **Select checkbox** to the left of the policy and click **Attach policy**

### *You can now repeat the steps used to create the EC2 instance using XYZ-Admin user, but while logged in as XYZ-User user.*

### *Leave EC2 running for the checks done in later labs.*
