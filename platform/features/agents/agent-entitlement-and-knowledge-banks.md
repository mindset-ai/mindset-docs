# Agent entitlement and Knowledge banks

{% hint style="info" %}
If you have the Knowledge assistant workflow enabled and available to users, entitlement to knowledge banks is provided through Agents and through the knowledge banks themselves.&#x20;

Remove the knowledge assistant workflow from the Design > Navigation and Layout tab to simplify the entitlement process.

For more information on Migrating from Assistants to Agents, see the link below.

[knowledge-bank-entitlement.md](../knowledge-graph-workflow/configuring-the-knowledge-graph-banks/knowledge-bank-entitlement.md "mention")
{% endhint %}

A users access to content within a knowledge bank is managed through their entitlement to use agents. Agents can be set to "Open access" where all application users will have access to the agent and any knowledge banks the agent has access to, or can be set to "Restricted access" where only specific accounts and their members can access the agent and related content. Access to knowledge banks through the agents also controls what content users will see in the Content Discovery function of the knowledge workflow if enabled.

## Managing Agent Knowledge

Each agent in your application only has access to the knowledge banks you define. When configuring an agent, select the "Knowledge banks" tab and enable the required knowledge banks. The content that should be made available to an agent should be based on: the problem or task the agent is deisnged to solve, and the nature of the content.

#### Open Access Agents

Agents that are set to open access and the knowledge banks they are assigned are available to all users of the application. These agents should never have access to premium content, account specific, or customer specific content. They must have acces to at least one knowledge bank and should have access to enough content to be able to perform their required task.

#### Restricted Access Agents

Agents that are set to restricted access and the knowledge banks they are assisgned are only available to the users of specified accounts. The knowledge banks they have available could include the same content as open agents, but contain richer configuration or more capabilities and could also have access to premium or customer specifc knowledge banks.

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption><p>Entitlement to Agents and Knowledge banks</p></figcaption></figure>

In the example above, the user depicted can access all three agents and will be able to find content from all five knowledge banks in the content discovery feature if enabled.

If the user was only a member of Account A, they would not be able to access Agent III or content from Knowledge Bank 5. Note that responses from Agent I will only be drawn from Knowledge Banks 1 and 2, even though the user is entitled to Knowledge banks 3 and 4 through Agent II
