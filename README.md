# WhatsApp-Driven Google Drive Assistant

## Overview
Hey there! This project is my attempt at building a cool WhatsApp-driven tool using n8n Cloud to manage Google Drive files. The idea is to control file operations like listing, deleting, and moving files right from WhatsApp messages. I created this as part of an internship task  to show off my skills in automation and problem-solving.

## Tasks Completed
- *Task 1: Court-Data Fetcher & Mini-Dashboard*
  - I couldn’t get to this one due to time limits and decided to focus all my energy on Task 2 instead. It was about fetching court data and making a dashboard, but I’ll save that for another day!
- *Task 2: WhatsApp-Driven Google Drive Assistant*
  - Here’s what I managed to do:
    - UPLOAD : Uploads the files to Google Drive.
    - LIST : Shows all files in the Google Drive folder.
    - DELETE : Removes a specific file.
    - MOVE : Moves a file to a new folder.
    - SUMMARY /ProjectX: I tried to add a feature to summarize file contents, but it’s only partially working with a manual workaround (more on that below).
  - I also set up audit logging in Google Sheets to keep track of every action—pretty neat.

## How I Built It
- *Tools*: I used n8n Cloud to put this together, skipping Docker as per the task requirements. It’s all running on n8n’s hosted platform with nodes for Webhook, Google Drive, Google Sheets, and Twilio.
- *Workflow*: The setup takes WhatsApp messages, figures out the command, does the file action, and logs it. Twilio sends responses back, though I hit some limits there.
- *Note*: No Docker was used—everything’s done straight in n8n Cloud!

## Challenges I Faced
- Getting the file content for SUMMARY was tricky because the n8n Google Drive node didn’t cooperate fully, so I couldn’t pull text from files easily.
- The OpenAI API kept giving me "Too Many Requests" errors, which stopped the automatic summarization from working smoothly.
- I worked around these by using manual text input for SUMMARY and spacing out my tests, but I couldn’t fully fix them due to time and API limits. It’s a work in progress!

## How to Set It Up
1. *What You Need*:
   - An n8n Cloud account (check out https://cloud.n8n.io).
   - Google Drive API access with OAuth2 credentials.
   - A Twilio account set up with the WhatsApp Sandbox.
   - An OpenAI API key (optional, for the partial summarization).
   - A Google Sheet with a valid Sheet ID.
2. *Steps*:
   - Import the workflow.json file into n8n Cloud.
   - Plug in your Google Drive, Twilio, and Google Sheets credentials in the nodes.
   - Link the Webhook URL from n8n Cloud to your Twilio WhatsApp Sandbox (e.g., https://<your-n8n-cloud>.app.n8n.cloud/webhook/<path>).
   - Update the Sheet ID in the Google Sheets nodes.
3. *Testing*:
   - Try commands like list, upload etc. respectively via WhatsApp and check the Google Sheet for logs.
   - For SUMMARY, you’ll need to manually add text for now—watch out for those API limits!
4. *Tip*: Take it slow with the OpenAI part to avoid hitting request limits.

## Demo Video
I’ll include a demo video link in the submission form, showing how the workflow runs with the commands I got working.

## A Little Help Along the Way
I used ChatGPT to get some guidance when I got stuck—big thanks to it for helping me figure things out! Also, a shoutout to the support team for their patience.

## Done by
- Gurpreet Kaur
