---
description: BETA
---

# Configuration

The agent's configuration defines how the agent behaves when interacting with users. The configuration is extremely sensitive and will last for the duration of the interaction between the agent and the user. Small changes in tone and language can have major impacts on how the agent performs, so any changes should be monitored for positive or negative affects.

### Ice Breaker Message

The initial message is sent as a prompt to kick-start the conversation. The message should be written as if a human sent it. If this field is left blank, no icebreaker message will be sent.

#### Examples:

To greet the user:

```
Hello
```

To greet the user and provide some initial guidance as to what the agent can do:

```
Hello, I am pleased to meet you; please briefly tell me what you can do for me.
```

To be extremely specific as to the task at hand:

```
Hello, I am here to talk about the update to a service request.
```

