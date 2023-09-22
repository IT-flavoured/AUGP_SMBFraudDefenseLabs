# Lab 4 – IAM users and groups creation

### *For the purposes of this Lab, we suggest a very simple identity structure:*

![A diagram of a diagram Description automatically generated](media/703a140818b54ebf663734a5d53d5315.png)

### *Remember to design identity structure according to the business and technical requirements, while having scalability in mind!*

1.  Sign in to the AWS Management Console, as Root: <https://console.aws.amazon.com/>
2.  Go to the **IAM** console
3.  On the left side of the screen, proceed to the **Users**
4.  Click on **Create user**
5.  Proceed with the instructions based on the information below:
    1.  User name: **XYZ-Admin**
    2.  Provide user access to the AWS Management Console: **Enable**
    3.  User type: **I want to create an IAM user**
    4.  Console password: Custom password: **P@ssw0rd-SMBFraudDefense**
    5.  Users must create a new password at next sign-in: **Disable**
    6.  Click **Next**
    7.  Click **Next** (we skip permissions on the user level)
    8.  Click **Create user**

### *(In Retrieve password section you can email sign-in instructions. For lab purposes we will skip this)*

1.  Click **Return to users list** and then **Continue**
    1.  Repeat steps from a to h using user name: **XYZ-User**

### *For the purposes of this Lab, we are using IAM instead of Identity Center because of the small environment. For the multi-account environments and usage of AWS Organizations, we recommend using Identity Center, formerly known as AWS SSO.*

### *The password provided and skipping the password reset on the first sign-in is for easier workshop handling. In a regular environment allow users to create their own passwords, that are compliant with the password policy!*

1.  On the left side of the screen, proceed to the **User groups**
2.  Click on **Create group**
3.  Proceed with the instructions based on the information below:
    1.  User group name: **XYZ-Administrators**
    2.  Add users to the group: check **XYZ-Admin**
    3.  Attach permissions policies: find on the list and check **AdministratorAccess**
    4.  Click **Create group**

### For the purposes of this Lab, we attached AdministratorAccess policy to the Administrators group – remember that AdministratorAccess policy is very privileged permission, and you should minimize those if possible.

### Policies that include \* (asterisk) in the “Allow” section should be monitored closely due to the extensive nature.

1.  Click on **Create group** again
2.  Proceed with the instructions based on the information below:
    1.  User group name: **XYZ-Users**
    2.  Add users to the group: check **XYZ-User**
    3.  Attach permissions policies: **skip this section (do not attach any permissions)**
    4.  Click **Create group**
3.  Click on **Create group** again
4.  Proceed with the instructions based on the information below:
    1.  User group name: **XYZ-AllUsers**
    2.  Add users to the group: **check all the users on the list.**
    3.  Attach permissions policies: **skip this section (do not attach any permissions)**
    4.  Click **Create group**
5.  **Catching up with previous lab:**
    1.  In order to check/modify existing user, on the left side of the screen click **Users**
    2.  Select any user (click the hyperlink)
    3.  Click on the **Security credentials** tab
    4.  Verify the **Summary** (last console sign-in), **Multi-factor authentication (MFA)** (assigned MFA device) and **Access keys** (if created and age) sections
    5.  In order to have better information on the user’s access, check the **Access Advisor** tab

### *In Access Advisor, information about no service access should be the indicator of possibility of lowering the permission level of the user!*
