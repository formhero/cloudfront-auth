Solution currently used to provide auth to static resources (such as handbook.formhero.com)
Forked from https://github.com/Widen/cloudfront-auth


Notes:
- I wasn't able to get the SAM deploy running, used a manual deploy
- Make sure to create your Lambda function in us-east-1 to be usable by the CloudFront distro


# handbook.formhero.com components

## Who can access
Anyone in the FormHero org with email ending in @formhero.com (specified by Hosted Domain + Authorization methods below)

## Settings for build.sh
>: Enter distribution name:  handbook-formhero-com
>: Authentication methods:
    (1) Google
    (2) Microsoft
    (3) GitHub
    (4) OKTA
    (5) Auth0
    (6) Centrify
    (7) OKTA Native

    Select an authentication method:  1
>>: Client ID:  REDACTED.apps.googleusercontent.com
>>: Client Secret:  REDACTED
>>: Redirect URI:  https://handbook.formhero.com/_callback
>>: Hosted Domain:  formhero.com
>>: Session Duration (hours):  (0) 1
>>: Authorization methods:
   (1) Hosted Domain - verify email's domain matches that of the given hosted domain
   (2) HTTP Email Lookup - verify email exists in JSON array located at given HTTP endpoint
   (3) Google Groups Lookup - verify email exists in one of given Google Groups

   Select an authorization method:  1

## Lambda
handbook-formhero-com-cloudfront-auth in FH root account on us-east-1
arn:aws:lambda:us-east-1:448989908326:function:handbook-formhero-com-cloudfront-auth:1

## CloudFront Distro:
E2LEBLSJMSIC35
dc9ijh2son9yh.cloudfront.net
handbook.formhero.com
Located in the FH root account

## Google Cloud
FormHero account
Project: fh-cloudfront-auth
https://console.developers.google.com/apis/credentials?project=fh-cloudfront-auth&folder=&organizationId=
OAuth 2.0 Client ID: handbook.formhero.com auth
