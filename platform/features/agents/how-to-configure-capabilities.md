---
description: What are Capabilities and how to configure them
---

# How to configure Capabilities

### What are Capabilities?&#x20;

Capabilities are pre-established paths of actions that agents can follow in a logical sequence to accomplish specific tasks. They are designed to enhance the user experience by streamlining the process of defining agent behavior, making it easier for users to interact with agents without prior knowledge of their functions. \
\
Capabilities allow agents to be more human-like in their interactions, offering a more intuitive and engaging user experience.  Capabilities empower the agent to become more specific and focused in its tasks, which can lead to better performance and outcomes.

### **How to Configure Capabilities**

Firstly on the left hand navigation of the administration portal go to **Manage** > **Agents** and select your **Agent** (you will need to have configured the **General Settings** and **Behaviour** tabs of your Agent first where you define the Agent's purpose, personality and rules): &#x20;

<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 13-46-44.png" alt=""><figcaption></figcaption></figure>

Next select the **Capabilities** tab:

<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 15-53-57.png" alt=""><figcaption></figcaption></figure>

You can choose to keep toggled on or toggle off **Display Capabilities as options.**  By keeping the toggle on this will display the Capabilities for this agent as options with the **/ key.** What this means is that at the **front end** of the application, the **/ key** can be seen to the left of the **Ask** the Agent bar for the user to select and view the list of Capabilities for that specific Agent. Or the user can add **/** to the Ask bar as an alternative way to bring up the list of **Capabilities**.\


<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 13-53-03_10 (1).png" alt=""><figcaption></figcaption></figure>

Next, in the Capabilities tab, select **Add Capability** to start configuring your **Capabilities**:\


<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 15-54-55.png" alt=""><figcaption></figcaption></figure>

Firstly you can toggle on **Hide this capability in prompts & options** if you do not want this capability to be displayed as an option with the **/ key** (as detailed above).\
\
Then add the **Capability Prompt** that would be shown to the user when they select the **/ key.**&#x20;

<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 12-18-38_5 (4).png" alt=""><figcaption></figcaption></figure>

Another example of a **Capability Prompt** could be _**Hunt for a policy problem**_ for a Policy Agent.  \
\
Next, add the **Automatic Trigger Scenario:** \
\
Here enter a detailed description of the specific conditions or events that will activate the capability. Describe the scenario clearly and concisely, focussing on the key elements that must be present for the capability to be triggered.  This could be a specific phrase, a set of keywords, or certain conditions.  When the defined scenario occurs, the system recognizes it and automatically activates the capability.

<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 14-26-49 (1).png" alt=""><figcaption></figcaption></figure>

Another example of an **Automatic Trigger Scenario** could be _**If the user is concerned that they may have violated a SAAR or GDPR policy**_ for a Policy Agent.  \
\
If the **Automatic Trigger Scenario** field is left blank then this capability is never automatically triggered.\
\
Next, add the **Process steps:**\
\
The Process steps outline the sequence of actions or operations that they Agent should follow to fulfil this capability once the interaction has started. Process steps are crucial for creating a smooth and intuitive user experience as they help in structuring the interaction between the user and the system. Each step should be clear and concise providing the necessary information and guidance to move the user forward without any confusion.\
\
Firstly select **Add Step**:

<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 12-35-21_7.png" alt=""><figcaption></figcaption></figure>

Once the first step has been added select **Add Step** to keep adding further steps, you can **remove empty steps** and **re-order** the steps by selecting the icon to the right of the steps:\


<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 13-18-53_8.png" alt=""><figcaption></figcaption></figure>

Then continue adding the remaining **steps,** like below as an example:\


<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 13-29-39_9.png" alt=""><figcaption></figcaption></figure>

An example of **Process steps** for the **hunt for a policy problem** Capability Prompt could be:\


<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 15-36-06.png" alt=""><figcaption></figcaption></figure>

Once you are happy with your process steps, select **Save**.

**Please note:** capabilities cannot have only 1 step, in this instance, the capabilities will not function in your agent. They require more than 1 step to work effectively.&#x20;

### Testing Capabilities 

**Testing** the **Capabilities** you've configured is essential to ensure your agent is performing as expected.  To do this interact with your agent using the capabilities you've configured.  Provide it with scenarios and inputs that the capability should handle.  Carefully observe the agent's responses to ensure they align with the expected outcomes.\
\
If the responses don't meet your expectations, adjust the Capabilities configuration and retest until the desired outcome is achieved.\
\
Select the **Test** tab, and the **/ key** and select your Capability. or just start interacting with your agent by asking questions using the **Ask** bar.\
\


<figure><img src="../../../.gitbook/assets/Summit10 2024-03-11 16-00-45.png" alt=""><figcaption></figcaption></figure>
