# api-authenticate-embedded-user

## Path

`/api-authenticate-embedded-user`

## **POST**

The request body should be content-type `application/json`

Example body `{"userEmail":"automated_user_fred.smith@acme.com"}`

The body should contain one value indicating a user email address on which to base the generated user's identity.

NOTE This email address is prefixed with additional identifying information , so the email address won't receive emails, and the account will not be the same as any account created by a user signing up with that email address.

You can also use a string that is like an email based on some othe user specific identifier meaningful to you.



Optionally you can specify accounts to join the user to.\
To do this pass an additional parameter `addToAccounts` which should be an array of objects of the form `{accountUid:"<uid-of-account-to-be-joined>"}`\


Example body `{"userEmail":"automated_user_fred.smith@acme.com",addToAccounts:[{accountUid:"account1"},{accountUid:"account2"}]}`

Users added like this will show up in the account admin members UI

### Responses

#### 401 - Missing API key

#### 403 - Invalid or deleted API Key

#### 201 - Auth token created successfully

The response body will contain JSON with a long string value for `authToken`. This token can be used to authenticate the Embed SDK&#x20;



