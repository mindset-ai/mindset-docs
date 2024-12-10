# How to use Tools

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

Considering the tool's automatic engagement, it is important to consider the configuration instructions to maximize the potential for clear and effective use of the Clarification Tool in interactions.

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

### Additional Accuracy checking

Designed to work with agents where the information returned to users **must** be based on the knowledge banks available, the additional accuracy checking tool adds extra validation checks to any answer provided by the LLM.

Working in concert with the agents normal systems, responses from the LLM are validated against data provided from the knowledge banks the agent has access to before being returned to the user. If any aspect of the agents response could not have been generated from this data, the LLM is instructed to regenerate it's answer with emphasis on any section where a disparity is located.

When this tool is enabled for an agent, there 3 notable impacts on the experience:

* Responses from an agent will appear fully formed and will not stream to the user word by word. This is required in order to validate the response before returning it to the user.
* Responses will take longer to generate. The process of checking and regenerating responses can be triggered multiple times in order to get a precise and accurate result.&#x20;
* It is possible that after several rounds of generation and checking that a valid and supported answer has not been produced. In these cases, the agent will respond back to the user that it is unable to provide an answer at this time. The same question may or may not be answered correctly on another attempt.

Even with this option in place, the agents response is not 100% failsafe. Though we recommend using this option in any situation where the accuracy of the agents response is critical, mistakes are still possible.&#x20;

### Additional Response Details:&#x20;

**Sources and topics UI style:** This is where administrators can select how the content used in agent's responses and related topics are displayed to users in the agent interface. This can either be displayed as pills below the agent's response, or display as panels above and below the agent's responses.&#x20;

Segments, topics, and speakers can be displayed in agent responses by toggling the 'display segments', 'display topics' and 'display speakers' switches on. The names of each of these can also be altered via the text box below the toggles. **Please note:** there is a character limit of 15 for these headings.&#x20;

**Display follow-up questions:** This generates relevant and appropriate follow-up questions, these prompts guide users deeper into the source material. Instead of relying on the user to know what to ask next, the system gently nudges them toward further discovery.

<figure><img src="../../../.gitbook/assets/Screenshot (5).png" alt=""><figcaption></figcaption></figure>

These questions are automatically generated and appear at the bottom of an Agent's message for a user to select.

<figure><img src="../../../.gitbook/assets/Screenshot (6).png" alt=""><figcaption></figcaption></figure>

**Display Citations:** Finally, admins can select whether to display citations in agent responses by toggling the 'display citations' switch on.

Citations refer to a reference to the source of information used by the agent to support a specific claim, fact, or statement. Citations allow users to see where the information they’ve been served has come from. This builds trust and enables users to verify the source. Users can consult the cited sources to verify claims, double-check facts, or explore a topic further.



### **Advanced Configuration:**&#x20;

**Number of Segments**: This setting lets admins adjust how many pieces of information (segments)  agent's consider when formulating an answer. The default is 5 segments.

For agent use cases where a user requires a quick, focused response, this number can be adjusted to 2 or 3 segments. However, in other use cases where discovery and in-depth responses are needed, this can be increased to 7-8 segments, so the agent will use more information and recommend more content.&#x20;

**Please note:** using a lot of segments can make responses longer and potentially increase the response time since the AI has to process more information.

&#x20;

**Segment Score Threshold**: This can be referred to as a 'quality filter' for segments. It's a score from 0 to 1 that rates how well each segment matches the user's question.&#x20;

Setting a higher threshold of 0.8 or 0.9 means agents will only use the most directly relevant segments in responses. This can be beneficial for technical responses where you need pinpoint accuracy.

Lowering the threshold to 0.5 or 0.6 allows agents to bring in segments that are more loosely related, but could provide helpful context or spark creative ideas for more open-ended conversations.

The key is adjusting these two controls in tandem based on the specific agent use case, and then using the different testing tools we provide in the agent administration portal.&#x20;

For specific, technical or compliance-driven use cases, use less high-relevance segments. For exploratory agent use cases, allow more segments with a lower relevance threshold.

We recommend experimenting to see what levels of detail and relevance work best for your typical use cases. These changes can be adjusted as required.



**Agent Diagnostics:** If the 'Agent Diagnostics' toggle is switched on, a debug code block will be displayed in the agent response. **Please note:** this debug code will only be visible for application admins.&#x20;



**Inject Source URL:** The 'Inject Source URL' toggle can also be enabled in the agent configuration. When this toggle is switched on and the knowledge has been via synced bank, agent responses will direct users to the original web page links where the segment's content has been sourced from.&#x20;
