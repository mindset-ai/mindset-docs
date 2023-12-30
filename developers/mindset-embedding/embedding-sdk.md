# Embedding SDK

## Installation

The Mindset Embed SDK is installed from the server hosting your Mindset application.&#x20;

```html
<head>
    <script src="http://YOUR-MINDSET-URL/mindset-sdk.js"></script>
</head>
```

### Basic Usage

1. You can place an HTML element (`div` , `span` , etc) anywhere on a page where you would like the Mindset Component to be embedded.
2. Set the ID of the HTML element and use a standard CSS class to define its width, height, and other properties.
3. Ensure that `mindset.init` is called before any other SDK function.&#x20;
4. Call `mindset.render` to render the Mindset Component in the HTML element provided

```html
<body>
<div id="my-div" class="my-div-class"></div>

<script>
        mindset.init({ appUid: 'APPUID', humanUid: '12345' });
        mindset.render({ elementId: 'my-div', view: 'home', showAppMenu: false });        
</script>
</body>
```

{% embed url="https://codepen.io/Barrie-Hadfield/pen/gOEpEVR" %}
Try this basic example
{% endembed %}

