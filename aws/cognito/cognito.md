# Amazon Cognito

* Give you login and all that bullshit work and sync as well. *

Amazon Cognito lets you easily add  sign-up and sign-in and manage
permissions for your mobile and web apps. You can create your own  directory
within Amazon Cognito. You can also choose to authenticate s through social
identity providers such as Facebook, Twitter, or Amazon; with SAML identity
solutions; or by using your own identity system. In addition, Amazon Cognito
enables you to save data locally on s' devices, allowing your applications
to work even when the devices are offline. You can then synchronize data across
s' devices so that their app experience remains consistent regardless of the
device they use.

## Identity Pools

An identity in a pool gets access to the AWS resources used by your app by being
assigned a role in AWS Identity and Access Management (IAM). The access level of
an IAM role is defined by the policy that is attached to it. Typical roles for
identity pools allow you to give different levels of access to authenticated
(Auth)or signed in s, and unauthenticated (Unauth)users.

## Identity and Access Management (IAM)

* s, groups, permissions to access to EC2 resources
* who can launch an instance
* logs on API activity
* standards based federation policy
* access keys rotation

## AWS Credentials

## SDK

## Setup Step

1. Create an identity pool and roles
2. Add the AWS SDK for iOS to your project
3. Import AWScore and Amazon Cognito APIs
4. Initialize the Amazon Cognito credentials provider
5. Retrieve Amazon Cognito IDs and AWS Credentials

## API Gateway

## Data Sync
sync 's data across devices, like when they upgrade their phone

## Cognito Identity
* pool - gives you sig-up and sign-in
* federated identities - use identity where a different service does the sign-up and sign-in. like google, facebook, Active Directory

![cognito](https://i.imgur.com/MAA7JdD.png)

## Refresh token

The idea of refresh tokens is that if an access token is compromised, because it is short-lived, the attacker has a limited window in which to abuse it.


### API Docs

from [here](https://docs.aws.amazon.com/cognito--identity-pools/latest/APIReference/cognito-user-identity-pools-apiref.pdf#CommonParameters)

* admin
* attributes
* confirmation code
* device
* device
* global
* group
* identity provider
* import job
* initiate auth
* list
* password
* resource server
* sign-out
* signup
* ui customization
* update
*
*  pool
*  pool domain

## Common Parameters for all requests

The following list contains the parameters that all actions use for signing Signature Version 4 requests with a query string. Any action-specific parameters are listed in the topic for that action. For more information about Signature Version 4, see Signature Version 4 Signing Process in the Amazon Web Services General Reference.

* action
* version
* x-amz-algorithm
* x-amz-credential
* x-amz-date
* x-amz-security-token
* x-amz-signature
* x-amz-signedheaders


### Classes

`AWSCognitoAuthConfiguration`

`AWSCognitoAuth`


### WTF These used for?
* `CognitoPoolAppClientId` Your app client id, i.e 81q37d9nfu607gil4uhopekm4b
* `CognitoPoolAppClientSecret` Optional Your app client secret, i.e. `45dpc0bk45v8alftrjv4afeu4nduz1b7do5mjqtia36r7cbnl4d9`. If you don't have a client secret, completely remove this key/string pair.
* `CognitoAuthWebDomain` Your domain, i.e. https://yourdomain.auth.region.amazoncognito.com

#### These two are ios redirect URIs I believe
* `CognitoAuthSignInRedirectUri` Your sign in redirect uri, i.e myapp://signin
* `CognitoAuthSignOutRedirectUri` Your sign out redirect uri, i.e. myapp://signout
---

- `CognitoAuthScopes` Array containing scopes to request, i.e. `aws.cognito.signin..admin` i.e. `aws.cognito.signin.user.admin`

### Redirect URI
todo

### Secure Remote Password (SRP) protocol
from [wikipedia](https://en.wikipedia.org/wiki/Secure_Remote_Password_protocol), [stanford](http://srp.stanford.edu/whatisit.html)

The Secure Remote Password protocol (SRP) is an augmented password-authenticated
key agreement (PAKE) protocol, specifically designed to work around existing
patents.[1] Like all PAKE protocols, an eavesdropper or man in the middle cannot
obtain enough information to be able to brute force guess a password without
further interactions with the parties for each guess. This means that strong
security can be obtained using weak passwords. Furthermore, being an augmented
PAKE protocol, the server does not store password-equivalent data. This means
that an attacker who steals the server data cannot masquerade as the client
unless they first perform a brute force search for the password. In layman's
terms, given two parties who both know a password, SRP (or any other PAKE
protocol) is a way for one party (the "client" or "") to demonstrate to
another party (the "server") that they know the password, without sending the
password itself, nor any other information from which the password can be
broken. Further, it is not possible to conduct an offline brute force search for
the password.

# Tokens
- `ID-Token`
- `Access-Token`
- `Refresh-Token`

## sample call
* doesnt work, yet

```bash
#!/bin/bash
region=us-east-1
user_poolid=us-east-1_YmCPtU8K8
auth_flow=ADMIN_NO_SRP_AUTH
client_id=my_client_id
cmd=admin-initiate-auth
auth_parameters="USERNAME=user1,PASSWORD=password1!"

aws cognito-idp "${cmd}" \
--user-pool-id "${user_poolid}" \
--auth-flow "${auth_flow}" \
--client-id "${client_id}" \
--region "${region}" \
--auth-parameters "${auth_parameters}"
```
