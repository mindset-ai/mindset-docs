---
description: BETA
---

# Tools

The Tools section within an Agent's configuration serves as a repository of additional functionalities or external modules that the Agent can leverage to enhance user interactions. These tools can range from language model functions, like the Clarification Tool, to integrations with external databases, APIs for retrieving information, or interactive elements designed to improve the engagement and effectiveness of the Agent's responses. The invocation of these tools during a conversation is determined by the Agent's underlying logic and decision-making processes, which assess the context and requirements of the interaction to decide when a specific tool is necessary.

**How Tools Are Invoked**

1. **Contextual Analysis:** The Agent continuously analyzes the conversation's context to understand the user's needs and the type of assistance required. This analysis is based on the user's queries, responses, and the conversational flow established by the Agent's purpose and process steps.
2. **Decision Points:** During the interaction, the Agent identifies decision points or moments where the conversation could benefit from the use of a specific tool. This could be a need for clarification, the requirement to pull in external data, or the opportunity to present information in a more engaging way.
3. **Tool Selection:** Based on the identified need, the Agent selects the appropriate tool from its configuration. The selection is guided by the tool's intended use case, the potential for enhancing the conversation, and the overall goal of addressing the user's query effectively.
4. **Automatic Activation:** Once a tool is selected, the Agent automatically activates or invokes it without requiring explicit instructions from the user or the Agent operator. This seamless integration allows for a fluid conversation experience, where the use of tools feels like a natural extension of the Agent's capabilities.
5. **User Interaction:** The tool interacts with the user according to its design—whether it's by providing visual options, retrieving information, or facilitating a specific task. The user's engagement with the tool informs the next steps in the conversation, allowing the Agent to further tailor its responses based on the user's input or selections.
6. **Continued Conversation:** Following the tool's invocation and the user's interaction with it, the Agent seamlessly continues the conversation, incorporating the outcomes or information obtained through the tool's use. This ensures a coherent flow, where the tool's integration feels like an integral part of the interaction rather than an external interruption.

### Clarification Tool

The Clarification Tool automatically activates during interactions when the Agent, powered by the LLM, identifies a need for further clarification from the user to proceed effectively. This tool facilitates a smoother conversation flow by presenting users with a set of visual UI pills representing the most logical options based on the context of their query. It's an intuitive aid that helps narrow down user intent or preferences without needing predefined triggers in the Agent's prompts.

**Integration Approach**

Given the automatic nature of the Clarification Tool, the focus shifts to ensuring the Agent's prompts are open-ended enough to allow for natural occurrences of clarification moments, without the need for explicit directive changes in the Agent's configuration.

**Examples Adjusted for Clarification to initiate the Clarification Tool**

Considering the tool's automatic engagement, it is important to consider the configuration instructions to maximize the potential for clear and effective use of the Clarification Tool in interactions.

**1. Customer Support Agent**

```plaintext
Ensure your responses invite open-ended feedback from the user about their 
satisfaction with the solutions provided or if they have additional queries, 
creating opportunities for the Clarification Tool to assist in narrowing down user 
needs.
```

**2. Policy Explanation Agent**

```plaintext
Encourage users to ask questions about policy details that may require further 
exploration, allowing the Clarification Tool to offer options for different policy 
aspects the user might be interested in.
```

**3. Coaching Agent**

```plaintext
Prompt users to share their goals or challenges in a manner that opens the door 
for specifying areas they wish to focus on, leveraging the Clarification Tool to 
help users make selections that best match their interests.
```

