# Dynamic tab Title Change Shopify
Script to dynamically change the tab title when the user switches away from your site, drawing attention back to it with the alternating messages.

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

## Code Snippet

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

## Resources

### Dynamic Shopify Title Implementation

I have created a GitHub repository to help people implement dynamic Shopify titles. This implementation is based on the code provided by Hey Tony Agency. Feel free to check it out and contribute!

- **Repository Link:** Dynamic Shopify Title Implementation https://www.instagram.com/reel/C_xyxdQuu88/
- **Instagram Source:** Matt Diamante https://www.instagram.com/heytony.agency/
