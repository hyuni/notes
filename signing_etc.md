# Provisioning Profile

A provisioning profile is a collection of digital entities that uniquely ties
developers and devices to an authorized iPhone Development Team and enables a
device to be used for testing. A Development Provisioning Profile must be
installed on each device on which you wish to run your application code. Each
Development Provisioning Profile will contain a set of iPhone Development
Certificates, Unique Device Identifiers and an App ID. Devices specified within
the provisioning profile can be used for testing only by those individuals
whose iPhone Development Certificates are included in the profile. A single
device can contain multiple provisioning profiles.

# Signing

* identifies you to users
* tied to bundle id

xcode behind the scenes uses a tool called `codesign`

it takes the apps bundle and applies a code seal. this way the system can see if the app has changed after signing.

it also signs the app so you can know where it came from

## 3 things to sign

1. signing certificate

  * issued by apple
  * creates a trust chain back to apple
  * distribution v. development certs
  * requires a private key
  * apple never has this private key
  * all about who you are
  * dev certs handled for you

2. provisioning profile

  * issued by apple
  * app specific
  * allow access to run on devices
  * gives access to entitlements
  * if you want to use entitlements it has to be on the list

3. entitlements
  * declare support for capabilities
  * defined per target
  * see the xcode capabilities tab, which manages the plist for entitlements

## When XCode goes to sign your app

* needs to know which cert to use
* needs to know which profile to use
* xcode looks in your keychain for the newest cert that matches dev team

* then looks at list of profiles, picks newest one that matches bundle id

* dev account has limit of one cert per

## Setting up new machines

* you can have multiple certs per dev for debug
* you can only have one cert for release

### Automatic Signing in XCode 8

* create certs
* updates app ID and profile
* signing reports show what XCode did and why

# Development Team

see [Development Team](./development_team.md)