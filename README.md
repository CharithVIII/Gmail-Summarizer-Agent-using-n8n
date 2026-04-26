# 📧 n8n Gmail AI Summarizer

A beginner-friendly n8n workflow that uses local LLMs (Ollama) to automatically summarize incoming Gmail messages.

## 🚀 Overview
This project automates the process of reading long emails. Whenever a new message hits your inbox, n8n triggers an AI processing chain that:
1. Pulls the email content.
2. Sends it to a local AI model (Ollama).
3. Summarizes the content into two concise bullet points.
4. Emails the summary back to you.

## 🛠️ Prerequisites
- **n8n**: Installed locally or via Docker.
- **Ollama**: Running locally with `gemma`, `llama3`, or `mistral`.
- **Google Cloud Account**: To enable the Gmail API and create OAuth2 credentials.

## ⚙️ Configuration Tip
When setting up the **Basic LLM Chain**, use the following expression to link your Gmail Trigger to the AI:

```javascript
Summarize this email in 2 short bullet points. Return ONLY the bullet points, no explanation or thinking process.
Subject: {{ $json.subject }}
Content: {{ $json.text }}
