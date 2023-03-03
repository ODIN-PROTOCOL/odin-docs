# Credentials

OdinID credentials are specific verifiable data fields which are used to compose the users identity. This credentials are issued by data providers to specific users for them to add to their identity.

## Credential offering data flow
1. A data provider creates a credential offering for a user which contains multiple credentials. 
2. The user accepts the credential offering, signs each credential and returns them back to the data provider.
3. The data provider verifies those signartures and sign user's signatures.
4. User verifies data provider's signatures, and creates and `AddCredentials` transaction in Odin network.
5. Odin network validates data, signature and updates trust rates.
![Credential Offering](../images/Credential-offering.png "Credential offering")

**IMPORTANT**: Users also have the option of rejecting the credential offering and not get does credentials. In that case flows stops in after step 1, with the user rejecting does credentials.