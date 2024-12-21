---
description: We have made some enhancements
---

# Enhanced API for embedding agents

We have improved the way our JS API can be used to embed an agent.

This has required a change that we could not make automatically backwards compatible, so to take advantage of it you will need to use our updated JS methods.

Existing integrations will continue to work, but the original methods will be deprecated.\


## Original technique <a href="#original-technique" id="original-technique"></a>

The SDK provided two methods to display an agent, that must be called in turn

`mindset.init()` and then `mindset.render()`

This allowed multiple instances of Mindset’s agent on the same page, but it did not start running Mindset code until the moment we wanted to show the user the agent’s UI.

A user always had to wait because it takes time for the Mindset code to initialise.

This is documented in  [embed-sdk.md](embed-sdk.md "mention")

## Updated technique <a href="#updated-technique" id="updated-technique"></a>

`mindset.init()` has been replaced by `mindset.initApp()`

This now allows the Mindset application to start initialisation as early as possible.

A much improved UX is now possible with the initialisation able to happen invisibly and asynchronously from actually wanting to display an agent.

When we want to display an agent UI to a user (assuming start up is complete) we can now do that almost instantly with `mindset.startAgentThread()`

It’s now also possible to start more threads, or switch the UI to a converse with a different agent.

This is documented in [how-to-embed-an-agent-in-your-site.md](how-to-embed-an-agent-in-your-site.md "mention")
