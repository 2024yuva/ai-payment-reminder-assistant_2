# AI Payment Reminder & Personal Finance Voice Assistant – README.md

## 🧠 Overview

This project is an **AI-powered Payment Reminder & Personal Finance Voice Assistant** built using **n8n**, **Google Gemini**, **AWS Lambda**, **Google Calendar**, **Sentiment Analysis**, **11 Labs**, and **Vapi**.

It listens to users through voice, understands payment-related concerns, identifies emotions, and responds with personalized voice messages. It can also schedule due dates, set reminders, and coach users calmly when they feel stressed.

This combines **Option A (Payment Reminder Assistant)** + **Option C (Hybrid Financial Assistant)** into one powerful workflow.

---

## 🚀 Features

### **1. Voice + Text AI Agent**

* Receives user input through webhook.
* Uses **Google Gemini Chat Model** for smart reasoning.
* Maintains short-term memory using **n8n Simple Memory**.

### **2. Smart Event Creation**

* Detects event-related queries.
* Creates Google Calendar events dynamically.

### **3. Sentiment Analysis Engine**

* Classifies user tone as:

  * `Positive`
  * `Neutral`
  * `Negative`
* Routes responses through conditional logic (IF nodes) to personalize replies.

### **4. Dynamic Response Generation**

* Uses multiple Edit Fields nodes to craft personalized replies depending on sentiment.
* Converts these responses into natural-sounding speech using **11Labs**.

### **5. Voice Delivery via Vapi**

* Sends AI-generated audio back through Vapi.
* Workflow finally responds to the initial webhook with a processed audio + text response.

### **6. Lambda Action Handler**

* Custom AWS Lambda function for business logic or external processing.

---

## 🧩 Workflow Architecture

Below is the high-level flow:

1. **Webhook** receives user request → forwards message.
2. **AI Agent** processes query using Gemini + Memory.
3. If event creation is needed → **Google Calendar: Create Event**.
4. Output sent to **Sentiment Analysis**.
5. IF conditions split into three emotional paths.
6. Each path edits fields to craft specific responses.
7. Response sent to **11Labs** for voice generation.
8. **Vapi** returns audio to client.
9. Final data sent back via **Respond to Webhook**.

---

## 🛠️ Tech Stack

| Component                   | Purpose                            |
| --------------------------- | ---------------------------------- |
| **n8n Workflow Automation** | Main orchestration engine          |
| **Google Gemini**           | Language reasoning & chatbot logic |
| **Google Calendar API**     | Event creation                     |
| **AWS Lambda**              | External custom logic              |
| **11 Labs**                 | Voice generation                   |
| **Vapi**                    | Voice assistant delivery           |

---

## 📌 Installation

### **Prerequisites**

* n8n installed (Cloud or Self-hosted)
* Google Cloud Project with Gemini + OAuth credentials
* AWS Lambda configured with required role
* 11Labs API key
* Vapi project + assistant setup

### **Steps**

1. Import the workflow in n8n.
2. Add all environment credentials:

   * Google Gemini
   * Google Calendar
   * 11Labs
   * Vapi
3. Update your webhook URL wherever needed.
4. Deploy workflow.

---

## 🎯 Use Cases

* Intelligent customer support agent
* Automated scheduler
* Emotion-aware voice assistant
* Productivity automation bot
* Payment reminder / AI receptionist system

---

## 🏆 Hackathon Ready Submission

This workflow is fully functional, modular, scalable, and demonstrates:

* **Generative AI reasoning**
* **Emotion-driven response branching**
* **Voice transformation pipeline**
* **Cross‑platform automation**

---

## 👥 Team Credits

* Designed & Developed by: [Srinidhi](https://github.com/srinidhi31-max) & [Yuva](https://github.com/2024yuva)
* Built for: *[Agentic AI Hackathon with IBM watsonx Orchestrate]*
* Powered by: n8n + Google + AWS + 11Labs + Vapi

---

* A **project description** for submission form
* A **pitch deck** for the hackathon
