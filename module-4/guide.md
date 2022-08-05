## Configuring Cross-Account Access

**Assuming Account IDs**
> Production AWS Account ID: 1111111111111 
> and DEV AWS Account ID: 2222222222222

**Steps on Prod Account**

A1)-Create S3 Bucket and update Bucket name in next step IAM policy.

A2)-Create IAM Policy (see prod-role-policy.json)

A3)-Create Create IAM Role and attach policy wiht the role -Step-A2

A4)-Get IAM Role ARN, it will be used in Step-B2

**Steps on Dev Account**

B1)-Create IAM Policy (see dev-user-policy.json), also update Role ARN, from step A4.

B2)-Create IAM Create User and attach policy-step-B1

Now you are ready to login.

**Console Access**

C1)-Login with below url

https://2222222222222.signin.aws.amazon.com/console

C2)-After login click Switch Role from Top right side.

Again Click Switch Role and Set Account ID(1111111111111), Role Name(From Step A3)

YAHOOOO, you are able to Login to Production Account from your Dev account.

**Advance Settings-MFA**

D1)-Edit IAM user, go to "Security Credentials", Assigned MFA device >> Manage >> Virtual MFA Device

D2)-Add Google Authenticator for Chrome from below link.

https://chrome.google.com/webstore/detail/authenticator/bhghoamapcdpbohphigoooaddinpkbai/related?hl=en

D3)-Set up virtual MFA device >> Show secret key

D4)-Go to Google Chrome Authenticator, Edit >> + >> Manual Entry, put secret key from step D3

D5)-Get two consecutive MFA Codes from Google Authenticator for Chrome and put in MFA Code 1 and MFA Code 2 and click Assign MFA

D6)-Logout from Dev User account and Login again. Now after Login authentication it will ask MFA Code.

YAHOOOO, you are able to Login to Your AWS Console Account using MFA.

Cheers.
