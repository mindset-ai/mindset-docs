---
description: Many APIs are designed to be called by external systems.
---

# API Key authentication

As these systems are under the control of administrators rather than end users, authentication can safely be handled by shared secrets known to two servers (Mindset's and the external system).

These secrets never need to or should be passed to end users.

API Keys for Mindset's system grant app owner level access to data.

## Generating an API key

API keys are generated for each application in the app admin console.

Each key is a long alphanumeric string would should be stored securely.

Navigate to the "API key management" to generate and copy a key

## Invalidating a key

If a key is compromised and it is being used outside of your control, or you suspect it might be, then you can delete the key from the admin console.

That will cause any future API calls that use the key to fail. It will not interrupt any currently ongoing processes initiated using that key.

(For example a user session that was created by using that key will continue to be valid)

## Using a key

Keys are used by passing them as a custom header in the web requests you make.

The header name is `x-api-key` and its value should be the full key string.
