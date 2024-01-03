# Embed SDK

## Installation

The Mindset Embed SDK is installed from the server hosting your Mindset application.&#x20;

```html
<head>
    <script src="https://YOUR-MINDSET-URL/mindset-sdk.js"></script>
</head>
```

### Basic Usage

1. You can place an HTML container (`div` , `span` , etc) anywhere on a page where you would like the Mindset Component to be embedded.
2. Set the ID of the HTML container and use a standard CSS class to define its width, height, and other properties.
3. Ensure that `mindset.init` is called before any other SDK function.&#x20;
4. Call `mindset.render` to render the Mindset Component in the HTML container provided

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

{% embed url="https://codepen.io/Barrie-Hadfield/pen/gOEpEVR" fullWidth="true" %}
Try this basic example
{% endembed %}

A simple HTML page would look like this:

{% code fullWidth="true" %}
```html
<!DOCTYPE html>
<html>

<!-- Ensure to change this to the server hosting the SDK -->
<script src="http://YOUR-MINDSET-URL/mindset-sdk.js"></script>

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
    mindset.init({ appUid: 'YOUR-APPUID', humanUid: '12345' });
    mindset.render({ containerId: 'check-sdk-div', component: 'checkSdk', options: {} });
    mindset.render({ containerId: 'copilot-div', component: 'copilot', options: {} });
    </script>    
</body>

</html>
```
{% endcode %}

## Components

### checkSdk

**Purpose:** Tests to see if the SDK is working. Rendered a confirmation message if all is well. This component is not needed for any other purpose, but is useful when installing the SDK to be assured it is working as expected.

**Usage:** `component: 'checkSdk', options: {}`

**Options:** none

**Example:**

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

### copilot

**Purpose:** Render a Mindset CoPilot into the specified HTML container.

**Usage:** `component: 'copilot', options: {...}`

**Options:**&#x20;

<table><thead><tr><th width="130">Option</th><th width="103">Type</th><th>Purpose</th><th>Default value</th></tr></thead><tbody><tr><td>heading</td><td>String</td><td>Specifies the heading of the CoPilot Component.</td><td>"CoPilot"</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr></tbody></table>

**Example:**

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

