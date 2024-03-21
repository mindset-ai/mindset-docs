# api-humans

Provides some information about end users who may or may not yet have signed up to the application, given their email address.

## Path

`/api-humans`

## GET

Use a query parameter `emailaddress` to find out if a user with this email address exists, has been invited, and to which accounts

### Response

#### 200

JSON object of: `status`: `userCreated` // A user has accepted an invitation or signed up to the app `userInvited` // A user has been invited to create an account in the app, but has not yet signed up

`uid`: // For users who have signed up only `accounts`: \[...acountUids...] an array of accountUids which the user is a member or or has been invited to

#### 404

No user was found with that email address

#### 401

Missing API Key

#### 403

Invalid API Key
