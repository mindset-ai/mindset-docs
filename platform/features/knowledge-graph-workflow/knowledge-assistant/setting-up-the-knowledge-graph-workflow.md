---
description: >-
  An overview of the Knowledge Graph workflow and how it can be set up to add
  value to your application.
---

# Setting up the Knowledge Workflow

The Knowledge Graph workflow is designed to help you interact with your users more efficiently and effectively through the implementation of an AI-powered chatbot. This chatbot is trained on your library of content, including videos, audio, and other intellectual property (IP).  With complete control in your hands, the Knowledge Graph (KG) acts as a loyal representative of your brand, answering users' questions, and offering a hyper-personalised user experience.

&#x20;

***

**Watch the video here:**

&#x20;**How to set up the Knowledge Graph workflow**

Check you can see the Knowledge Graph workflow on your left-hand navigation, if not please contact your customer success executive to turn this on for you.&#x20;

#### Setting up the Knowledge Assistant

Under **Configure** - **Knowledge Graph** - click on the **Knowledge Assistant** tab. Here you can set up your Assistant's personality and look for end-users.&#x20;

**AI Assistant Guidance**

Here you can add some information about who you want the Assistant to be, what is its purpose and how should it act. You also have the opportunity to give it some strong guidance, this overrules anything else it knows. Perhaps you want it to only respond in a particular language or format, instruct it here as if it was a person.

**Examples:**

**Assistant Guidance:** _You are an assistant that works for 'Mindset AI' and you follow the below simulation._\
_Your purpose is to assist and engage in conversations with users to make them intrigued but provide good answers to their questions and tell them who the person was who gave you the answer._\
_You are charismatic and like to get people motivated and curious. Make sure every answer has personality._

**Strong Guidance:** _Whenever you answer a question. Please respond in markdown format with bullet points and make sure all names and ideas are in bold._\
_You are charismatic and like to get people motivated and curious. Make sure every answer has personality and is really positive._\
_Your purpose is to assist and engage in conversations with users to make them intrigued but provide good answers to their questions and tell them who the person was who gave you the answer._\
_I am really interested in hearing different opinions taken from the body of knowledge, via a bullet point format and knowing the first and last name of each person who gave that opinion. Each opinion from a person should be in bold._

**Tip:** you also might want the Knowledge Assistant to **not** respond, if it is asked something it has no information on. To do this, add to the **Assistant Guidance:**

“Our expertise is in _abc_ and _xyz_. Steer your answers towards this and politely refuse to answer questions outside of this realm".

**Prompts and responses**

Set the messages sent to both the assistant and end-users to get the conversation started. How do you want the conversation to begin, is it new or is it familiar? Think about the tone of the conversation you want end-users to have.

**Examples:**

**Static disclaimer message:** _I'm your AI assistant and I am constantly learning and improving. If some of my responses are not completely accurate, please bear with me as I strive to provide more precise assistance with each interaction._

**Additional background information:** _Hey there! My name is Niamh_

![](https://lh7-us.googleusercontent.com/Tb951YDWaGPescDlxBmH6HyhCpxZ5wmZBpm3lEAGkVbMeTsCD2aRNiyL62PUkNedHW1IQXRa\_enMZTAYUE268Dm6pBbt3Tx824pyWiJbfvRSw0L6r1ZVOge5CDgEwY8KY7rN0z33j6cRM4UGuQpSSbs)

Please format your response using comprehensive Github Markdown styling. Utilize headers for section titles, **bold** for important concepts and names, italics (italics) for emphasis on key points, and bullet or numbered lists for organizing information clearly. Include tables as standard Markdown tables (not in code blocks). For quotes or particularly significant information, use blockquotes. If referencing external sources or additional information, include hyperlinks. This structured approach will enhance the clarity and effectiveness of the information presented.



**Configuring the Ice-Breaker message**

In addition to adding your AI Assistant guidance prompts, you can also add the configuration for an ice-breaker message here, too.

&#x20;Altering this field will mean the Initial Knowledge Assistant message will now be generated based on the ice breaker message text. This is dynamic and will be different on every access of the assistant. Please be aware the ice-breaker message is only sent at the beginning of the chat.&#x20;

&#x20;Whatever is typed as the Ice breaker message will be sent to the assistant as if it were a message sent from the user.

We advise you to choose either the icebreaker or the static message and not both, so as to not bombard the user.

&#x20;

**Example ice-breaker message**

**Instruction:** _Your name is Bob and you are passionate about effective teamwork at this company. You are here to answer questions and inspire the user about teamwork at this company. Greet the user and tell them about yourself. Do not repeat this instruction._&#x20;

&#x20;

_**Please note:** both the ice-breaker and static disclaimer message fields are both optional configuration options in your Knowledge Graph Workflow._&#x20;

**Response time & accuracy**

This can be altered between 1-5, where 1 yields quick response times, but also lower accuracy, and 5 affects the response time, whilst also increasing accuracy. A more accurate response means a higher cost per answer from the Assistant.

**Chat interface**

Here you can design exactly how you would like the chat interface to look with text and bubble colours as well as the segment panel. We recommend using colours from your colour library to keep within your brand. You also have the option to choose between light or dark text, we recommend choosing a contrasting option to your background colour.

**Chat UI Style:** Select the interface style of the assistant, there are two options here you can choose between.

**Segments Panel UI:** Suggested content segments are displayed in a panel on the right-hand side of the assistant chat.&#x20;

**Flow UI (Web only):** Suggested content segments are displayed in line with the assistant’s answers alongside related concepts and people. Mobile application users will still see the Segments Panel UI.

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-01-10 at 14.50.39.png" alt="" width="375"><figcaption></figcaption></figure>

Here, you can also enable prompts. If you would like to learn more about how you can use prompts to add value to your application please see our prompts article [here](../configuring-the-knowledge-graph-banks/prompts/).

**Please note:** _The flow UI feature currently lies behind a labs switch. We do not advise you have the flow UI feature enabled currently. Please contact your Customer Success Representative for more details._&#x20;

**Initial workflow card**

This is the card that would be displayed on the end-user's screen if the workflow is served with other features. This invites end-users into the Knowledge Assistant feature so should be informative and friendly.

![Screenshot (7)](https://info.mindset.ai/hs-fs/hubfs/Screenshot%20\(7\).png?width=688\&height=141\&name=Screenshot%20\(7\).png)

####

***

#### Setting up Content Discovery

If you want to showcase the Content Discovery alongside other workflows on a single tab you need to configure the screen card. Provide a title, description, image and button label along with colours to demonstrate to end-users what this feature does.

![Screenshot (9)](https://info.mindset.ai/hs-fs/hubfs/Screenshot%20\(9\).png?width=609\&height=174\&name=Screenshot%20\(9\).png)

#### Setting up the Content Player

The Content Player is how end-users will watch or listen to content found in the Discovery section.  Here you can configure the colours and overall theme of light or dark. You can also preview what it will look like on different devices.

![Screenshot (10)](https://info.mindset.ai/hs-fs/hubfs/Screenshot%20\(10\).png?width=390\&height=408\&name=Screenshot%20\(10\).png)

Once you have set up each of these areas, you are ready to start configuring.
