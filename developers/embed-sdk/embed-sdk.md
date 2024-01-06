# Embed SDK

## Installation

#### **Overview:**

The Mindset Embed SDK is integrated directly into your web application by including a script reference in the HTML document. This script is hosted on the server where your Mindset application resides.

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
        .copilot-div-class {
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
    <div id="copilot-div" class="copilot-div-class"></div>

    <script>
    mindset.init({ appUid: "YOUR-APPUID", authToken:"AUTH-TOKEN-FOR-CURRENT-USER" });
    mindset.render({ containerId: "check-sdk-div", component: "checkSdk", options: {} });
    mindset.render({ containerId: "copilot-div", component: "coPilot", options: {} });
    </script>    
</body>
</html>
```

In this example, two Mindset components (`checkSdk` and `coPilot`) are embedded within designated containers on the page. The `mindset.init` function is called first to initialise the SDK, followed by `mindset.render` calls for each component.

***

## Authentication

**Overview:**

The Mindset SDK employs an authentication mechanism that uses an authentication token. This token is pivotal in linking the client-side session to a user account within the Mindset platform. The process ensures a seamless integration of user sessions with the platform's functionalities.

The authentication approach is two-fold:

1. **Existing User Linkage**: If the user already exists in the Mindset platform, the authentication process will generate a token that links the current client-side session to this existing user account. This facilitates a continuous and integrated experience for returning users.
2. **Automatic User Creation**: In cases where a user does not exist on the platform, the authentication process automatically triggers the creation of a new user account based on the provided email address. A corresponding authentication token is generated, linking the new user account to the client-side session. This streamlined process ensures new users are smoothly onboarded without additional manual steps.

The authentication token is a critical component in this process, serving as the key to accessing and interacting with the SDK's features while maintaining user-specific contexts and preferences.

**Authentication Token Generation:**

A secure server-side HTTP POST request is made to the Mindset authentication endpoint to generate the `AUTH-TOKEN-FOR-CURRENT-USER`. This process involves sending user identification details (such as email address) and your application credentials.

```
POST https://YOUR-MINDSET-URL/authenticate-embedded-user
```

#### **Request Body:**

The body of the request should include:

* `appUid` (String): Your application's unique identifier.
* `apiKey` (String): Your application's API key, retrievable from your app's admin UI.
* `userEmail` (String): The email address of the user to authenticate.

#### Example JSON body:

```json
{
  "appUid": "YOUR-APPUID",
  "apiKey": "YOUR-API-KEY",
  "userEmail": "USER-EMAIL-ADDRESS"
}
```

#### **Server-Side Authentication:**

* **Critical**: The authentication process must be handled server-side. This is to ensure the security of your API key and the overall integrity of the user authentication process.
* Upon successful authentication, the API returns an authentication token. This token is then used in subsequent SDK function calls to authenticate the user.

#### **User Account Handling:**

* An authentication token will be generated if a user with the provided email address exists in your application.
* If no such user exists, a new user account will be created using the provided email address, and an authentication token will be generated.

#### **Security Considerations:**

* **API Key Confidentiality**: Keep your API key confidential. It should be securely stored and never exposed in client-side code.
* **Authentication Tokens**: Handle authentication tokens securely. They should be transmitted and stored using secure methods to prevent unauthorised access.

#### **Example Server-Side Usage:**

```javascript
// Example Node.js code to make a server-side HTTP POST request for user authentication
// Adapt this example based on your server-side programming environment

const fetch = require('node-fetch');

const requestBody = {
  appUid: "YOUR-APPUID",
  apiKey: "YOUR-API-KEY",
  userEmail: "user@example.com"
};

fetch('https://YOUR-MINDSET-URL/authenticate-embedded-user', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(requestBody)
})
.then(response => response.json())
.then(data => {
  console.log('Authentication Token:', data.authToken);
})
.catch((error) => {
  console.error('Error:', error);
});

```

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
* `authToken` (String): The authentication token for the current user. This token is used to manage user sessions and access control. Ensure that the token is valid and correctly configured for the user's session. See the [Authentication](embed-sdk.md#authentication) section above for details on generating an authentication token.

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
* `options` (Object): An optional configuration object containing settings specific to the rendered component. These settings can vary depending on the component. An empty object `{}` must be passed if no options are needed.

#### Behavior:

* **Component Rendering**: Upon invocation, `mindset.render()` targets the HTML element specified by `containerId` and renders the requested component within it.
* **Options Handling**: The function utilises the `options` object to customise the component's behaviour and appearance. These options should be tailored to the specific requirements of the component.
* **Error Handling**: If an invalid `containerId` is provided or if the specified `component` does not exist, the function will throw errors or fail to render the component. Ensure that the parameters are correctly set.
* **Idempotency**: Calling `mindset.render()` multiple times with the same `containerId` will typically replace the container's content with the new component render. The exact behaviour may depend on the component's internal implementation.

***

## Components

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

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

***

### `coPilot`

#### **Purpose:**&#x20;

The `coPilot` component is designed to render an interactive Mindset CoPilot interface within a specified HTML container. It integrates seamlessly with the Mindset platform to provide dynamic, user-interactive content.

#### **Usage:**

```javascript
mindset.render({
  containerId: "container-id",
  component: "coPilot",
  options: { heading: "Your CoPilot Heading" }
});
```

#### **Options:**

* `heading` (String): Specifies the heading or title for the CoPilot interface.

#### **Notes:**

* All configurations for the `coPilot` component, including content and analytics, are managed through the Mindset Platform. Refer to the [Knowledge Graph](../../platform/features/knowledge-graph-workflow/) section in the Platform documentation for detailed configuration guidelines.
* Use CSS to style the HTML container hosting the component and configure the behaviour, look and feel of the CoPilot within the Mindset Platform Admin interface.

#### **Example output:**

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Note</p></figcaption></figure>



***
