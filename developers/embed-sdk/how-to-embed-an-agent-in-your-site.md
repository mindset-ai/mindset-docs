# How to embed an agent in your site

## What you can do <a href="#what-you-can-do" id="what-you-can-do"></a>

You can embed your Mindset agent into a web page you are building for your users.

Typically this will form part of a range of resources you make available to specific people - students studying certain courses, team members in a particular group.

Identifying the user and controlling access to the agent, and the knowledge it has access to, is in the control of your site.

## Mindset Agent code flow <a href="#mindset-agent-code-flow" id="mindset-agent-code-flow"></a>

There are three distinct steps that must happen in order to display an agent to an end user.

### 1. Authentication - server side <a href="#authentication-server-side" id="authentication-server-side"></a>

This happens under the control of your server systems. Ideally it can happen as your site builds the page to return to the end user, but you could implement your own server side API that will respond to authorised (as a user of your site) requests.

Same as before - [![](https://1456005154-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5dRId4QrAnQV7eKBUoK5%2Ficon%2FgBwS2A1GsF0OqDEzROje%2Fmindset-fav-48.png?alt=media\&token=d099863c-fc9f-40e2-b9b3-93e126db791e)Authentication | Mindset AI Documentation](https://docs.mindset.ai/developers/embed-sdk/authentication)

### 2. Mindset application initialisation <a href="#mindset-application-initialisation" id="mindset-application-initialisation"></a>

#### Bootstrapping JS  <a href="#bootstrapping-js" id="bootstrapping-js"></a>

In order to be able to call the agent you must include the Mindset bootstrapper JS in your HTML page.

This lightweight JS makes available the methods you’ll need to call our agent.

The URL for this script depends on the main application URL your Mindset application has.

Eg - if your Mindset application is at **https://app.acme.com** then the bootstrapper JS is at **https://app.acme.com/mindset-sdk.js**

You can include the script anywhere in the page as long as you ensure it has loaded before you try to use it.

#### Start the Mindset application running <a href="#start-the-mindset-application-running" id="start-the-mindset-application-running"></a>

It takes a few seconds for the Mindset application to initialise itself. With this updated functionality you can now start this process as early as possible instead of waiting until the user requests the agent.

The Mindset application needs the following to start running:

* an authentication token for the current user
* an element in the page to which it can attach, and in which all UI will be rendered

The element in the page will typically be a div. You must give it a unique ID, and then pass that ID to the Mindset client side API

**This element does not yet need to be visible to the end user, or of any particular size.** You can leave it hidden until you want to display an agent to the user.

If the element is visible then it will display a loading spinner as the application loads.

The client method to initialise mindset is:

{% code lineNumbers="true" %}
```
window.mindset.initApp({
    appUid: %YOUR_APP_UID%,
    containerId: 'id-agent-div', // ID you have allocated to the agent
    authToken: %AUTH_TOKEN_FOR_THIS_USER%, // Generated server side
    loadingText: 'Text to display below the spinner', // OPTIONAL
});
```
{% endcode %}



Once initialised the mindset application displays empty whitespace in its UI until an agent is invoked.

### 3. Starting Agent Threads <a href="#starting-agent-threads" id="starting-agent-threads"></a>

You can start a conversation for the user with an agent by calling a second method.

This will display the agent chat UI

By default it will use a configured icebreaker to send a first message to the user from the agent.

**Optionally you can pass in some text to be sent to the agent as a first message from the user - eg as search query constructed by code in your site.**

You need to know the UID of your agent.

If it is a restricted agent then you need to make sure that when generating the authToken you passed the UID of an account that has access to the agent.

The code to start an agent thread is:

{% code lineNumbers="true" %}
```
window.mindset.startAgentThread({
    agentUid:%YOUR_AGENT_UID%, // MANDATORY
    initialQuestion:'Some text to send to the agent', // OPTIONAL - see below
    variables: {role:'supervisor', customerId:'bigcorp'}, // OPTIONAL see below
});
```
{% endcode %}

#### initialQuestion

If this is missing or an empty string then the configured icebreaker message, if any, will be used to start an agent conversation.

If this is supplied then it will be sent to the agent as the first input from the user.

Eg `initialQuestion: 'Do you have information on safety requirements',`

#### variables <a href="#variables" id="variables"></a>

Some content can be ingested so that it will link to external URLs. It is possible that these URLs will contain placeholders that need to be replaced with specific values for individual users.

This parameter allows you to specify those values at the moment the user interacts with the agent.

For example - you might have a branded site for your content that means you want to include a customer ID and a user role in the URLs you link to

If you are [acme.com](http://acme.com/) & your customer is BigCorp then this allows you to have content URLs that resolve to:

https://**bigcorp**.acme.com/content/specific-item?role=**supervisor**

## Other details <a href="#other-details" id="other-details"></a>

### You can request to start a thread immediately <a href="#you-can-request-to-start-a-thread-immediately" id="you-can-request-to-start-a-thread-immediately"></a>

If the Mindset application has time to start before you display an agent, then the user will see the agent immediately your site displays it.

That’s not always the case.

If a call is made to startAgentThread before the application is ready then it will act on that request as soon as it can.

Note - Only the most recent call to startAgentThread will be acted on.

### You can start fresh threads any time <a href="#you-can-start-fresh-threads-any-time" id="you-can-start-fresh-threads-any-time"></a>

If you want to start an agent thread in response to something that happens elsewhere on your page then just call `startAgentThread` again.

The user’s previous threads will be available to them from their thread list.

### You can call different agents <a href="#you-can-call-different-agents" id="you-can-call-different-agents"></a>

You can only have one agent visible at a time, but you can switch between agents without having to initialise the Mindset application again.

Just pass a different UID into the startAgentThread call.
