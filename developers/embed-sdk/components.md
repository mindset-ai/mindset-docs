---
description: >-
  This page details the exposed Mindset components. If a component you would
  like to use is not referenced here, please speak to support to have it added.
---

# Components

### `checkSdk`

#### **Purpose:**&#x20;

The `checkSdk` component serves as a diagnostic tool to verify the successful integration and operation of the Mindset SDK. It displays a confirmation message, confirming that the SDK is working correctly. This component is particularly useful during the SDK's initial installation and setup process.

#### **Usage:**&#x20;

```javascript
mindset.render({
  containerId: "container-id",
  component: "checkSdk",
  options: {}
});
```

#### **Options:**&#x20;

* None. The `checkSdk` component does not require any additional options. Pass an empty `{}`.

#### **Example output:**

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Example of a checkSdk component</p></figcaption></figure>

***

### `agent`

#### **Purpose:**&#x20;

The `agent` component is designed to render an interactive Mindset Agent interface within a specified HTML container. It integrates seamlessly with the Mindset platform to provide dynamic, user-interactive content.

#### **Usage:**

```javascript
mindset.render({
  containerId: "container-id",
  component: "agent",
  options: { agentUid: "YOUR AGENT UID" }
});
```

#### **Options:**

* `agentUid` (String): This is the UID obtained from your management console under the API section on the Agents tab.

#### **Notes:**

* All configurations for the `agent` component, including content and analytics, are managed through the Mindset Platform. Refer to the [Agent](../../platform/features/agents/) section in the Platform documentation for detailed configuration guidelines.
* Use CSS to style the HTML container hosting the component and configure the behaviour, look and feel of the CoPilot within the Mindset Platform Admin interface.

#### **Example output:**

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>
