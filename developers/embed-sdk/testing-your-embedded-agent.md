---
description: A working example for a developer wanting to embed an agent in web page.
---

# Testing your Embedded Agent

## Introduction

Mindset's embedded agent assumes that all user authentication and management is handled externally, so it needs a host application to manage this.

We have created a very simple server side script which handles the authentication using query parameters passed in a URL, and then returns a working HTML page which loads an agent.

You are encouraged to view the source of this page and see how:

* the agent is assigned to an element in the page
* how the agent is configured with application, agent and user information

You will not see the code that uses your API key to create an **authToken** for the user. That is handled in the server side code, but the code is as described in [**Authentication**](authentication.md)

<figure><img src="../../.gitbook/assets/Screenshot from 2025-02-11 17-45-49.png" alt=""><figcaption><p>Screenshot of the testing page</p></figcaption></figure>

### Not for end users

This page is an example implementation for developers to use as a reference.

It is not suitable for end users because the API Key needed should never be revealed to end users. It grants access to many application resources.

To build your own implementation you can also follow the details described in [Embed an AI agent: step by step guide](embed-an-ai-agent-step-by-step-guide.md)

### Security warning

This test page uses an API Key in its URL

This is inherently insecure. API keys should in normal use never be in anything run by an end user’s browser.

The API key has the same rights to all data in your application that an app admin has.&#x20;

This functionality is provided for internal use by Mindset's partners developing their systems

## Getting started

### You will need to know

* **appUid** - It is likely to be the main part of your domain name.
* **agentUid** - You can get it from your Mindset App Admin UI (agents section)
* **Your API host server -** also known as **MINDSET-API-HOST**

Your Mindset contact can help you with these pieces of information.

You will also need:

* an **API key**. You can generate this yourself in the API Key management section of the admin UI.

If you cannot see this in the Admin UI you may need to ask Mindset to enable it for you

You should also pick an email address to use as a test user.

**Note** This merely has to be in the format of an email address. No emails will ever be sent to this address, and it will be visible in a modified form in some parts of the Admin UI

## Testing page starting point

Open that URL in your browser : **https://your-api-host-server/api-embed-agent-test-initform**, then fill all INPUT fields with your own information, and click the submit button.

<figure><img src="../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>



## Testing your embed agent in a playground page

You should now see the playground page.\
\
The authentication token has been generated on our server side and we encourage you to open the source code tool of your browser in order to check the Mindset javascript used on the fronte end to display the embed agent in that testing page.

\
Your agent is not loaded yet. You must do some action in that playground to demonstrate how the Mindset SDK methods work:

* Click on the **initApp()** button to load the Agent module in the sample web page.
* Click on the **agentStartThread()** button to display the agent UI initially loaded with the question passed from the playground INPUT field.
* Click again on the **agentStartThread()** button, but this time by passing another **initial question**.



