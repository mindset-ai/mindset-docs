# api-accountmembership

Joins someone to an account using their email address, triggering an invitation & validation email

## Path

`/api-accountmembership`



## POST

Body should contain application/json with values for

mandatory:\
`userEmail` - user address to invite to the account\
`emailSubject` - subject line of the email they will receive\


one of:\
`accountUid` - account they are being invited to\
`externalId` - identifier specified when creating the account through the API

optional:\
`emailMessage` - text that will be part of the message body of the email

### Response

#### 200

User was already a member or has already been invited

#### 201

An invitation email was sent

#### 401

Missing API Key

#### 403

Invalid API Key

#### 404

Account was not found

