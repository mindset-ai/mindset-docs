---
hidden: true
---

# api-accounts

Allows creation & querying of accounts (grouping of users). This is the basis for granting entitlement to restricted access content

## Path

`/api-accounts`

## GET

Retrieves information about an account.

Use a query parameter `accountUid` OR `externalId` to find the account

### Response

#### 200

JSON object of: `accountUid` : uid of the account you just queried for `accountName`: name of the account (as displayed in the admin console and to end users) `externalId`: identifier for the account that can optionally be specified in create account (POST)

It is assumed that `externalId` will be unique. If multiple accounts exist with the same value for `externalId` then only one of them will be returned and there is no predictability which one.

#### 404

No account was found

#### 401

Missing API Key

#### 403

Invalid API Key



## POST

JSON in the request body containing {`accountName`:--Name of the account--}&#x20;

Optionally the body can contain a string value for an externalId (See GET for how this can be used to query)

### Response

#### 201

On successful save the response will be JSON containing the name of the account and its `accountUid`

#### 401

Missing API Key

#### 403

Invalid API Key

