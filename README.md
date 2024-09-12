# Dynamic tab Title Change Shopify
Script to dynamically change the tab title when the user switches away from your site, drawing attention back to it with the alternating messages.

![](https://github.com/thewakar22/dynamic-tab-title-change-shopify/blob/main/screen-capture.gif)

# Shopify Theme Script Implementation
This repository provides a step-by-step guide to implement a script that changes the document title based on the visibility of the page in a Shopify theme.

## Implementing the Code in Shopify
1. **Access Your Shopify Admin**:
   - Log in to your Shopify admin panel.

2. **Edit the Theme**:
   - Go to **Online Store** > **Themes**.
   - Click on **Actions** > **Edit Code**.
   - Open the `theme.liquid` file.
   - Paste the script right above the `</head>` tag.
   - Save the changes.
   - Dont forget to change **$\color{Orange}{\Huge{\textsf{New Message 1}}}$, $\color{Orange}{\textsf{New Message 2}}$** as of your liking.

## Code Snippet
```
<script>
     let originalTitle = document.title;
     let interval;
     document.addEventListener('visibilitychange', function() {
         if (document.hidden) {
             
             let messages = ["New Message 1", "New Message 2"];
             let messageIndex = 0;
             interval = setInterval(function() {
                 document.title = messages[messageIndex];
                 messageIndex = (messageIndex + 1) % messages.length;
             }, 1000); 
         } else { 
             clearInterval(interval);
             document.title = originalTitle;
         }
     });
</script>
```

## Resources
I have created a GitHub repository to help people implement dynamic Shopify titles. This implementation is based on the code provided by Hey Tony Agency. Feel free to check it out and contribute!

- **Post Link:** [Dynamic Shopify Title Implementation](https://www.instagram.com/reel/C_xyxdQuu88/)
- **Instagram Profile:** [Matt Diamante / Hey Tony](https://www.instagram.com/heytony.agency/)
