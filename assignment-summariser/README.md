# 📝 Assignment Summarizer

An n8n workflow that uses **Ollama (Llama 3.2 1B)** to summarize assignments or articles and return structured data. 

## 🔄 Workflow Architecture

`Webhook` ➔ `AI Agent` ➔ `Validate & Parse` ➔ `IF (Error Check)` ➔ `Response`

## ✨ Features

- 📝 **Assignment & Article Summarization:** Condenses long-form text into digestible overviews.
- 🔑 **Key Point Extraction:** Highlights the core arguments and facts.
- 📖 **Important Terms:** Identifies domain-specific vocabulary and keywords.
- ❓ **Revision Questions:** Generates study questions to test comprehension.
- ✅ **Action Items:** Extracts actionable tasks mentioned in the text.
- 🔍 **JSON Validation:** Ensures the AI agent returns strictly formatted data.
- ⚠️ **Error Handling:** Gracefully manages and routes invalid AI outputs.
- 🤖 **Local AI:** Powered securely and locally using Ollama.

## 🚀 Usage

### Input
Send a POST request to the workflow's webhook URL with the following JSON structure:

```json
{
  "text": "Paste your assignment or article text here..."
}
```

### Output
If successful, the workflow returns a strictly structured JSON response:

```json
{
  "success": true,
  "summary": "A brief overview of the provided text...",
  "key_points": [
    "First main takeaway",
    "Second main takeaway"
  ],
  "important_terms": [
    "Term 1",
    "Term 2"
  ],
  "questions": [
    "What is the primary argument of the text?"
  ],
  "action_items": [
    "Review chapter 4",
    "Submit draft by Friday"
  ]
}
```

## 🛠️ Technologies

- **n8n:** Workflow automation and routing.
- **Ollama:** Local LLM environment.
- **Llama 3.2 1B:** Base AI model for lightweight, fast inference.
- **Webhooks:** REST API trigger mechanism.
- **JSON & JavaScript:** Data parsing, formatting, and conditional logic.

## 🎯 Purpose

This project was built to practice practical AI integration, enforce structured outputs from LLMs, and handle JSON parsing, validation, and error routing within n8n.

