---
description: A working example for a developer wanting to embed an agent in another web
---

# Testing the Embedded Agent



Mindset's embedded agent assumes that all user authentication and management is handled externally, so it needs a host application to manage this.

We have created a very simple server side script which handles the authentication using query parameters passed in a URL, and then returns a working HTML page which loads an agent.

You are encouraged to view the source of this page and see how:

* the agent is assigned to an element in the page
* how the agent is configured with application, agent and user information

You will not see the code that uses your API key to create a authToken for the user. That is handled in the server side code, but the code is as described in [authentication.md](authentication.md "mention")



### Security warning

This test page uses an API Key in its URL

This is inherently insecure. API keys should in normal use never be in anything run by an end user’s browser.

The API key has the same rights to all data in your application that an app admin has.&#x20;

This functionality is provided for internal use by Mindset's partners developing their systems

## Getting started

Your tools for this are **a web browser** and **a text editor**.

### You will need to know

* appUid - It is likely to be the main part of your domain name.
* agentUid - This will soon be available in the Admin UI
* Your API host server

Your Mindset contact can help you with these pieces of information.

You will also need:

* an API key. You can generate this yourself in the API Key management section of the admin UI.

If you cannot see this in the Admin UI you may need to ask Mindset to enable it for you

You should also pick an email address to use as a test user.

**Note** This merely has to be in the format of an email address. No emails will ever be sent to this address, and it will be visible in a modified form in some parts of the Admin UI

## Construct the browser string

You need to provide all this information as query parameters in a browser query string

eg, replacing all the _**bold-italic-elements**_

https://_**API.HOST.SERVER**_/api-embed-agent-test?appUid=_**myapp**_\&agentUid=_**myagent**_\&userEmail=_**some\_test\_user@nowhere.com**_\&apiKey=_**a-really-long-api-key-string**_



When you load that in your browser you should the embedded SDK in action

## This is a test page

It is deliberately not styled or laid out in any particular way.

It contains the "check" component which is only useful to verify that the embedded front code is successfully initialized and connected to our back end.

You are encouraged to use the browser dev tools to see how it is embedded.

