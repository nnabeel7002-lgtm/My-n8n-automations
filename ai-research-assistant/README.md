🔎 AI Research Assistant
An AI-powered research chatbot built with n8n and Ollama. It allows users to ask research questions and uses web search to retrieve current information before generating a concise, AI-powered summary.

✨ Features
💬 Conversational chat interface using n8n Chat Trigger

🤖 Local AI processing with Ollama

🔎 Web search for current and recent information

🧠 Conversation memory using n8n Simple Memory

📝 AI-generated summaries of search results

🔐 No paid AI API required

💻 Runs locally with Ollama

🏗️ Workflow Architecture
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
⚙️ How It Works
The user enters a research question through the Chat Trigger.

The AI Agent analyzes the question.

If current or recent information is required, the agent calls the HTTP Request Tool.

The HTTP Request Tool searches the web using DuckDuckGo.

The search results are returned to the AI Agent.

Ollama processes the information and generates a concise response.

Simple Memory maintains context between messages.

🧪 Example
User
Find the latest information about lithium battery technology.

AI Assistant
The agent recognizes that the question requires current information, performs a web search, and summarizes the relevant findings.

Another example:

What are the latest developments in solid-state batteries?

The assistant searches for recent information and provides a summarized response.

🛠️ Technologies Used
Technology	Purpose
n8n	Workflow automation
Ollama	Local LLM execution
Llama 3.2 1B	AI language model
DuckDuckGo	Web search
HTTP Request Tool	Search API/tool integration
Simple Memory	Conversation context
💰 Cost
This project is designed to use free/local tools:

n8n — local instance

Ollama — local

Llama 3.2 1B — local

DuckDuckGo HTML search — free for this practice project

No OpenAI, SerpAPI, or paid AI API is required.

📁 Project Structure
02-ai-research-assistant/
│
├── workflow.json
└── README.md
workflow.json contains the exported n8n workflow.

🚀 Setup
1. Install Ollama
Install Ollama and make sure the model is available:

ollama list
The workflow uses:

llama3.2:1b
2. Import the workflow
Import workflow.json into your n8n instance.

3. Configure Ollama
Connect the Ollama Chat Model node to your local Ollama credential.

For a local Ollama installation, the server is typically available at:

http://localhost:11434
4. Activate/Test the workflow
Open the Chat Trigger and ask a research question.

🔒 Security
No API keys or passwords should be stored directly inside this repository.

Credential references included in the n8n workflow export are not the same as the actual credential secrets.

Do not commit:

.env
credentials.json
secrets.json
*.key
*.pem
🎯 Purpose
This project was created as part of a collection of n8n automation practice projects, with the goal of learning how to combine AI agents, local LLMs, memory, tools, APIs, and automation workflows.

Workflow #2 of 10 — AI Research Assistant 🚀