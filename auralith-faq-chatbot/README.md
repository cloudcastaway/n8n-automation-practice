# Auralith FAQ Chatbot

This repository contains two n8n workflows that power the Auralith FAQ Chatbot: an AI-enhanced assistant capable of responding to user messages using a semantic FAQ database, and a document ingestion system to keep that database updated via Google Drive uploads.

## Overview

The system consists of two main workflows:

1. **Auralith Chat Agent**  
   Responds to user messages using context, semantic FAQ search, and a language model. Can also store user contact information.

2. **Auralith Uploader**  
   Monitors a Google Drive folder for new files, extracts and processes their contents, and updates the Pinecone vector database with embeddings.

## Workflows

### 1. Auralith Chat Agent

This workflow manages user interactions through a chat interface. It uses memory, semantic search, and a chat model to provide relevant answers from the FAQ vector store.

#### Features

- Routes and interprets incoming chat messages
- Maintains memory to preserve conversational context
- Retrieves FAQ answers using semantic vector search
- Uses OpenAI to generate contextual responses
- Optionally stores user contact data in Airtable

#### Annotated Diagram

![Auralith Chat Agent](./images/auralith-chat-agent-annotated.png)

#### JSON Export

- [Download Auralith Chat Agent Workflow](./workflows/auralith-chat-agent.json)

---

### 2. Auralith Uploader

This workflow supports the chat agent by ingesting new files into the FAQ system. It extracts, splits, embeds, and indexes document content for use in future semantic queries.

#### Features

- Watches Google Drive for new file uploads
- Extracts and splits file content into chunks
- Creates vector embeddings using OpenAI
- Stores data in Pinecone for fast vector search

#### Annotated Diagram

![Auralith Uploader](./images/auralith-uploader-annotated.png)

#### JSON Export

- [Download Auralith Uploader Workflow](./workflows/auralith-uploader.json)

---

## Technologies Used

- [n8n](https://n8n.io)
- [OpenAI API](https://platform.openai.com)
- [Pinecone](https://www.pinecone.io)
- [Airtable](https://airtable.com)
- [Google Drive API](https://developers.google.com/drive)

## Deployment

### Requirements

- Running n8n instance (local, Docker, or Render)
- API keys for OpenAI, Pinecone, Airtable, and Google Drive
- Necessary credentials configured in n8n

### Setup Instructions

1. Import the provided JSON workflows into your n8n instance.
2. Configure authentication for all connected services (OpenAI, Pinecone, Airtable, Google Drive).
3. Deploy the Auralith Chat Agent to handle incoming chat messages.
4. Activate the Auralith Uploader to ingest files from Google Drive automatically.

---

## Testing

- Use "Test workflow" in n8n to simulate a document upload or message.
- Upload supported files to Google Drive and verify they appear in Pinecone.
- Send a sample message to the chatbot and confirm the semantic response is accurate.

---

## Notes

The workflows include visual annotations explaining the function of each node. These are visible in the annotated screenshots above. No additional `NOTES.md` is necessary.

---

## File Structure

```plaintext
/
auralith-faq-chatbot/
├── README.md
├── images/
│   ├── auralith-chat-agent-annotated.png
│   └── auralith-uploader-annotated.png
├── workflows/
│   ├── auralith-chat-agent.json
│   └── auralith-uploader.json