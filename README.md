# Rural-guard— Rural Emergency AI Assistant

> AI-powered, voice-first emergency response assistant designed for
> villages and low-resource areas in India.

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 🎯 What is Rural guard?

Rural Guard helps people in rural India survive medical emergencies
when a doctor is not nearby. It understands voice or text in
Hindi and English, gives step-by-step first aid instructions,
and alerts family members and health workers automatically.

---

## ✨ Features

- 🗣️ Voice input via Whisper STT (Hindi + English)
- 🤖 AI guidance powered by GPT-4o-mini
- 📋 Structured first aid for bleeding, cardiac, burns, fractures, fever
- 📱 SMS alerts via Twilio (simulated in prototype)
- 🏥 Nearest hospital suggestions
- 📶 Offline fallback — works on 2G/3G
- 🔐 Security gate — rate limiting, input sanitization, anonymized logs
- 🔊 Hindi audio output via gTTS
- 🖥️ Gradio web UI — runs in browser, shareable public link
---

## 🏗️ Architecture
Voice/Text Input
↓
Whisper STT
↓
Security Gate (Auth + Rate Limit + Sanitize)
↓
AI Engine (GPT-4o-mini + Rule Engine)
↓
┌─────────────┬───────────────┬────────────┐
First Aid     Alert System    Data Logger
(Hindi steps) (Twilio SMS)    (JSON + hash)
└─────────────┴───────────────┴────────────┘
↓
gTTS Hindi Audio Output

---

## 🧰 Tech Stack

| Layer | Tool |
|---|---|
| Speech-to-Text | OpenAI Whisper |
| AI Engine | GPT-4o-mini |
| Text-to-Speech | gTTS |
| Web UI | Gradio |
| Alerts | Twilio (SMS/Call) |
| Database | Firebase (planned) |
| Backend | FastAPI (planned) |
| Dev Environment | Google Colab |

---

## 📁 Project Structure
sahayak-rural-emergency-ai/
├── rural_emergency_assistant.py  # Core pipeline (Cells 1–13)
├── gradio_deploy.py              # Gradio UI (Cells 14–18)
├── sahayak_colab.ipynb           # Full Colab notebook
├── emergency_log.json            # Auto-generated incident log
├── .gitignore
├── LICENSE
└── README.md
