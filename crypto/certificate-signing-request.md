# Certificate Signing Request

from [wikipedia](https://en.wikipedia.org/wiki/Certificate_signing_request)

In public key infrastructure (`PKI`) systems, a certificate signing request
(also `CSR` or certification request) is a message sent from an applicant to a
certificate authority in order to apply for a digital identity certificate. It
usually contains the public key for which the certificate should be issued,
identifying information (such as a domain name) and integrity protection
(e.g., a digital signature). The most common format for `CSR`s is the PKCS #10
specification and another is the Signed Public Key and Challenge SPKAC format
generated by some web browsers.

* consists of three main parts:
  1. the certification request information
  1. a signature algorithm identifier
  1. a digital signature on the certification request information.

## tl;dr
- make key pair
- include public key in CSR
- include identifying info, like domain name in CSR

## apple example
we create the CSR, send it off to Apple through our authorized iTunes Connect account.

## Create CSR Mac
To create a CSR file, follow the instructions below to create one using Keychain Access.

### Create a CSR file.
* Keychain Access.
* `Keychain Access > Certificate Assistant > Request a Certificate from a Certificate Authority`.

In the Certificate Information window, enter the following information:

* In the User Email Address field, enter your email address.
* In the Common Name field, create a name for your private key (e.g., John Doe Dev Key).
* The CA Email Address field should be left empty.
* In the "Request is" group, select the "Saved to disk" option.
* Click Continue within Keychain Access to complete the CSR generating process.

## notes from Steve Gibson
STEVE:  Well, yeah, because you need to pay somebody in order to get one.  The
idea is that - and we're going to discuss this in detail.  There is an implied
trust at some level within the certificate structure.  That is, you know, for
example, VeriSign is generally the company I get mine from, although I used
GoDaddy this summer when I was messing around with a wildcard certificate
because they were so much less expensive.  But the point is none of them are
free because, in return for getting the certificate, you have to go through some
procedure to prove you are who you say you are.  They are supposed to, in turn,
verify that information, make sure that this is coming from Gibson Research
Corporation.  I mean, they check our Dun & Bradstreet number, they place phone
calls to phone numbers that are known to be associated with Gibson Research that
come from sources other than us saying, oh, here, call this number.  So they
independently verify as much information as they can, really as a function of
how secure you want this to be.  So they want to get paid in return for doing
all that.  And that's sort of the ecosystem that we have for certificates.

## namecheap explanation
https://www.namecheap.com/support/knowledgebase/article.aspx/337/67/what-is-a-certificate-signing-request-csr
