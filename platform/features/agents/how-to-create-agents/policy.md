---
description: Learn about the Policy options within the Agent workflow.
---

# Policy

The P**olicy** section provides guidelines to keep the agent on track and within your defined scope. Unlike other sections, you can apply multiple policy options at the same time, which combine to produce a focused and consistent agent.  Many of the options available under the policy heading have additional supporting fields to help define the policy boundaries.

You can include additional policy rules if you want to enhance the policy option available, or can use this field on its own to define a policy behavior from scratch.

<figure><img src="../../../../.gitbook/assets/image (29).png" alt=""><figcaption><p>Agent policy</p></figcaption></figure>



<figure><img src="../../../../.gitbook/assets/Screenshot 2024-08-09 at 13.32.25.png" alt=""><figcaption></figcaption></figure>

One of the pre-configured policy options is 'Feedback Encouragement'. If this option is selected in the agent configuration, it means that any feedback provided by the user will only be relevant within the thread that it is given. This feedback will not train the agent in their long-term responses, nor will it impact any other user's responses, agent responses, or thread responses.&#x20;

If the 'Feedback Encouragement' policy option is selected for an agent, it will increase the number of times the LLM asks 'how am I doing'.

### Additional Information

The **Additional Information** field provides crucial background or context for the Agent's interactions. This might include guidance on tone, references to external knowledge, or instructions for handling sensitive topics. It ensures the Agent's responses are well-informed by factors beyond its usual knowledge.

<figure><img src="../../../../.gitbook/assets/summit10 2024-07-22 13-20-43.png" alt=""><figcaption></figcaption></figure>

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
<< contact information for the policy >>
```
