# Embed SDK

## Installation

#### **Overview:**

The Mindset Embed SDK is integrated directly into your web application by including a script reference in the HTML document. This script is hosted on the server where your Mindset application resides.

<figure><img src="../../.gitbook/assets/mindset-sdk-embed.png
" alt=""><figcaption><p>Mindset embed flow</p></figcaption></figure>

#### **Adding the SDK Script:**

To install the Mindset Embed SDK, include the following `<script>` tag in the `<head>` section of your HTML document:

```html
<head>
    <!-- Replace 'YOUR-MINDSET-URL' with the actual URL where your Mindset SDK is hosted -->
    <script src="https://YOUR-MINDSET-URL/mindset-sdk.js"></script>
</head>
```

This script tag imports the Mindset SDK, making its functionalities available within your web application.

## Usage

**Overview:**

The Mindset SDK allows you to embed interactive components within any HTML container element (such as `<div>`, `<span>`, etc.) on a webpage. These components are configurable and can be customised based on the specific needs of your application.

#### **Setup and Rendering:**

1. **HTML Container Setup**: Define an HTML container with a unique ID where the Mindset component will be rendered. Use standard CSS to style the container, setting properties like width, height, etc.

```html
<div id="my-div" class="my-div-class"></div>
```

2. **Initialisation**: Ensure that `mindset.init` is called before any other SDK function. This initialises the SDK with the necessary configuration parameters.

```javascript
mindset.init({
  appUid: "YOUR-APPUID", 
  authToken: "AUTH-TOKEN-FOR-CURRENT-USER"
});
```

3. **Component Rendering**: Use `mindset.render` to embed the desired Mindset component within the specified container. Pass the container ID and any options required for configuring the component.

```javascript
mindset.render({ 
  containerId: "my-div", 
  component: "checkSdk", 
  options: {} 
});
```

**Complete HTML Page Example:**

A complete HTML page integrating the Mindset SDK might look like this:

```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://YOUR-MINDSET-URL/mindset-sdk.js"></script>
    <style>
        .agent-div-class {
            height: 500px;
            width: 70%;
            margin-left: auto;
            margin-right: auto;
            overflow: auto;
            border-radius: 16px;
        }
    </style>
</head>

<body>
    <h1>Mindset Embedded SDK Example</h1>

    <div id="check-sdk-div"></div>
    <hr>
    <div id="agent-div" class="agent-div-class"></div>

    <script>
    mindset.init({ appUid: "YOUR-APPUID", authToken:"AUTH-TOKEN-FOR-CURRENT-USER" });
    mindset.render({ containerId: "check-sdk-div", component: "checkSdk", options: {} });
    mindset.render({ containerId: "agent-div", component: "agent", options: {"agentUid":"UID-OF-YOUR-AGENT"} });
    </script>    
</body>
</html>
```

In this example, two Mindset components (`checkSdk` and `coPilot`) are embedded within designated containers on the page. The `mindset.init` function is called first to initialise the SDK, followed by `mindset.render` calls for each component.

***

## Functions

### `mindset.init`

Initialises the Mindset SDK with necessary configuration parameters. This function must be called before invoking any other functions in the SDK. `mindset.init()` primarily sets up internal variables and returns immediately without waiting for any asynchronous operations.

```javascript
mindset.init({ 
    appUid: "YOUR-APPUID", 
    authToken:"AUTH-TOKEN-FOR-CURRENT-USER" 
});
```

#### Parameters:

* `appUid` (String): The unique identifier for your application. This is required to link the SDK to your specific application instance.
* `authToken` (String): The authentication token for the current user. This token is used to manage user sessions and access control. Ensure that the token is valid and correctly configured for the user's session. See the [Authentication](authentication.md) section for details on generating an authentication token.

#### Behavior:

* **Precedence**: `mindset.init()` should be the first function called upon starting your application. This ensures that all SDK functionalities are correctly configured and can operate based on the provided settings.
* **Idempotency**: If `mindset.init()` is called multiple times, the next API call will use the latest parameters supplied. There should be no reason to call this function multiple times, but provided the same parameters are supplied, there should be no negative effect.
* **Error Handling**: In case of invalid or missing parameters, the function may throw errors or warnings. Ensure that valid `appUid` and `authToken` are provided.
* **Asynchronous Consideration**: The function returns immediately and does not wait for any network or asynchronous operations to complete.

### `mindset.render`

The `mindset.render()` function is responsible for rendering a specified component within a designated container on the web page. It is a key function of the Mindset SDK used to display SDK components dynamically.

Multiple Mindset components can be rendered on the same page, and they will maintain state change between each other automatically.&#x20;

```javascript
mindset.render({
  containerId: "CONTAINER-ID",
  component: "MINDSET-COMPONENT",
  options: {}
});
```

#### Parameters:

* `containerId` (String): The ID of the HTML container (usually a `div` element) where the component will be rendered. This ID should correspond to an existing element in your HTML.
* `component` (String): The name of the component to be rendered. This name should match one of the predefined components in the Mindset SDK. See the [Components](embed-sdk.md#components) section below for all exposed components and their options.
* `options` (Object): A mandatory configuration object containing settings specific to the rendered component. These settings can vary depending on the component. An empty object `{}` must be passed if no options are needed.
  * If rendering an agent then the uid of the agent must be passed in the options as `agentUid`

#### Behavior:

* **Component Rendering**: Upon invocation, `mindset.render()` targets the HTML element specified by `containerId` and renders the requested component within it.
* **Options Handling**: The function utilises the `options` object to customise the component's behaviour and appearance. These options should be tailored to the specific requirements of the component.
* **Error Handling**: If an invalid `containerId` is provided or if the specified `component` does not exist, the function will throw errors or fail to render the component. Ensure that the parameters are correctly set.
* **Idempotency**: Calling `mindset.render()` multiple times with the same `containerId` will typically replace the container's content with the new component render. The exact behaviour may depend on the component's internal implementation.

***
