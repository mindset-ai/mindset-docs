# Embed SDK

## Installation

The Mindset Embed SDK is installed from the server hosting your Mindset application.

```html
<head>
    <script src="https://YOUR-MINDSET-URL/mindset-sdk.js"></script>
</head>
```

## Usage

1. You can embed a Mindset Component into any HTML container (`div` , `span` , etc) anywhere on a page.
2. Set the ID of the HTML container and use a standard CSS class to define its width, height, and other properties.
3. Please make sure that `mindset.init` is called before any other SDK function.
4. Call `mindset.render` to render the Mindset Component in the HTML container provided by passing its ID and options used for the specific configuration of this instance of the Component.

```html
<body>
<div id="my-div" class="my-div-class"></div>

<script>
   //Ensure this code runs after the div has been inserted 
    mindset.init({ appUid: 'YOUR-APPUID', humanUid: '12345' });
    mindset.render({ containerId: 'my-div', component: 'test', options: {} });        
</script>
</body>
```

A complete HTML page would look like this:

{% code fullWidth="true" %}
```html
<!DOCTYPE html>
<html>

<!-- Ensure to change this to the server hosting the SDK -->
<script src="https://YOUR-MINDSET-URL/mindset-sdk.js"></script>

<head>
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
    <h1>Mindset embedded SDK example</h1>

    <div id="check-sdk-div"></div>
    <hr>
    <div id="copilot-div" class="copilot-div-class"></div>

    <script>
    mindset.init({ appUid: 'YOUR-APPUID', authToken:'AUTH-TOKEN-FOR-CURRENT-USER' });
    mindset.render({ containerId: 'check-sdk-div', component: 'checkSdk', options: {} });
    mindset.render({ containerId: 'copilot-div', component: 'coPilot', options: {} });
    </script>    
</body>

</html>
```
{% endcode %}

## Authentication

Users need to be authenticated in the Mindset system to use Mindset functionality.

You can generate the `AUTH-TOKEN-FOR-CURRENT-USER` needed by calling the following API:

```html
POST to https://YOUR-MINDSET-URL/authenticate-embedded-user

with body:

{ "appUid": "YOUR-APPUID",
  "apiKey": "YOUR-API-KEY", 
  "userEmail": "USER-EMAIL-ADDRESS"
}
```

If a user with that email address exists in your application then an authentication token will be generated for them.

If such a user does not exist, one will first be created.

`YOUR-API-KEY` can be retrieved from your app admin UI.

**Keep your API key secure** As it can be used to create a valid session for any user to access your content, you should make sure you know who it is being used for.

## Components

### checkSdk

**Purpose:** Tests to see if the SDK is working. Rendered a confirmation message if all is well. This component is not needed for any other purpose, but is useful when installing the SDK to be assured it is working as expected.

**Usage:** `component: 'checkSdk', options: {}`

**Options:** none

**Example:**

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

***

### coPilot

**Purpose:** Render a Mindset CoPilot into the specified HTML container.

**Usage:** `component: 'coPilot', options: {heading: 'My CoPilot'}`

**Options:**

<table><thead><tr><th width="130">Option</th><th width="103">Type</th><th width="136">Deafult</th><th>Purpose</th></tr></thead><tbody><tr><td>heading</td><td>String</td><td>'heading'</td><td>Specifies the heading of the CoPilot Component.</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr></tbody></table>

**Example:**

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Note</p></figcaption></figure>

**Notes:**

* All of the configuration of the CoPilot is handled within the Mindset Platform. Please see the [Knowledge Graph](../../platform/features/knowledge-graph-workflow/) section of the Platform documentation.
* All content & analytics is handled by the Mindset platform itself.

***
