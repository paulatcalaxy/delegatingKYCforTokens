# Delegated KYC Policies in HTS

- hip: 28
- title: Delegated KYC Policies in HTS
- author: Paul Madsen - paul@calaxy.com
- type: Standards Track
- category: Application
- status: Draft
- created: 2021-10-10
- discussions-to: 
- updated: 

## Abstract

This HIP proposes an extension to the HTC mechanism by which the KYC status of a given Hedera account for a given HTS token can be indicated. Rather than actively managing the KYC status of accounts (using their own KYC key to set the KYC flag on an account), a token admin can delegate that burden to the admin of some other token. If an when the admin of that delegatee token sets the KYC status of a given account to true, the delegator token effectively inherits that status. When one token has delegated the KYC status to another, Hedera nodes would interpret the KYC

## Motivitation

When creating (or subsequently modified if the token is not immutable) a token on HTS, an admin can optionally stipulate a KYC key. If such a key is stipulated, then individual Hedera accounts will only be able to send or receive that token if that account's KYC flag for that token has been set to true. The current model is that the KYC status for a given Hedera account for different tokens is independent, that is, the admin of each different token is expected to separately manage the KYC status of each account for their own token. 

This HIP proposes that, for a given Hedera account, one token would be able to effectively inherit the KYC status of another token and so remove from the delegator token the burden of actively managing KYC status for their token.

## Rationale


## Specification

If a token delegates to another, 

If a token delgates to another, the delegator token MUST not have its own KYC key.


## Backwards Compatibility

## Security Implications

There are no direct security implications, since the uniresolver only exposes the resolution of DID documents trough an API backend that integrates with the existing driver. This means that there is no possibility that mutable actions on data can take place.

## How to Teach This
N/A

## Reference Implementation
N/A

## Rejected Ideas
N/A

## Open Issues

## References
