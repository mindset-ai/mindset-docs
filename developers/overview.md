---
description: Overview of the Mindset API and Mindset Embedded
---

# Overview

## Integration Options

Mindset provides two modes of integration:

* [Mindset API](mindset-api/) (headless REST and gRPC APIs)
* [Embed SDK](embed-sdk/) (embedding Mindset UI components on webpages)

The method of integration depends on your objectives.&#x20;

If you want to interact with Mindset as a headless service and provide all the UI, then the Mindset API is the perfect route. You will interact with Mindset through our REST or modern gRPC APIs (which both provide the same features), and you will need to implement all the user interfaces for your users.

To leverage Mindset's user interface components in your web application, the Embed SDK approach is better for you. Individual UI components can be added to your application, and you can interact with these components using JavaScript. All of the UI configuration is handled through the [Mindset Platform](broken-reference).

You can use both the API and the Embedded approach if your use-case requires it.

Whichever method you choose, you will need to set up a Mindset Application and have obtained an API key from support. Please [contact support](../support/contacting-support.md) if you have not done this yet, and we will help you get started.
