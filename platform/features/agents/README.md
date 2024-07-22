---
description: An Introduction to Agents in the Mindset platform.
---

# Agents

### An Introduction to Agents

LLMs have changed the way people interact with computers, a change which has happened unprecedently fast.&#x20;

Everyone can see the opportunity AI has to revolutionise the way people learn, with every company, in every industry in the world needing a solution. The market size is $59 billion across all industries. How much would you be worth if you captured 0.1% of that market opportunity?

Mindset wants to enable you to be at the forefront of providing AI solutions to problems in your specific industry.&#x20;



**Below is the evolution of conversational AI:**

1. **Old-school chatbots - T**he type that requires you to plan every possible question, answer, and workflow. Very painful, and always broken because a user asked a question that was not planned for.&#x20;
2. **LLM chatbots -** The first implementation of OpenAI could be considered a well-trained Chatbot. You asked it a question, and it answered from its pre-trained neural network. Although chatbots have been around for over a decade, OpenAI's release of GPT 3 in 2023 was the first groundbreaking innovation using an LLM (large language model).
3. **Assistants (or Co-Pilots)** **-** The core distinction between an Assistant and a Chatbot is that a co-pilot has access to a corpus of data outside the training set of the underlying LLM.&#x20;



Throughout 2023, numerous Assistants and Co-pilots have been developed with increasing levels of complexity and access to data. RAG (retrieval-augmented generation) is an AI framework for retrieving facts from an external knowledge base to ground large language models (LLMs) on the most accurate, up-to-date information.&#x20;

4. **Assistants with Knowledge Graphs -** Beyond RAG, information available to the Assistant can be highly structured (from structured and unstructured data) to run entity extraction on the source data and the responses from an LLM to provide insights into bias and information coverage, as well as personalize answers based on company context (specific terminology to a company, people, locations, products etc).
5. **Agents -** Agents are a system that can use an LLM to reason through a problem, create a plan to solve the problem, and execute the plan with the help of a set of tools. An Agent is an architecture that includes all of the concepts mentioned above and below.

<figure><img src="https://lh7-us.googleusercontent.com/1TubduKTBp2AjefpRio4BCGrtiDPASDzobDGnDGvX5EUddRKV_QG0dahnwDUV3Z868T3OzBaqLeoZYYARJwhItWYpzisI6aiD9DpX33-ANYQgMkEL8Fu5e36BqmZD3K_ZetfluNnBJuuUuo0QOVP9nw" alt=""><figcaption></figcaption></figure>

\


<table data-header-hidden><thead><tr><th width="183"></th><th></th></tr></thead><tbody><tr><td><strong>Access</strong></td><td>An agent has multiple user interfaces and front-end integrations into the line of work where people are likely to need it.</td></tr><tr><td><strong>Task Planning &#x26; Automated Querying.</strong> </td><td><p>Agents plan how to complete a task and what questions it must ask to clarify what a human is trying to achieve. </p><p></p><p>Much like a human, they will ensure they have all the information available to conduct the task set for them. </p><p></p><p>All they require to achieve this is integrations into policy, enterprise content and agent configuration. <br></p><p>Each agent is configured to behave in a certain way for a task. For example, policy search agents must be pedantic, to ensure they provide accurate information. They will ask questions back to a human, ensuring they understand what is being asked of them. </p></td></tr><tr><td><strong>Agents completing specific tasks</strong></td><td><p> Agents represent a specific business process. Each agent is an expert at completing a specific task. Agents communicate with other agents to help them complete a series of tasks. </p><p></p><p>A group of agents (called a swarm) becomes a complex, expert system for completing entire business processes, requiring no human input until the final review stage. </p><p></p><p>Imagine a data analyst agent automatically analyzing a salesperson's performance. Then, automatically collaborate with an L&#x26;D programme design agent to create personalised upskilling plans for a human to review.</p></td></tr><tr><td><strong>Data Access</strong> </td><td>It will have access to structured and unstructured data and use a RAG (retrieval augmented generation) process. It should also have a Knowledge Graph to ensure all responses are personalised and clear bias identification and reporting for compliance. </td></tr><tr><td><strong>Tools</strong> </td><td>It has an extensible architecture which allows for the addition of tools (or access to APIs and processes) to push and pull data from other systems. Agents are systems with complex reasoning capabilities, memory, and the means to execute tasks.</td></tr><tr><td><strong>LLM Agnostic</strong> </td><td><p>Agents are not tied to individual LLMs, but can navigate from one LLM to another depending on the task. This abstraction from the LLM is fundamental in the architecture of an Agent infrastructure.</p><p><br></p><p>Each LLM has strengths and weaknesses in completing specific tasks.  </p></td></tr><tr><td><strong>Personality</strong> </td><td><p>Agents can have personas and/or tones of voice and idiosyncrasies to modify the agent’s final response.</p><p><br></p></td></tr></tbody></table>



### Agent Use-Cases 

Agents represent the next big leap in conversational AI. They are real AI co-workers.&#x20;

Agents can perform tasks through analysis, planning, information retrieval, and synthesis from both web-based and internal data sources. They can also automatically interact with other agents.

These agents are not only task-oriented but can also collaborate amongst themselves. Once a goal is set, they autonomously collaborate to achieve the desired outcomes.

Consider, for instance, a smart bot analyzing a salesperson's performance and then collaborating with an L\&D program bot to create personalized upskilling plans ready for human approval.



#### How Agents differ from Assistants

Each agent represents a specific use case and purpose. Often, an agent can be built for a task or role. They can provide answers to any queries, if they have been connected to the right data sources, and execute tasks that align with their role.&#x20;



Think of an Agent as a digital employee hired to perform a specific role. The Agent configuration is much like a job spec, it describes how the Agent should behave, what information it has access to and what process and policies it should follow. \


| <p>HR Use-Case: </p><p><br></p><p>‘How much holiday do we get each year?’</p> |                                                                                                                                                                                  |
| ----------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>Assistant response:</strong></p><p><br></p>                        | According to the company handbook, your holiday year restarts on 1st April.                                                                                                      |
| <p><strong>Agent response:</strong></p><p><br></p>                            | <p>As you are based in EMEA your holiday year restarts on 1st April each year. </p><p><br></p><p>Would you like to know how much holiday you have left to use for this year?</p> |

The Agent's level of knowledge and ability to serve the end user creates an engaging, full-circle experience for end users.

Their only limitation is (a) the data they have access to (b) the tools they can use and ( c) the integrations they can utilize. \


#### Example Agent Use-Cases

**Sales training Agent:** Sales teams can utilize AI to locate specific sales techniques or product information, particularly useful when preparing for pitches or responding to customer inquiries. Depending on the tools, a sales agent could then analyze CRM data, send emails execute other important tasks.  \


**Compliance Agent:** In the context of complex compliance topics, by enabling the tool ‘verification’, the agent will be pedantic and ensure it asks follow-up questions to get someone to the exact answer they need with 100% certainty.&#x20;



**Leadership development:** You could create an agent that represents a specific leader (real or imagined), a specific personality or framework - enabling you to create experiences that help challenge learners, make them think differently and embed their learning in new ways.
