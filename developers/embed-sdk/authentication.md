# Authentication

See also [https://docs.mindset.ai/developers/mindset-api/rest-api/api-authenticate-embedded-user](https://docs.mindset.ai/developers/mindset-api/rest-api/api-authenticate-embedded-user)

## Authentication

**Overview:**

The Mindset SDK employs an authentication mechanism that uses an authentication token. This token is pivotal in linking the client-side session to a user account within the Mindset platform. The process ensures a seamless integration of user sessions with the platform's functionalities.

The authentication approach is two-fold:

1. **Existing User Linkage**: If the user already exists in the Mindset platform, the authentication process will generate a token that links the current client-side session to this existing user account. This facilitates a continuous and integrated experience for returning users.
2. **Automatic User Creation**: In cases where a user does not exist on the platform, the authentication process automatically triggers the creation of a new user account based on the provided email address. A corresponding authentication token is generated, linking the new user account to the client-side session. This streamlined process ensures new users are smoothly onboarded without additional manual steps.

The authentication token is a critical component in this process, serving as the key to accessing and interacting with the SDK's features while maintaining user-specific contexts and preferences.

**Client Authentication Token Generation:**

A secure server-side HTTP POST request is made to the Mindset authentication endpoint to generate the `AUTH-TOKEN-FOR-CURRENT-USER`. This process involves sending user identification details (such as email address) and your application credentials.

```
POST https://MINDSET-API-HOST/api-authenticate-embedded-user
```

#### **Authorisation Header:**

You must supply an API key header with your request.

API keys are managed in the app admin UI.

The header should be passed as:

```
x-api-key: YOUR-API-KEY
```

#### **Request Body:**

The body of the request should include:

* `userEmail` (String): The email address of the user to authenticate.
* `addToAccounts` (optional, array)\
  You can specify one more accounts to automatically add this user to. This to allow embedded agent user sessions to be granted access to restricted agents.\
  Each element of the array should be of the form `{"accountUid":"<UID-OF-ACCOUNT-TO-ADD-USER-TO"}`

#### Example JSON body:

```json
{
  "userEmail": "USER-EMAIL-ADDRESS"
}

```

```
{
    "userEmail":"USER-EMAIL-ADDRESS",
    "addToAccounts":[{"accountUid":"firstaccountid1234"}
}
```

####

#### **Server-Side Authentication:**

* **Critical**: The authentication process must be handled server-side. This is to ensure the security of your API key and the overall integrity of the user authentication process.
* Upon successful authentication, the API returns an authentication token. This token is then used in subsequent SDK function calls to authenticate the user.

#### **User Account Handling:**

* An authentication token will be generated if a user with the provided email address exists in your application.
* If no such user exists, a new user account will be created using the provided email address, and an authentication token will be generated.

#### **Security Considerations:**

* **API Key Confidentiality**: Keep your API key confidential. It should be securely stored and never exposed in client-side code.
* **Authentication Tokens**: Handle authentication tokens securely. They should be transmitted and stored using secure methods to prevent unauthorised access.

#### **Example Server-Side Usage:**

```javascript
// Example Node.js code to make a server-side HTTP POST request for user authentication
// Adapt this example based on your server-side programming environment

const fetch = require('node-fetch');

const requestBody = {
  userEmail: "user@example.com"
};

fetch('https://MINDSET-API-HOST/api-authenticate-embedded-user', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'x-api-key': 'YOUR-API-KEY'
  },
  body: JSON.stringify(requestBody)
})
.then(response => response.json())
.then(data => {
  console.log('Authentication Token:', data.authToken);
})
.catch((error) => {
  console.error('Error:', error);
});
```
