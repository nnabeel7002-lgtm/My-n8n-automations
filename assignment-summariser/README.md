# 📝 Assignment Summarizer

An n8n workflow that uses **Ollama (Llama 3.2 1B)** to summarize assignments or articles and return structured information.

## Workflow

Webhook → AI Agent → Validate & Parse → IF → Response

## Features

- 📝 Assignment/article summarization
- 🔑 Key point extraction
- 📖 Important terms
- ❓ Revision questions
- ✅ Action items
- 🔍 JSON validation
- ⚠️ Error handling for invalid AI output
- 🤖 Local AI using Ollama

## Input

```json
{
  "text": "Paste your assignment or article here..."
}

## Output

```json
{
  "success": true,
  "summary": "...",
  "key_points": [],
  "important_terms": [],
  "questions": [],
  "action_items": []
}

## Technologies

- n8n
- Ollama
- Llama 3.2 1B
- Webhooks
- JSON
- JavaScript

## Purpose

Built to practice **AI integration, structured outputs, JSON parsing, validation, and error handling in n8n**.