# AI Travel Assistant

An AI-powered travel planning assistant built with n8n and Ollama.

## Features

- Answers travel planning questions
- Retrieves weather forecasts
- Finds attractions and museums
- Uses AI to decide which tools are required
- Combines results into one response
- Uses local Ollama LLM

## Architecture

Chat Trigger
    ↓
AI Agent
    ├── Get Weather Tool
    │       ↓
    │   Open-Meteo
    │
    └── Find Places Tool
            ↓
        OpenStreetMap / Overpass

## Technologies

- n8n
- Ollama
- Llama 3.2 1B
- Open-Meteo
- OpenStreetMap
- Nominatim
- Overpass API

## Example

User:
"I'm going to Lahore this weekend. What should I do and what's the weather?"

The AI determines that both the weather and places tools are required and combines their results.