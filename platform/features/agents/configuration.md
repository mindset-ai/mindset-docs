---
description: This article explains how you can configure an Agent.
---

# How to Configure Agents

### An Introduction to Agent Configuration

The Agent's configuration shapes how it behaves and interacts with users. This finely-tuned setup remains constant throughout user engagement, where even small changes in tone or language can significantly affect performance and user perception.

Due to its sensitivity, any modifications to the configuration must be approached with care, ensuring they are carefully evaluated for their impact. Monitoring these changes is essential for maintaining a balance between user satisfaction and the Agent's effectiveness, allowing for ongoing improvement in the interaction experience.&#x20;

This dynamic configuration covers various aspects, from defining the Agent's purpose and personality to establishing operational rules and using specialized tools, all aimed at improving the quality and efficiency of user interactions.

### Purpose

The "Purpose" field outlines the main role or function of the Agent. This could range from customer support, providing information, facilitating transactions, to entertaining users.&#x20;

Defining the purpose is critical because it guides the overall design of the Agent, including its interactions, responses, and the specific needs it addresses for its users.

#### Best Practices

* **Clarity and Specificity:** Clearly define what the Agent is designed to do. A specific purpose enables targeted interactions that meet user expectations.
* **User-Centric:** The purpose should focus on addressing the needs or solving the problems of its users. Understanding your target audience can help tailor the Agent’s purpose to their requirements.
* **Feasibility:** Ensure the purpose aligns with what is technologically possible and practical within your resources and constraints.

**Examples**

1. **Customer Support Agent**

```plaintext
Your role is to assist customers by providing quick and accurate answers to 
inquiries, resolving support issues, and offering information on products and 
services.
```

2. **Policy Explanation Agent**

<pre class="language-plaintext"><code class="lang-plaintext"><strong>Your role is to provide users with detailed, accurate information about policies, 
</strong><strong>regulations, and compliance requirements relevant to their inquiries. 
</strong><strong>You are tasked with guiding users through complex policy landscapes, 
</strong><strong>offering clarifications, and assisting in understanding how policies apply to 
</strong><strong>their specific situations. Additionally, you should help identify steps for 
</strong><strong>compliance and direct users to additional resources or departments when more 
</strong><strong>specialized assistance is needed.
</strong></code></pre>

3. **Life Coach Agent**

```plaintext
Your role is to support users in achieving their personal growth and development 
goals. You will offer motivational guidance, strategies for overcoming obstacles, 
and personalized advice to help users navigate life's challenges. 
By encouraging self-reflection and providing actionable steps for improvement, 
you aim to assist users in realizing their full potential, enhancing their 
well-being, and making positive life changes.
```

### Personality

The "Personality" options set the tone and style of interaction for the Agent. It's crucial for determining how users perceive the Agent's friendliness, professionalism, and approachability. A clearly defined personality ensures a cohesive user experience that matches the brand's voice and meets the audience's expectations.

There are 4 predefined personalities you can choose from for any agent. These personalities are based on our own best practices and offer a safe and simple way to define your agents personality, trouble free.

#### Custom personality

If you find that the predefined personalities do no match your need or don't go far enough, you can select the custom personality option and define your own.

**Best Practices**

* **Consistency:** Ensure the personality is consistent across all configuration fields to build a coherent identity for the Agent.
* **Alignment with Purpose:** The personality should complement the Agent's purpose. For example, a Coaching Agent might have a motivational and empathetic personality, while a Policy Explanation Agent might adopt a more formal and precise tone.
* **Audience Awareness:** Tailor the personality to suit the preferences and expectations of the target audience. Consider cultural nuances and language preferences.

**Examples**

**1. Customer Support Agent**

```plaintext
Uses positive language and expresses empathy to ensure users feel heard and 
supported throughout their interaction.
```

**2. Policy Explanation Agent**

```plaintext
Utilizes precise language and maintains a neutral tone to convey information 
accurately and efficiently.
```

**3. Coaching Agent**

```plaintext
Engages users with motivational language, offers encouragement, and demonstrates 
understanding of users’ personal growth challenges.
```

### Output Formatting

The "Output Formatting" field determines how the Agent's responses appear to users. It covers language use, formatting (such as bullet points or paragraphs), and including visuals or links when needed. Good output formatting improves readability, clarity, and the user experience.

**Best Practices**

* **Clarity and Consistency:** Maintain a clear and consistent formatting style throughout the Agent's interactions to help users easily understand and follow the information provided.
* **User-Friendly Layout:** Use bullet points, numbered lists, and short paragraphs to break down complex information into manageable pieces.
* **Adaptive Formatting:** Tailor the formatting to the type of information being delivered and the platform through which the Agent is accessed, considering the limitations and advantages of each platform.

**Examples**

**1. Customer Support Agent**

```plaintext
When providing step-by-step instructions, use numbered lists to guide the user 
through the process.
- For FAQs, present the question followed by a concise answer in a new paragraph.
- Use bullet points to list options or features.
```

**2. Policy Explanation Agent**

```plaintext
Present policy summaries in short, clear paragraphs.
- Use bullet points to highlight key policy points or requirements.
- Include links to full policy documents for detailed reading.
```

**3. Coaching Agent**

```plaintext
Offer advice and tips in a friendly, conversational tone, using short paragraphs.
- Use bullet points for action items or strategies.
- When sharing resources or exercises, include clear headings and concise descriptions.
```

### Icebreaker Message

The Icebreaker Message is the initial prompt sent to the Agent, instructing it on how to begin interactions with users. This message is crucial for setting the interaction's tone, providing the Agent with guidance on introducing itself, stating its purpose, and inviting user engagement in a concise manner. The goal is to create a welcoming environment that encourages users to start their inquiry or discussion.

**Best Practices**

* **Clear Instructions:** Provide the Agent with straightforward instructions on greeting the user, introducing itself, and stating its purpose.
* **Conciseness:** Ensure the message is brief yet informative enough to guide the Agent without overwhelming the user.
* **Engagement:** Include a prompt that invites the user to engage, such as asking how the Agent can assist.

**Examples**

**1. Customer Support Agent Instruction**

```plaintext
Greet the user warmly, and introduce yourself as a Customer Support Agent designed 
to assist with inquiries and issues, and ask how you can help them today.
```

**2. Policy Explanation Agent Instruction**

```plaintext
Begin by welcoming the user, then explain that you are here to provide clear 
explanations of policies and procedures. Prompt the user to specify the policy 
the information they are seeking.
```

**3. Coaching Agent Instruction**

```plaintext
Start the conversation by introducing yourself as a Coaching Agent focused on 
personal growth and motivation. Encourage the user to share their goals or challenges 
you might help them with.
```

### Policy Rules

The "Agent policy" options are vital for establishing operational guidelines that outline the boundaries of the Agent's actions. It covers restrictions on the Agent's responses and behaviors, safeguards against overstepping its designated role, and measures to prevent unauthorized actions. These rules ensure the Agent stays on track, adheres to ethical standards, and delivers a secure, dependable experience for users.

As with personality, we provide a number of predefined and tested policies. You can mix and match the required policies available, add your own policy, or enrich the available policies with additional policy rules.

**Best Practices**

* **Specific Limitations:** Clearly define the scope of tasks and topics the Agent can address, including explicit mentions of actions or query types it should not attempt to handle.
* **Jailbreak Prevention:** Incorporate specific rules or phrases that the Agent recognizes as cues to avoid engaging in behaviors that could lead to bypassing its operational constraints.
* **User Guidance:** Inform users about the limitations of the Agent’s capabilities and suggest alternative actions or referrals when requests fall outside the Agent's scope.

**Examples**

**1. Customer Support Agent**

```plaintext
Avoids engaging in personal advice or topics unrelated to customer support.
```

**2. Policy Explanation Agent**

```plaintext
Refrains from offering personal opinions on policy matters.
```

**3. Coaching Agent**

```plaintext
Do not provide medical, legal, or financial advice. 
Encourages users seeking such advice to consult with qualified professionals.
```

### Additional Information

The "Additional Information" field provides crucial background or context for the Agent's interactions. This might include guidance on tone, references to external knowledge, or instructions for handling sensitive topics. It ensures the Agent's responses are well-informed by factors beyond its usual knowledge.

**Best Practices**

* **Specificity:** Clearly define the additional parameters or considerations the Agent must account for in its interactions.
* **Relevance:** Ensure all provided information is relevant to the Agent's purpose and the types of interactions it will have.
* **Conciseness:** Offer this information in a concise manner to avoid overloading the Agent, ensuring it remains focused and effective.

**Examples**

**1. Customer Support Agent**

```plaintext
<< specific information the agent might use to provide links to support sites >>
```

**3. Coaching Agent**

```plaintext
<< a summary of the coaching methodology and key concepts >>
```

**2. Policy Explanation Agent**

```plaintext
<< contact information for the policy team >>
```

### Spelling

You now have the option to switch automatically between US and UK spelling for agent responses.&#x20;

* If this toggle is turned on, automatic conversion from US to UK spelling will be disabled.&#x20;
* If this toggle is turned off, all US spellings will automatically convert to UK spellings.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-06-17 at 16.40.16.png" alt=""><figcaption></figcaption></figure>
