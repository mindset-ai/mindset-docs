---
hidden: true
---

# api-bankaccess

Grants or removes access to a knowledge bank

DEPRECATED - **This method of controlling access to restricted knowledge is no longer in use and will soon be replaced by a similar API to manage account access to agents.**

## Path

`/api-bankaccess`



## POST

Adds an account to a bank's access list

Body should contain application/json with values for

`bankUid` - (aka contextUid) uid of the bank to be modified `accountUid` or `externalId` - account being added to the access list

### Response

#### 200

No change made - Account already had access

#### 201

Account was added to the bank's access list

#### 401

Missing API Key

#### 403

Invalid API Key

#### 404

Account was not found, or bank was not found

#### 422

Bank is openAccess so all accounts already have access. No change made



## DELETE

Removes an account from a bank's access list

Query parameters should contain values for:

`bankUid` - (aka contextUid) uid of the bank to be modified\
`accountUid` or `externalId` - account being added to the access list

### Response

#### 200

Account no longer exists in bank access list

#### 401

Missing API Key

#### 403

Invalid API Key

#### 404

Account was not found, or bank was not found

#### 422

Bank is openAccess so all accounts already have access. No change made
