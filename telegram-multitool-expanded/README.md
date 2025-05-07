# Telegram Multitool Chat Agent - Expanded

This project contains three n8n workflows that power the Telegram Multitool Chat Agent - Expanded: a Telegram-based AI chatbot capable of responding to both text and voice messages, sending and retrieving emails, and managing calendar events through sub-workflows.

## Overview

The chatbot is built from three connected workflows:

1. **Telegram Multitool Chat Agent - Expanded**  
   Handles incoming Telegram messages (both text and voice), performs tool-based routing, and responds via OpenAI and Google APIs.

2. **Calendar Agent**  
   A sub-workflow triggered to handle event creation, updates, deletion, and retrieval from Google Calendar.

3. **Email Agent**  
   A sub-workflow used for retrieving, labeling, replying, and sending emails via Gmail.

## Workflows

### 1. Telegram Multitool Chat Agent - Expanded

This workflow listens for Telegram messages, distinguishes between text and audio, and routes queries to internal or external tools using an AI Agent.

**Features:**
- Accepts both text and voice input from Telegram
- Converts voice messages to text using OpenAI
- Maintains memory across user interactions
- Interacts with Gmail and Google Calendar through dedicated agents
- Sends final response back to the user via Telegram

**Diagram:**

![Telegram Multitool Chat Agent - Expanded](./images/telegram-multitool-expanded-annotated.png)

**JSON Export:**
- [telegram-multitool-expanded.json](./workflows/telegram-multitool-expanded.json)

---

### 2. Calendar Agent

This sub-workflow handles all calendar-related actions on behalf of the main agent, including success/failure feedback.

**Features:**
- Creates events (with or without guests)
- Updates or deletes existing events
- Retrieves upcoming events
- Sends structured responses back to the main agent

**Diagram:**

![Calendar Agent](./images/calendar-agent-annotated.png)

**JSON Export:**
- [calendar-agent.json](./workflows/calendar-agent.json)

---

### 3. Email Agent

This sub-workflow handles a range of Gmail interactions triggered by the main workflow.

**Features:**
- Retrieves emails and labels
- Sends emails or replies (immediate or draft)
- Applies labels, marks emails as read/unread
- Returns structured output based on result

**Diagram:**

![Email Agent](./images/email-agent-annotated.png)

**JSON Export:**
- [email-agent.json](./workflows/email-agent.json)

---

## Technologies Used

- [n8n](https://n8n.io)
- [Telegram Bot API](https://core.telegram.org/bots/api)
- [OpenAI API](https://platform.openai.com)
- [Google Calendar API](https://developers.google.com/calendar)
- [Gmail API](https://developers.google.com/gmail)

## Setup

### Prerequisites

- A running instance of n8n (locally or hosted)
- Telegram bot token
- OpenAI API key
- Google Cloud project with Gmail and Calendar APIs enabled
- Environment variables or credentials set up in n8n

### Deployment Steps

1. Import all three JSON workflows into your n8n instance.
2. Set up credentials for Telegram, OpenAI, and Google (OAuth2).
3. Deploy and activate the Telegram Multitool Chat Agent.
4. Send sample voice and text queries to test calendar and email operations.

## Testing

- Send a voice message like “What’s on my calendar today?” and check if the agent responds with events.
- Send an email command like “Send an email to Alice” to trigger Gmail integration.
- Use "Test workflow" in n8n to simulate tool output and success/failure paths.

## File Structure

```plaintext
/
telegram-multitool-expanded/
├── README.md
├── images/
│   ├── telegram-multitool-expanded-annotated.png
│   ├── calendar-agent-annotated.png
│   └── email-agent-annotated.png
├── workflows/
│   ├── telegram-multitool-expanded.json
│   ├── calendar-agent.json
│   └── email-agent.json