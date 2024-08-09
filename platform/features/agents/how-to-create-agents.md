---
description: An Introduction to Creating your Agents
---

# How to Create Agents

## **Adding an Agent**

In order to add a new agent in your application, you will first need to be in the administration portal. Locate the '**Agents**' tab in your left-hand navigation bar under **'Manage'.**&#x20;

When agents have been created, you'll find a comprehensive list of your previously configured ones along with their corresponding handles displayed here.

For instance, within this application, the agents named Michelle and Angie have been set up. Their respective handles, @Michelle and @Angie, are visible in the list under the '**Agents**' tab.

<figure><img src="../../../.gitbook/assets/summit10 2024-07-08 13-52-33.png" alt=""><figcaption></figcaption></figure>

To initiate the creation of a new agent, select the '**add an agent**' button. Each agent represents a specific use case and purpose. Often, an agent can be built for a task or role. They can provide answers to any queries, if they have been connected to the right data sources, and execute tasks that align with their role.

### Setting up your agent

After clicking the '**Add an agent**' button, you'll gain access to configuring the agent according to your preferences.

#### Settings

Under the '**Settings**' tab, you can add the basic details for your agent:

* **Agent name**, **Agent handle**, and **Agent description** are used for identification and display to help you and your users recognize the agent. Both **handle** and **description** can be visible to users of your application.
* **Agent purpose** is a very important field and has a significant impact on the way your agent will behave, how it will interpret questions, and how it will structure answers.
* **Agent visibility**. Toggling this button on will enable your end-users to see and interact with the agent created, in the front-end of the application. We recommend that all the agent configuration and testing be completed prior to enabling its access to end users.&#x20;

<figure><img src="../../../.gitbook/assets/summit10 2024-07-22 13-13-55.png" alt=""><figcaption></figcaption></figure>

#### Personality

The personality tab is where your define the agents personality.  This will impact the tone of responses and the way the agent will format its responses.

You can select from a number of preconfigured **personality** and **output formatting** options, or choose custom and create your own.  We advise significant testing if you go with the custom option to ensure that the agent responds in a reliable and consistent manner.

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption><p>Agent personality</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (26).png" alt=""><figcaption><p>Output formatting</p></figcaption></figure>

You can also add in the **Icebreaker message instructions** which will define how an agent first greets the user.

<figure><img src="../../../.gitbook/assets/summit10 2024-07-22 13-16-26.png" alt=""><figcaption></figcaption></figure>

_**Please note:**_ You can find more information about each of these by either clicking the small question mark icon next to the headings or alternatively clicking [here](https://docs.mindset.ai/platform/features/agents/how-to-configure-agents).

#### Policy

The **policy** section provides guidelines to keep the agent on track and within your defined scope. Unlike other sections, you can apply multiple policy options at the same time, which combine to produce a focused and consistent agent.  Many of the options available under the policy heading have additional supporting fields to help define the policy boundaries.

You can include additional policy rules if you want to enhance the policy option available, or can use this field on its own to define a policy behavior from scratch.

<figure><img src="../../../.gitbook/assets/image (29).png" alt=""><figcaption><p>Agent policy</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Screenshot 2024-08-09 at 13.32.25.png" alt=""><figcaption></figcaption></figure>

One of the pre-configured policy options is 'Feedback Encouragement'. If this option is selected in the agent configuration, it means that any feedback provided by the user will only be relevant within the thread that it is given. This feedback will not train the agent in their long-term responses, nor will it impact any other user's responses, agent responses, or thread responses.&#x20;

If the 'Feedback Encouragement' policy option is selected for an agent, it will increase the number of times the LLM asks 'how am I doing'.

Under the Policy tab you can also add **Additional Information**. This equips the agent with essential background or contextual information that influences its interactions with users. This could encompass guidelines on tone, references to external knowledge not contained within its training data, or directives on handling sensitive topics.

<figure><img src="../../../.gitbook/assets/summit10 2024-07-22 13-20-43.png" alt=""><figcaption></figcaption></figure>

**Capabilities**

Next, you can set up your agent **capabilities** under the '**capabilities**' heading. An agent capability is a specific set of steps that this agent is able to perform for the user. In order to find out more about capability configuration for your agents, please read our 'capabilities' article [here](how-to-configure-capabilities.md).&#x20;

<figure><img src="../../../.gitbook/assets/image (30).png" alt=""><figcaption><p>Capabilities</p></figcaption></figure>

**Tools**

In the next step of agent configuration, you'll choose the **tools** you want the agent to utilize when answering end-users questions, within the '**Tools**' tab.

Here, you have the option to decide if you want the agent to utilize the **clarification tool** and **prompt library**.&#x20;

Further details about these functionalities can be found [here](https://docs.mindset.ai/platform/features/agents/how-to-configure-agents).&#x20;

Lastly, you can choose additional response details that the agent will incorporate when answering user inquiries. This includes, including whether to display **segments**, **topics**, and **speakers** to the user.&#x20;

_**Please note:**_ You do not have to select all 3 of these features together for the same agent.&#x20;

<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

#### Design

Under the Design tab, the agent's primary color and text color can be configured.

To change the color simply click the 'select color' button and choose your color from the color wheel or from your designated color library.

<figure><img src="../../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

**Knowledge**&#x20;

Under the '**Knowledge**' tab, you can select the knowledge banks that the agent can have access to.&#x20;

_**Please note:**_ The agent can have access to the information from multiple knowledge banks. More than one knowledge bank can be selected here.&#x20;

Once the selected knowledge banks have been toggled on and saved, the agent will then be able to utilize all information from those associated banks when answering end-user questions.&#x20;

<figure><img src="../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

#### Bias

Under the **Bias** tab select **Bias Assessment** to see a summary of the Agent’s available Banks of Data. This provides information on the key themes and concepts of the bank's content.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-07-17 at 09.36.47.png" alt=""><figcaption></figcaption></figure>

The **Weighted** Concepts tab displays the concepts and the related segments, with the highest weighted concepts at the top and the lowest at the bottom.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-07-17 at 09.35.13.png" alt=""><figcaption></figcaption></figure>



**Testing**

Under the **Testing** tab, you can run tests and compare agent responses to understand end-users experiences. Further details on the agent testing framework can be found [here](https://docs.mindset.ai/platform/features/agents/agent-testing-framework).

**Preview**

Under the '**Preview**' tab, you can practice trialing out your agent to see how it responds to questions asked. We recommend you take your time testing your agent here prior to sharing it with your end-users, to ensure it is performing correctly.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-07-17 at 09.31.41.png" alt=""><figcaption></figcaption></figure>





**Access**&#x20;

The **Access** tab allows you to choose which of your accounts have access to the selected agent.&#x20;

The agent can either be configured with **open access** - where all application members are able to view and search published content, including users who are members of any account; or **restricted access**, where only members of selected accounts are able to view and search published content in the knowledge bank.&#x20;

<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

To restrict access to your agent to specific accounts, select the '**restricted access**' button and click save.&#x20;

Next, you can select from your list of accounts below, the ones you wish to have access to the selected agent. To do this, toggle on the button next to the account you wish to grant access to the agent, and click save.&#x20;

<figure><img src="../../../.gitbook/assets/summit10 2024-06-19 20-56-41.png" alt=""><figcaption></figcaption></figure>

You can additionally grant access to all of you accounts in one go by selecting the '**grant access to all**' button, or revoke access for all accounts in one go by selecting the '**revoke access for all**' button.

In order to find out more about access management, please refer to our article titled 'Agent entitlement and Knowledge banks'.



