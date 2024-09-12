# Dynamic tab Title Change Shopify
Script to dynamically change the tab title when the user switches away from your site, drawing attention back to it with the alternating messages.
# Shopify Theme Script Implementation

## Introduction
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

## Code Snippet
    ```javascript
     // Store the original title
     let originalTitle = document.title;
     let interval;

     // Listen for visibility changes
     document.addEventListener('visibilitychange', function() {
         if (document.hidden) {
             // Define the messages to alternate between
             let messages = ["New Message 1", "New Message 2"];
             let messageIndex = 0;

             // Start an interval to alternate between messages
             interval = setInterval(function() {
                 document.title = messages[messageIndex];
                 messageIndex = (messageIndex + 1) % messages.length;
             }, 1000); // Change title every second
         } else {
             // Clear the interval and restore the original title
             clearInterval(interval);
             document.title = originalTitle;
         }
     });
      ```

## Conclusion
Your GitHub repository is now set up, and the code is implemented in your Shopify theme. If you need any further assistance, feel free to ask!
