# iFrame Embedding

## **Overview:**

The Mindset application also supports embedding via an iFrame, allowing seamless integration of the entire Mindset platform within your web application. This approach is ideal for incorporating the full functionality of Mindset into websites and web-based platforms, providing users with a comprehensive experience without navigating away from your site.

### **Embedding Process:**

1. **Creating the iFrame**: To embed the Mindset application, create an iFrame element in your HTML with the `src` attribute set to the Mindset application URL.
2. **iFrame Attributes**:
   * `src`: The URL of the Mindset application.
   * `width` and `height`: Dimensions of the iFrame. These can be set in pixels or as a percentage of the container's size.
   * `frameborder`: Set this to `0` for a borderless iFrame.
   * Additional attributes such as `allowfullscreen`, `allowtransparency`, and `scrolling` can be adjusted based on your requirements.
3. **Styling the iFrame**: Use CSS to style the iFrame and its container for a seamless integration with your website’s layout and design.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Mindset Application iFrame Embed</title>
    <style>
        .mindset-iframe-container {
            width: 100%;
            height: 600px; /* Adjust as needed */
            border: none;
            overflow: hidden;
        }
    </style>
</head>
<body>
    <h1>Integrated Mindset Application</h1>

    <div class="mindset-iframe-container">
        <iframe src="https://YOUR-MINDSET-URL" 
                width="100%" 
                height="100%" 
                frameborder="0" 
                allowfullscreen>
        </iframe>
    </div>
</body>
</html>
```

In this example:

* An iFrame is used to embed the Mindset application within a `div` container.
* The `src` attribute of the iFrame points to the Mindset application URL.
* CSS styles are applied to ensure that the iFrame fits well within the layout of the page.

**Security and Permissions:**

* When the whole Mindset application is embedded, login and user creation is handled by the embedded application itself.&#x20;
