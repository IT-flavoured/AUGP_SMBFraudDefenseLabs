# Lab 3 – IAM basic security

1.  Sign in to the AWS Management Console, as Root: <https://console.aws.amazon.com/>
2.  Go to the **IAM** console *(Tip: use the search bar on top of the screen for faster navigation)*
3.  In the **IAM Dashboard** take a note of the **AWS Account** section.

### *For an easier use, you can edit the Account Alias. Make sure to save the Sign-in URL for IAM users in this account for the future use.*

4.  On the left side of the screen, proceed to the **Account settings**
5.  Check the **Password policy** section and click **Edit**
6.  Choose **Custom** to apply customized password requirements
7.  According to the best practices:
    1.  Edit **Password minimum length** to 14 or greater
    2.  Edit **Prevent password** **reuse** to 24

### *Remember that password policy should be aligned with the organizational requirements. Keep the best practices in mind, to ensure security!*

8.  Click **Save changes** after editing the data
9.  On the left side of the screen, proceed to the **Credential report**
10.  Click on **Download credentials report** and ensure:
    1.  Multi-factor authentication (MFA) is enabled for all IAM users that have a console password
    2.  Access keys are not setup during the initial user setup for all IAM users that have a console password
    3.  Access keys are rotated every 90 days or less
    4.  Credentials unused for 45 days or greater are disabled

### *Even though the users have not been created for lab purposes yet, make sure the Credential report is being analyzed periodically. In the next section, we will explain where the MFA and access keys created per user can be accessed and modified.*
