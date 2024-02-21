---
description: BETA
---

# Tools

### What are Tools?&#x20;

The Tools section in an Agent's setup serves as a storage for extra features or external modules to improve user interactions. These can include language tools, database integrations, APIs for information retrieval, or interactive elements. The Agent decides when to use these tools based on its logic and understanding of the conversation's context and needs.

**How Tools Are Invoked**

1. **Contextual Analysis:** The Agent consistently assesses the conversation's context to grasp the user's needs and the necessary assistance. This evaluation relies on the user's questions, responses, and the flow of conversation guided by the Agent's objectives and steps.
2. **Decision Points:** Throughout interactions, the Agent spots moments where using a particular tool could enhance the conversation. This might include clarifying information, bringing in external data, or making information more engaging.
3. **Tool Selection:** The Agent chooses the right tool from its setup, considering its intended purpose, how it can improve the conversation, and ultimately, how it helps address the user's query effectively.
4. **Automatic Activation:** Once a tool is chosen, the Agent activates it automatically, without needing any specific instructions from the user or the Agent operator. This smooth integration ensures a seamless conversation experience, where using tools feels like a natural part of the Agent's abilities.
5. **User Interaction:** The tool engages with the user based on its design, offering visual choices, getting information, or helping with a task. How the user interacts with the tool guides the next conversation steps, enabling the Agent to adjust its responses to the user's input or choices.
6. **Continued Conversation:** After the tool is used and the user interacts with it, the Agent smoothly carries on the conversation, integrating any results or information gained from the tool. This maintains a smooth flow where the tool feels like a natural part of the conversation, rather than an interruption.

### Clarification Tool

The ClarificationTool kicks in during interactions when the Agent, powered by the LLM, senses the need for more clarity from the user to proceed smoothly. It helps by showing users a visual list of options based on their query context, making it easier to understand their intent or preferences without needing specific prompts from the Agent.

**Integration Approach**

Because the Clarification Tool works automatically, the emphasis is on making sure the Agent's prompts are broad enough to naturally prompt clarification moments. This means there's no need for explicit changes in the Agent's setup to accommodate these instances.

**Examples Adjusted for Clarification to initiate the ClarificationTool**

Considering the tool's automatic engagement, it is important to consider the configuration instructions to maximise the potential for clear and effective use of the Clarification Tool in interactions.

**1. Customer Support Agent**

```plaintext
Ensure your responses invite open-ended feedback from the user about their 
satisfaction with the solutions provided or if they have additional queries, 
creating opportunities to assist in narrowing down user needs.
```

**2. Policy Explanation Agent**

```plaintext
Encourage users to ask questions about policy details that may require further 
exploration, creating opportunities to offer options for different policy 
aspects the user might be interested in.
```

**3. Coaching Agent**

```plaintext
Prompt users to share their goals or challenges in a manner that opens the door 
for specifying areas they wish to focus on, creating opportunities to 
help users make selections that best match their interests.
```

