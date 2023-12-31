# Lab 2 - Basic Root account protection

1.  Sign in to the AWS Management Console, as Root: <https://console.aws.amazon.com/>
2.  On the navigation bar, choose your account name (top right corner), and then choose **Security credentials.**
3.  Check the **Access keys** section and ensure that there are no access keys created for the Root user
    1.  If access keys were created for the Root user, select them one by one, click on **Actions** and then click **Delete**
    2.  Active keys need to be deactivated first, and then they can be deleted

### *If Root user access keys are being used in the environment, check how they are utilized. Deactivation and deletion of the access key can cause problems in the environment but keeping them is a critical risk!*

4.  Check the **Multi-factor authentication (MFA)** section and ensure the MFA is enforced for the Root user
    1.  If the MFA has not been set up, click **Assign MFA device** and proceed with the instructions

### *Multi-factor authentication feature requires external device. You can choose from:*

- *Authenticator app – Authenticate using a code generated by an app installed on your mobile device or computer.*
- *Security Key – Authenticate using a code generated by touching a YubiKey or other supported FIDO security key.*
- *Hardware TOTP token – Authenticate using a code displayed on a hardware Time-based one-time password (TOTP) token.*

5.  On the navigation bar, choose your account name (top right corner), and then choose **Account.**
6.  Scroll down to check **the IAM user and role access to Billing information** and check status
    1.  If **Activated**, no action is necessary.
    2.  If **Deactivated**, click **Edit**, check the **Activate IAM Access** checkbox and then click **Update**
