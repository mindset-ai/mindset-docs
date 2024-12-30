---
description: Learn about the Tools available within the Agent feature.
---

# Tools

The Tools area allows you to further configure the Agent using different methods.



Here, you have the option to decide if you want the agent to utilize the **clarification tool, prompt library,** and **additional accuracy checking.**&#x20;

_**Please note:**_ The clarification tool, prompt library, and additional accuracy checking are all optional features that can be enabled individually or in combination with one another.

Lastly, you can choose additional response details that the agent will incorporate when answering user inquiries. This includes, including whether to display **segments**, **topics**, and **speakers** to the user.&#x20;

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-08-15 at 14.49.58.png" alt=""><figcaption></figcaption></figure>

**Sources and topics UI style:**&#x20;

This is where administrators can select how the content used in agent's responses and related topics are displayed to users in the agent interface. This can either be displayed as pills below the agent's response, or display as panels above and below the agent's responses.

Segments, topics, and speakers can be displayed in agent responses by toggling the 'display segments', 'display topics' and 'display speakers' switches on. The names of each of these can also be altered via the text box below the toggles. **Please note:** there is a character limit of 15 for these headings.

#### Segment Recommendation & Accuracy Controls&#x20;

Accuracy and relevance are something Mindset is constantly focused on improving. These new controls solve a few important challenges users were facing with getting the right level of detail and relevance in agent responses.

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-08-28 at 16.58.05.png" alt=""><figcaption></figcaption></figure>

#### **Configuring your Advanced Configuration:**&#x20;

These controls can be found in the 'tools' tab of your agent configuration.&#x20;

**Number of Segments**: This setting lets you adjust how many pieces of information (segments) your agent considers when formulating an answer. The default is 5 segments.

For agent use cases where a user just needs a quick, focused response, you can lower this number to 2 or 3 segments. But in other use cases where discovery and in-depth responses are needed, you can increase this number to 7-8 segments, so the agent will use more information and recommend more content.&#x20;

Just keep in mind that using a lot of segments can make responses longer and potentially increase the response time since the AI has to process more information.

&#x20;

**Relevance Threshold**: Think of this as a "quality filter" for the segments. It's a score from 0 to 1 that rates how well each segment matches what the user asked.

Setting a higher threshold of 0.8 or 0.9 means your agent will only use the most directly relevant segments in its response. Great for technical responses where you need pinpoint accuracy.

Lowering the threshold to 0.5 or 0.6 allows your agent to bring in segments that are more loosely related, but could provide helpful context or spark creative ideas for more open-ended conversations.

&#x20;

The key is adjusting these two controls in tandem based on the specific agent use case, and then using the different testing tools we provide in the agent administration portal.&#x20;

For specific, technical or compliance-driven use cases, use less high-relevance segments. For exploratory agent use cases, allow more segments with a lower relevance threshold.

We recommend experimenting to see what levels of detail and relevance work best for your typical use cases. These changes can be adjusted as required.

The 'Inject Source URL' toggle can also be enabled in the agent's configuration. When this toggle is activated, agents will create direct links to external articles after ingesting content from a website.&#x20;

For segments extracted from web pages, the link will direct to the original URL of the web page from which the content was sourced.

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-10-03 at 17.47.47.png" alt=""><figcaption></figcaption></figure>
