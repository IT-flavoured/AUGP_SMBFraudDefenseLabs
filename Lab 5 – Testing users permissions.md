# Lab 5 – Testing users permissions

### *If signed in as Root, sign out from the AWS Console*

1.  Use the saved **Sign-in URL for IAM users in this account** link in your browser and log in using **XYZ-User** credentials. If created according to the lab instructions, use the information below:
    1.  IAM user name: **XYZ-User**
    2.  Password: **P@ssw0rd-SMBFraudDefense**
2.  Go to the **EC2** console
3.  Click on the **Launch instance**
4.  Proceed with the instructions based on the information below:
    1.  Name: **myEC2instance**
    2.  Application and OS Images (Amazon Machine Image): ensure **Amazon Linux 2023 AMI** is selected
    3.  Instance type: …

### *Despite seeing many errors before, the “Instance type” dropdown is not accessible due to the “An error occurred loading the data. Please refresh to try again.” error message. The lack of permissions the XYZ-User is currently using disallows for creation of EC2 instance.*

**Sign out** from AWS Console, and proceed with **XYZ-Admin** credentials:

5.  Use the saved **Sign-in URL for IAM users in this account** link in your browser and log in using **XYZ-Admin** credentials. If created according to the lab instructions, use the information below:
    1.  IAM user name: **XYZ-Admin**
    2.  Password: **P@ssw0rd-SMBFraudDefense**
6.  Go to the **EC2** console
7.  Click on the **Launch instance**
8.  Proceed with the instructions based on the information below:
    1.  Name: **myEC2instance**
    2.  Application and OS Images (Amazon Machine Image): ensure **Amazon Linux 2023 AMI** is selected
    3.  Instance type: ensure **t2.micro** is selected
    4.  Skip the other specification and click **Launch instance** on the left
    5.  In the **Create key pair** prompt select **Proceed without key pair** and then click **Proceed without key pair**
9.  You should see the green prompt “**Success - Successfully initiated launch of instance (**\<instanceID\>\*\*)\*\*”
10.  Click on View all instances at the bottom of the screen.
11.  You can skip waiting for the **Instance state** to change to **Running**,– proceed with instance termination
12.  **Select the instance** (checkbox) and click **Instance state** button.
13.  Click **Terminate instance** and confirm by clicking **Terminate**
14. In order to keep environment clean, after the **Instance state** changes to **Terminated**, you can **delete the automatically created security group:**
    1.  On the left, in the **Network & Security** section, click **Security Groups**
    2.  **Check the security group created with the instance** (if it is first instance, the name will be **launch-wizard-1**), click on **Actions** and then **Delete security groups**
    3.  Confirm by typing “**delete**” in the textbox

**XYZ-Admin** using the elevated permissions succeeded in creation of the EC2 instance. **On purpose there was no region selection mentioned in the instructions** – if not selected otherwise, the instance could have been launched in **US East (N. Virginia)**, which could have been not compliant with the company policy, or just the administrator’s mistake. **We will be modifying permissions in the next lab.**
