# b2cfed
Uses B2C to federate with multiple external IdPs, incl. AAD Common supporting url based HRD

## Purpose

Use B2C to federate external token issuers to an application while minimizing the Home Realm Discovery effort either on the application or the user. Intended to support
SaaS applications where number of external STS's is large and changing, users must not be aware of which STS's are supported and the effort needed to support
the federations should be minimized.

The policy uses B2C's support for federating to the AAD /common endpoint making federation with new AAD tenants almost configuration-free (admin consent at most).

The policy uses a REST function to map a meaningless code (which could be used by users) to a choice of the appropriate Technical Profile (AAD common or non-AAD)
to complete user sign-in.

## Demo

Run the following link from your browser. The last parameter determines whether the user will be re-directed to an existing AAD tenant or some other external non-AAD STS. Use *abc* for 
*microsoft.com*, *xyz* for *meraridom.com* or *goo* for *google.com* (only non-AAD STS supported by this policy).

https://mrochonb2cprod.b2clogin.com/mrochonb2cprod.onmicrosoft.com/oauth2/v2.0/authorize?p=B2C_1A_FedSusi&client_id=e4535fdc-6ae7-4d65-9c5c-bf79b136f932&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms%2F&scope=openid&response_type=id_token&prompt=login&domain_hint=abc


