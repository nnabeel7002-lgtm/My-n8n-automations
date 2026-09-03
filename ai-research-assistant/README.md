# 🔎 AI Research Assistant

An AI-powered research chatbot built with **n8n** and **Ollama**. It allows users to ask research questions and uses web search to retrieve current information before generating a concise AI-powered summary.

## ✨ Features

- 💬 Conversational chat interface using n8n Chat Trigger
- 🤖 Local AI processing with Ollama
- 🔎 Web search for current and recent information
- 🧠 Conversation memory using n8n Simple Memory
- 📝 AI-generated summaries of search results
- 🔐 No paid AI API required
- 💻 Runs locally with Ollama

## 🏗️ Workflow Architecture

```text
                 ┌── Simple Memory
                 │
Chat Trigger → AI Agent
                 │
                 ├── Ollama Chat Model
                 │
                 └── HTTP Request Tool
                         ↓
                    DuckDuckGo
                         ↓
                    Search Results
                         ↓
                      AI Agent
                         ↓
                       Answer
