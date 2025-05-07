# n8n-automation-practice

This repository brings together workflows developed with [n8n](https://n8n.io) as part of a continuous exploration of automation using LLMs, APIs, and low-code tools. The projects reflect a focus on hands-on learning, system integration, and task orchestration.

This collection includes both independently built workflows and others created by following guided walkthroughs as part of an educational course.

## Projects

### Original Projects

- **[Daily Briefing Bot](./daily-briefing-bot)**  
  Automates the delivery of personalized daily briefings via Telegram or email. It gathers user-specific data such as city and currency preferences, retrieves relevant weather and exchange rate information, and formats the output using OpenAI.

- **[YouTube Tracker](./youtube-tracker)**  
  Monitors a list of YouTube channels and sends Telegram alerts only when new videos match custom keywords. Logs relevant videos to Airtable and updates timestamps to prevent duplicates.

### Walkthrough-Based Projects

- **[Auralith FAQ Chatbot](./auralith-faq-chatbot)**  
  A semantic search-based chatbot that answers user queries by matching against a FAQ dataset stored in a vector database.

- **[Telegram Multitool Chat Agent - Basic](./telegram-multitool-basic)**  
  A Telegram-based AI chatbot that routes queries to either OpenAI, a calculator, or a custom search agent.

- **[Telegram Multitool Chat Agent - Expanded](./telegram-multitool-expanded)**  
  An enhanced version of the basic agent with support for voice input, calendar management, and Gmail integration via sub-workflows.

- **[Pet Adoption Email](./pet-adoption-email)**  
  Sends a formatted email via Gmail whenever a new record is added to an Airtable pet adoption table.

## Technologies Used

- OpenAI (Chat, Embedding, and Transcription APIs)
- Pinecone (Vector storage)
- Airtable (Record management)
- Telegram Bot API
- Gmail API
- Google Calendar API
- SerpAPI (for search)
- n8n (workflow orchestration)

## Purpose

This repository serves as both a personal learning log and a practical demonstration of how to use n8n to build real-world, AI-powered automation workflows with modular design and external API integrations.

## Observação

Este repositório está documentado em inglês por padrão. Caso prefira uma versão em português, estou disponível para fornecer ou explicar o conteúdo conforme necessário.