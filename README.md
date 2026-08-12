# 🤖 Digital Twin — AI-Powered Career Assistant

> **Talk to my AI twin about my career, experience, skills, and professional journey.**

An AI-powered **Digital Twin** built with Python, Gradio, and Google's Gemini API.  
It acts as a conversational version of me, answering questions about my professional background while using **AI tool calling** to capture meaningful interactions.

---

## ✨ What is a Digital Twin?

This project creates a conversational AI representation of my professional profile.

Instead of browsing through a traditional resume, you can simply ask questions like:

> 💬 "What technologies does Raj work with?"

> 💬 "Tell me about his GenAI experience."

> 💬 "What projects has he built?"

> 💬 "How can I get in touch with him?"

The AI uses my professional context and knowledge to provide conversational answers.

---

## 🚀 Features

### 🧠 AI-Powered Conversations
Uses Google's Gemini API through its OpenAI-compatible interface to generate natural conversations.

### 🛠️ AI Tool Calling
The assistant can intelligently trigger tools when required.

Currently implemented tools include:

- 📩 **Record user details**
  - Captures name
  - Email
  - Additional notes

- ❓ **Record unanswered questions**
  - Records questions the AI couldn't answer
  - Helps identify gaps in the Digital Twin's knowledge

### 🔔 Pushover Notifications

Important interactions can be sent through the **Pushover API**, allowing the owner to receive notifications when:

- Someone wants to get in touch
- A user provides their email
- The AI encounters an unanswered question

### 💬 Interactive Gradio UI

A clean conversational interface powered by Gradio with:

- Custom CSS
- Custom JavaScript
- Example prompts
- Chat history
- Responsive interface

---

## 🏗️ Architecture

```text
                    ┌──────────────────────┐
                    │      User            │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │     Gradio UI        │
                    │   Chat Interface     │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Python Backend     │
                    │      chat()          │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │     Gemini API       │
                    │  AI + Tool Calling   │
                    └──────────┬───────────┘
                               │
                    ┌──────────┴───────────┐
                    │                      │
                    ▼                      ▼
          ┌─────────────────┐    ┌──────────────────┐
          │ User Details    │    │ Unknown Question │
          │     Tool        │    │      Tool        │
          └────────┬────────┘    └─────────┬────────┘
                   │                       │
                   └───────────┬───────────┘
                               ▼
                    ┌──────────────────────┐
                    │   Pushover API       │
                    │    Notifications     │
                    └──────────────────────┘