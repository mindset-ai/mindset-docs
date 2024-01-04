---
description: Everything you should consider when engaging with an AI company.
---

# AI Buyers Guide

\
AI Buyer's Guide: What Really Matters.

## AI Buyers Guide: What Really Matters

This guide aims to provide businesses with crucial considerations when investing in AI technology.

## 1. Accuracy&#x20;

Accuracy is one of the most important focuses for any AI buyer. Currently, companies do not pay much attention to the accuracy of responses from AI vendors. In 2024, as buyers become more educated, this will start to change.&#x20;

<mark style="background-color:blue;">**What techniques and technology processes have you used to increase the accuracy of responses?**</mark>

Because the questions we ask Large Language Models (LLMs) heavily influence their outputs, “prompt engineering” is a key part of getting LLMs to do what we want them to do. This entails testing how close different methods of prompting LLMs (i.e., asking them questions) get us to our desired LLM responses.&#x20;

**Capabilities to look out for:**&#x20;

**RAG (Retrieval-Augmented Generation):** RAG is a highly advanced AI system that combines the abilities of a search engine (retrieval) and a content generator (generation). It can understand complex queries, search for information, and then generate detailed and contextually relevant responses. It will know where the source of that information came from, requiring an indexing process to be successful.

Stanford University found that RAG could enhance data retrieval accuracy by 25% compared to basic LLMs.

**Chain of Thought:** Traditional methods often involve providing the model with a single prompt-answer model to receive a response. This approach can be limiting in terms of the complexity of problems that the model can solve, or when a high level of accuracy is required.&#x20;

Chain-of-thought methods, on the other hand, are akin to a logical reasoning process. This approach enables AI to analyse and process information in a structured manner, by breaking down complex problems into smaller, manageable components. Each step in the chain represents a logical thought process or action, and together, they lead to a comprehensive understanding and solution

A Chain-of-Thought approach has a huge number of benefits. When it comes to accuracy, instead of relying solely on surface-level information, Chain-of-Thought allows AI to dive deep into the details of a question or problem. It explores multiple angles and considers various factors, leaving no stone unturned.

**Knowledge Graph**: Knowledge graphs are structured representations of knowledge that use a graph-based model to connect entities and concepts. They consist of nodes (representing entities or concepts) and edges (representing relationships between them). &#x20;

Knowledge graphs store a variety of data, including information about people, their relationships, events, locations, concepts and terminology that is specific to a company.&#x20;

For instance, they can record how employees in a company are connected, track the participants in various events, link individuals to specific projects, note office locations, and establish connections based on common topics. Knowledge graphs enable AI to make sense of intricate data connections and deliver precise information.



<mark style="background-color:blue;">**How do you stop inaccuracies from reaching end users?**</mark>

No matter how good AI gets, there can still be mistakes. Every AI vendor must have capabilities which stop any inaccurate responses from reaching end-users.&#x20;

**Capabilities to look out for:**&#x20;

**Validation Pipelines**: Validation pipelines are designed to catch and rectify inaccuracies from LLMs before they reach end users.

**Fail-Safes**: Fail-safe mechanisms that can detect when an AI is likely to generate inaccurate or nonsensical responses and prevent them from being delivered to users, as well as providing controls to ensure the AI will not respond to questions which are nonsensical.

**Diverse Data Sources**: Draw from diverse data sources to provide a well-rounded understanding of topics, reducing the risk of bias and inaccuracies.

**Feedback Loops**: Continuously gather feedback from users and data sources, then incorporate it into model updates and improvements.

\
<mark style="background-color:blue;">**How do you train the AI to improve responses for my business?**</mark>&#x20;

**Capabilities to look out for in a vendor:**&#x20;

**Feedback Loops**: Continuously gather feedback from users and data sources, then incorporate it into model updates and improvements.

**Knowledge Graphs:** All data, when stored in a knowledge graph, becomes something that AI can continually train on without the buyer needing to invest resources into improving answers manually.&#x20;

**Data Visualisation**: The vendor should provide ways for the buyer to visualise all data that has been uploaded. For example, a document may be titled ‘Annual Leave Policy’ but the document covers a huge amount of topics which are unrelated to annual leave or even HR due to human error. The buyer must be able to visualise this data to ensure accurate responses.

**Simulations**: The buyer should be able to ask the system to simulate all possible questions and responses based on the data. The system must then identify outliers to the buyer which are inaccurate or questionable.&#x20;

<mark style="background-color:blue;">**How do you ensure all AI responses are personalised?**</mark>&#x20;

**Knowledge Graphs**: Knowledge graphs store a variety of data, including information about people, their relationships, events, locations, concepts and terminology that is specific to a company. This enables the AI to personalise responses.

**Context Integrations**: The AI vendor must be able to integrate with an active directory or another source of data which provides context on the user to personalise responses.&#x20;

<mark style="background-color:blue;">**How do you ensure end-users trust AI responses?**</mark>&#x20;

**Capabilities to look out for in a vendor:**&#x20;

**Source Content**: The source content for the response is critical. People trust responses most when the source material is provided to them. Most importantly, the user must be able to visit the source material and be taken to the exact segment of text the answer was derived from when possible.&#x20;

**Human in the Loop**: There must be mechanisms in place to ensure questions and tasks can be routed to a human.&#x20;

**Personalisation**: People trust AI when the responses are highly personalised, demonstrating the system understands the person it is speaking with.&#x20;

## 2. Security & Data Managment

For an AI solution to be successful, it must process a significant portion of your enterprise data. From documents, processes and even contextual data about a user.&#x20;

<mark style="background-color:blue;">**How are third-party AI vendors chosen?**</mark>

Vendors should be able to provide a full process and system for selecting third-party AI vendors.&#x20;

<mark style="background-color:blue;">**What data is collected and incorporated into AI interactions?**</mark>

**Capabilities to look out for in a vendor:**&#x20;

**Client's IP**: The client's IP should be synthesised into the platform.&#x20;

**Anonymised Usage Data**: This includes anonymised user queries, usage metrics, user learning pathway data, user attributes, feedback metrics related to the chatbot, and general system usage. Collected usage data allows us to enhance system performance and provide more relevant responses.

**User-Specific Information**: The information gathered during user onboarding and subsequent interaction with the system is used to personalise user experience, helping tailor responses to be more relevant and effective.

<mark style="background-color:blue;">**How does your AI solution ensure the security of sensitive data, and what measures are in place to prevent data leakage to the LLM?**</mark>

When it comes to data and security, there are many well-known good practices expected from technology providers. However, when it comes to AI solutions, there are now many new approaches vendors can take to protect from data issues that can arise from LLMs.

**Here are some capabilities you can look out for:**

**Continuous Monitoring and Audits**: Systems that continuously monitor LLM interactions. Regular audits must be conducted to ensure that all data protection protocols are adhered to, and any anomalies are promptly addressed.

**Differential Privacy**: This is a technique that introduces "noise" into the data, ensuring that any output from the LLM cannot be reverse-engineered to identify the original input. By adding this layer of differential privacy, AI solutions can ensure that the data remains indistinguishable and protected.

**Data Isolation**: Isolating data for specific companies, ensuring that different customers' data does not get leaked to the LLM, and no data is used across different customers.&#x20;

\
<mark style="background-color:blue;">**How does your platform ensure the safety of sensitive data?**</mark>

**Capabilities to look out for in a vendor:**&#x20;

\
**Zero Trust Security Model**: This means that no one, whether inside or outside the organisation, is automatically trusted with access to data or systems.

**Strong Authentication Practices**: Using multiple methods or factors to verify the identity of a user or system trying to access data or a system.

**A Shift-Left Approach**: Security becomes an integral part of the development process from the very beginning. This means that as developers are writing code, they are also considering and implementing security measures.

**GDPR Compliance**: Adherence to the EU's General Data Protection Regulation.

**Data Encryption**: Does the platform employ strong encryption mechanisms to protect data both in transit and at rest? This is non-negotiable for safeguarding sensitive information.

**Authentication Methods**: Evaluate the platform's authentication options. Multi-factor authentication (MFA) adds an extra layer of security to user access.

**Audit Trails**: Does the platform maintain detailed audit logs of user activities and system events? This is crucial for monitoring and investigating security incidents.

**Data Residency**: Consider where your data will be stored. Some platforms offer options for data residency to comply with regional regulations.

**Access Controls**: Can you define and enforce granular access controls? Ensuring that only authorised personnel can access specific data is fundamental to security

### 3. Bias Mitigation

Work on bias identification and mitigation is changing fast. Ultimately, the underlying LLM cannot be understood. OpenAI cannot explain ChatGPT. However, identifying how your data set has biased the underlying model is essential.&#x20;

\
<mark style="background-color:blue;">**What are you doing to identify and mitigate bias?**</mark>&#x20;

**Capabilities to look out for in a vendor:**&#x20;

**Data Visualisation**: The vendor must be able to visualise all data that has been synthesised into the platform to identify how your system has been biased.&#x20;

**Simulations**: Vendors must be able to simulate responses and questions by users, before deployment and on a consistent basis.&#x20;

For example, the system must be able to generate possible combinations of questions asked to test itself, with an identification system that enables buyers to spot biased answers, identify how the answer was biased and be able to correct the problem quickly.&#x20;

\
