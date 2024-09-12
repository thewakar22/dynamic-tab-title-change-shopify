# Dynamic tab Title Change Shopify
Script to dynamically change the tab title when the user switches away from your site, drawing attention back to it with the alternating messages.
# Shopify Theme Script Implementation

## Introduction
This repository provides a step-by-step guide to implement a script that changes the document title based on the visibility of the page in a Shopify theme.

## Table of Contents
- Introduction
- Creating a GitHub Repository
- Adding Your Code
- Pushing Changes to GitHub
- Implementing the Code in Shopify

## Creating a GitHub Repository
1. **Log in to GitHub**: Go to GitHub and log in to your account.
2. **Create a New Repository**:
   - Click on your profile icon and select **Repositories**.
   - Click the **New** button.
   - Enter a repository name, description, and choose the visibility (public or private).
   - Initialize the repository with a README file.

## Adding Your Code
1. **Clone the Repository**:
   - Open your terminal or Git Bash.
   - Clone the repository to your local machine using:
     ```bash
     git clone https://github.com/your-username/your-repository-name.git
     ```
2. **Add Your Code**:
   - Navigate to the cloned repository folder.
   - Create a new file named `theme.liquid` and add your code snippet:
     ```html
     <script>
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
     </script>
     ```

## Pushing Changes to GitHub
1. **Commit and Push**:
   - Add the changes:
     ```bash
     git add .
     ```
   - Commit the changes:
     ```bash
     git commit -m "Added script to change document title on visibility change"
     ```
   - Push the changes to GitHub:
     ```bash
     git push origin main
     ```

## Implementing the Code in Shopify
1. **Access Your Shopify Admin**:
   - Log in to your Shopify admin panel.
2. **Edit the Theme**:
   - Go to **Online Store** > **Themes**.
   - Click on **Actions** > **Edit Code**.
   - Open the `theme.liquid` file.
   - Paste the script right above the `</head>` tag.
   - Save the changes.

## Conclusion
Your GitHub repository is now set up, and the code is implemented in your Shopify theme. If you need any further assistance, feel free to ask!
