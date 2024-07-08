---
description: >-
  This page addresses the fundamental questions anyone considering AI should
  know about the vendor's approach to AI and data and the use of third-party AI
  in their solution.
---

# AI Guidelines

## AI Q\&A

### What are you doing to mitigate bias in your AI?

The Mindset AI system uses a RAG process to help our clients' users get to information and trigger automated actions efficiently. Each client’s instance is entirely separate and is fed from their nominated IP (a knowledge base in the form of documents, recordings, videos, etc).

The first major potential source of bias in such a system is source material bias: RAG systems retrieve information from a knowledge base or external sources to generate responses. The generated responses can inadvertently reflect these biases if these sources contain biased information or lack diverse perspectives. For instance, if the knowledge base is heavily skewed towards certain political views or lacks representation of certain cultures, the responses generated could be similarly skewed.

Mindset AI’s goal is to help our clients successfully manage their AI Agents, and the principal step to crafting a successful AI Agent is to feed it with a well-rounded body of knowledge. To accomplish this, we are developing ways of identifying “blind spots” in a client’s knowledge base and reporting this information to them with actionable insights so that they can remedy the situation.

Another type is inherent adverse bias in interpreting the source material, where the system consistently and unfairly disadvantages certain groups or individuals based on characteristics like race, gender, age, location, etc.

Mindset AI conducts regular system bias audits where we simulate several reversed controlled experiments on many cohorts of synthetic users.

These synthetic cohorts are diverse in demographics, and the expectation is that system responses to two synthetic users in similar contexts but with different demographics should mostly be similar. Detected discrepancies are identified and form the basis of an actionable report we make available to our clients.

### What is the high-level explanation of your AI process?

At a high level, the Mindset AI system for any particular client consists of:

* A process by which the client’s IP is assimilated into their instance of the Mindset Knowledge Graph.
* The client-segregated instance of the Mindset Knowledge Graph.
* A process by which their user engages with the Knowledge Graph using asking questions (“Ask”) and conversationally triggering predefined actions (“Do”).



IP ASSIMILATION

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Fig 1. Assimilation of IP</p></figcaption></figure>

The ingestion of clients’ IP documents follows a process that starts with text extraction and document format abstraction. This is followed by the semantic segmentation of the extracted text, speaker detection and identification (in the event of audio/video input), topic detection, text splitting and embedding, and knowledge-entitlement segregation.

* Assimilated IP is never used to train any LLM shared between clients nor used for any process other than answering questions posed by users of the Agents created by your organization for your purpose.
* Data is stored in GCP (Google Cloud Platform) hosted databases and secured with row-level security, which Google manages.



MINDSET KNOWLEDGE GRAPH

The Mindset Knowledge Graph is a collection of different databases; each used to aid the efficient and contextual retrieval of client IP document fragments. This collection stores IP such that the contents and the context of information are equally important.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption><p>Fig 2. The Knowledge Graph</p></figcaption></figure>





USER INTERACTIONS WITH THE KNOWLEDGE GRAPH

Users interact with the Knowledge Graph through an embedded chat interface where they can get answers to their questions (“Ask”) and also trigger predefined actions (“Do”).

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption><p>Fig 3. Interaction with the Knowledge Graph</p></figcaption></figure>

This interaction flow starts with the user’s input passing through an entitlement filter, where the specific information that the user is entitled to is determined. After this, the best Knowledge Graph elements are fetched, and, based on the user’s specific context, the best answer/action strategy is decided on. Suppose a semantic interface (LLM) is needed. In that case, the best interface is chosen based on availability and specialization to the task (Mindset is LLM agnostic in that we can route to GPT, Claude, PaLM, etc.)

If the request is for information (“Ask”), the LLM’s output is returned to the user.

### How do you ensure humans understand when they are interacting with AI?

Each interaction with an Agent starts with a Disclaimer message, which explains that the Agent is an AI and the specific limitations of the Agent.

### What are your AI ethical principles?

Our goal is to build an AI-powered system that is honest, helpful, and harmless.

HONESTY

* **Accurately reflect the client IP:** Enable our clients to craft knowledge bases containing accurate and reliable information.
* **Transparency in Responses:** We communicate the source of the information (answers) provided by the system, enabling users to zero in on the specific IP fragments that informed the system’s response

HELPFULNESS

* **User-centered Design:** Our system is tailored to address user needs effectively. This includes understanding the context of queries and providing relevant and actionable responses.
* **Personalization within Ethical Bounds:** The system offers personalized responses where appropriate and ensures that personalization does not infringe on user privacy or ethical standards.
* **Continuous Learning and Improvement:** We use user feedback and interaction data to improve the system's ability to provide helpful responses.

HARMLESSNESS

* **Bias Mitigation:** We regularly audit the system for biases in available content, content retrieval, and generation. This includes monitoring for gender, racial, cultural, or any other form of bias.
* **Content Moderation:** We have mechanisms for reporting instances where users feel the generated responses were wrong, biased, or inappropriate. These reports are routed to the appropriate stakeholders for action.
* **Safety Protocols:** We have protocols for handling sensitive topics, including directing users to human experts or authorities when necessary (e.g., in cases of legal advice, health emergencies, etc.)

### How does the AI improve the user experience?

At Mindset AI, the AI enhances the user experience through real-time, context-aware responses, ensuring precision and relevance. Automated actions simplify processes, while grounded answers build trust. Iterative learning ensures continual enhancement, empowering users with accurate and helpful interactions.

### Where does the AI add value?

VALUE TO USERS

As a conceptual AI agent, the platform is designed to provide real-time, contextual responses, optimizing users' access to the right information when needed. User questions trigger the generation of informational responses and predefined automated actions, simplifying various processes.

VALUE TO CLIENTS

Mindset-AI provides several benefits to our clients, helping them deliver an enriched and seamless user experience. Mindset’s AI system strengthens our clients' offerings by enabling them to offer real-time, informed responses via AI Agents. This aids in handling queries and automatically triggering actions based on user inputs. Integrating our clients' IP into the secure Mindset Knowledge Graph gives them a sturdy system for managing their IP and providing value to their users. Firebase Authentication and our robust security framework guarantee the highest level of data security.

Most importantly, our AI Agents work as a tool, helping clients shape informed decisions and stay in full control of the information flow. The context-aware system helps clients provide information and empower their users with knowledge. Finally, our iterative approach to integration eases maintenance and ensures seamless integration with various platforms, enhancing overall efficiency.

## Data Q\&A

### What data is collected?

At Mindset, we primarily collect data to enhance the functionality of our products and improve our user experience. We follow the principles of data minimization, only collecting pertinent data required for the product's functioning.

Here are the main types of data collected:

* **Client's IP:** The client's IP is integrated into the Mindset Knowledge Graph. Our clients have a separate tenant in the Knowledge Graph that only they can access.
* **Anonymized Usage Data:** This includes anonymized user queries, usage metrics, user learning pathway data, user attributes, feedback metrics related to the chatbot, and general system usage. Collected usage data allows us to enhance system performance and provide more relevant responses.
* **User-Specific Information:** The information gathered during user onboarding and subsequent interaction with the system is used to personalize user experience, helping us tailor our responses to be more relevant and effective.

The data collection is in line with legal requirements, ethical guidelines, and the principle of data minimization; we collect only essential data required for service improvement and personalization. It's critical to note that we maintain the highest level of anonymity and confidentiality in our data collection process.

### How is data used?

At Mindset AI, our primary focus regarding data usage is improving our products and services.

Client-owned IP integrated into our Mindset Knowledge Graph is essential for answering user queries and informing automated actions. However, we assertively state that this data doesn't contribute to training the commercial large language models (LLMs) that our system uses as a semantic interface.

Instead, the training data for our LLMs is explicitly provided by and external LLM and stands independently of the client IP. Therefore, client data usage solely focuses on enhancing services specific to the client.

In our continuous bid to uphold client data's confidentiality, integrity, and availability, we ensure that our data usage policies are transparent and prioritize informing clients promptly about any changes.

### How is data stored?

DATA STORAGE

Mindset-AI houses data using the Google Cloud Platform (GCP), leveraging a modern, serverless architecture to guarantee robust data security. Our use of GCP ensures that your data is retained in a highly secure, encrypted environment, offering state-of-the-art protection.

We use Firebase Authentication, a robust service provided by Google, to manage authentications. With this, Mindset-AI ensures that access to stored data aligns with our strict access control and governance policies. These meticulous measures keep your data secure, easily retrievable, and appropriately isolated, guaranteeing the integrity and availability of your data at all times.

DATA POLICIES

We prioritize our clients' data security.

**Zero Trust Security Model:** We enforce strict identity verification for every person and system trying to access resources on our network, regardless of location.

**Data Isolation:** We adhere to a stringent separation of data, ensuring that each client's data is confined in a secure environment, secluding it from other clients’ data.

**Mindset’s AI Guardrails:** These ensure the safe and ethical use of pre-trained AI models and tackle potential vulnerabilities.

**Firebase Authentication:** We use Firebase Authentication to manage secure access to stored data.

Through our meticulous measures, we put multiple layers of protection between threats and your data, ensuring its security at all points. A dynamic and vigilant approach is always at play, aiming to detect and rectify potential threats swiftly.

### How is data shared?

At Mindset AI, we believe conducting business with integrity includes maintaining transparency about our data policies:

**Data Sharing:** We strictly follow a 'No Third-Party Sharing Policy'. We do not share, sell, or trade our clients' data with third parties or other clients under any circumstance. Your data and IP stays exclusively within the purview of Mindset AI to enhance the product we deliver and the services we offer you.

**Transparency:** We prioritize keeping our clients informed if there are any changes to our data handling policies. Any updates in the data usage policies are shared promptly with our clients to ensure maximum transparency.

### What data protection regulations are followed?

Mindset AI is committed to ensuring compliance with data protection regulations, including GDPR and CCPA. We prioritize user privacy by adhering to strict data collection, storage, and usage guidelines in line with legal requirements. Our approach revolves around data minimization, ensuring that only essential data required for service improvement and personalization is collected. We maintain the highest level of anonymity and confidentiality in our data collection process, safeguarding user privacy and upholding ethical standards. Additionally, we inform clients about changes in our data handling policies, ensuring transparency and mutual trust.

## Agent Q\&A

### How are humans kept in the loop?

OBJECTIVITY

At Mindset AI, we believe in the mantra, 'AI works best with human involvement.' We offer a user-centered design that facilitates open and continuous interaction between our AI system and the user, creating a feedback loop that sharpens the system's responses over time.

Additionally, our AI Agents are crafted as tools to assist rather than replace their human counterparts, enabling users to make enlightened decisions – based on system responses – while keeping a full command over the overall process.

We fundamentally believe in the principle of human-in-the-loop as a significant step towards creating a more beneficial and effective AI solution.

A good example of Mindset-AI's commitment to the human-in-the-loop model can be seen in its Content Moderation feature. If users feel that the AI system generates a wrong, biased, or inappropriate response, they can report this instance. These reports are made available to the appropriate stakeholders for review and action. In this way, Mindset-AI ensures that human judgment is involved in refining and improving the AI system, thus keeping a human actively involved in the loop.

### How is user feedback incorporated?

FEEDBACK

We currently gather quality-type signals from empirical usage, with plans to gather many more. This is in the form of user answer ratings (binary: thumbs-up and thumbs-down) but will be expanded to a star score and/or qualitative written/spoken input on user experience and answer quality. This signal is used to (a) report back to the admins of the system on “which types of questions are typically garnering negative user feedback” and (b) to provide our system with a set of subjectively well-answered questions for automated client-specific quality assurance processes.

We believe a system where different users’ feedback is weighted differently: the feedback from specific users (system admins, SMEs, early adopters) would have a higher weight.

We see the feedback loop from user to admin as vital: enabling the administrators to know to feed the system with the right, high-quality information is key to end-user engagement.

### How are the Agents’ output explained to users?

EXPLAINABILITY

A core part of Mindset’s value proposition is to foster user knowledge exploration. We do this by accompanying Agents' responses with contextual information, like the specific media segments from the Knowledge Graph related to the provided answer and the core concepts close to this conversation.

### How do you ensure that the Agents are working optimally?

VALIDITY

At Mindset-AI, evaluating RAG Agents is pivotal to ensure their effectiveness. We rigorously monitor their performance across the three key metrics of the RAG Triad: Answer Relevance, Context Relevance, and Groundedness. By scrutinizing these fundamental aspects, we guarantee that our RAG Agents provide precise, contextually relevant, and grounded responses, securing quality and reliability in user interactions.

### What steps are taken to ensure the Agents cannot be interfered with?

SECURITY

At Mindset-AI, we prioritize rigorous security measures to safeguard our RAG Agents against potential interference. We apply Input Validation and Sanitization to neutralize harmful inputs. Our secure API integration fortifies protection against potential breaches while consistent usage and behavior monitoring detect abnormal activities. Additionally, rate limiting cancels out high-frequency request attacks, making prompt injections unviable. Ultimately, users must pass our robust authentication before interacting with the RAG Agents, ensuring only authorized access. Through these layers of protection, we strive to deliver a smooth, secure, and reliable user experience.

## 3rd Party AI Vendors

### How are 3rd party vendors chosen?

SUITABILITY

At Mindset-AI, we're deliberate and meticulous in selecting third-party vendors like OpenAI. A key criterion is IP Protection; we ensure that our client's data is never used to train the vendors' models, preserving the integrity and confidentiality of client data.

Coming from the belief that we stand on the shoulders of giants, we capitalize on the excellent foundational work of such reputable vendors while contributing our unique, innovative layer to refine and advance their offerings.

We also look keenly into the vendor's specialty. Each provider brings unique strengths to the table, and we select the most suitable tool for the job, even if it means adapting it to our specific requirements. The dependability of a vendor is quintessential in our selection. We opt for reliable and trustworthy vendors with a proven track record.

Lastly, while we appreciate quality and reliability, we also know the cost. We strive for a careful balance of cost-effectiveness without compromising product quality and client satisfaction.

### 3rd Party Vendor Privacy and Security Commitments&#x20;

| Service provider | Purpose                                             | Security information                                                                                                                                         |
| ---------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| OpenAI           | LLM response generation                             | <p><a href="https://openai.com/enterprise-privacy#our-commitments">Privacy commitments</a></p><p><a href="https://trust.openai.com">trust.openai.com</a></p> |
| Pinecone         | Vector database mapping topic and context           | [Pinecone security documentation](https://www.pinecone.io/security/)                                                                                         |
| Assembly AI      | Audio Visual content transcription and segmentation | [Assembly AI security documentation](https://www.assemblyai.com/security)                                                                                    |
