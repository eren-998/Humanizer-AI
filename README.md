# The Humanizer 🧑‍💻

## Anti-Jargon Agent Powered by Gemini & n8n

[![Mulerun Agent Status](https://img.shields.io/badge/Status-LIVE%20on%20Mulerun-B84AFF?style=for-the-badge)](https://mulerun.com/@Eren_kaif/the-humanizer)
[![LLM Backend](https://img.shields.io/badge/Model-Gemini%202.5%20Flash-0069B5?style=for-the-badge)](https://ai.google.dev/models/gemini)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)

### 🔗 Product Link
Use the agent directly on the Mulerun Marketplace: **[The Humanizer 🧑‍💻](https://mulerun.com/@Eren_kaif/the-humanizer)**

---

## 🚀 Core Agent Architecture (Technical Deep Dive)

This project implements a single-workflow, high-fidelity content transformation agent built on the n8n automation platform. Its architecture is optimized for fast execution and high visual fidelity (UX).

### Key Components:
| Component | Function | Technical Node |
| :--- | :--- | :--- |
| **LLM Engine** | **Core Transformation & Logic.** Handles Anti-Jargon filtering and Dynamic Tone Adaptation. | `lmChatGoogleGemini` |
| **Agent Framework** | **System Prompt Orchestration.** Executes the defined system message and input variables. | `AI Agent (LangChain)` |
| **UX Layer** | **Branded Output Rendering.** Transforms raw text into a clean, modern, copy-enabled HTML page. | `Code in JavaScript` |
| **Input Schema** | **Input/Default Handling.** Manages optional fields (TONE, AUDIENCE) via implicit defaults. | `Form Trigger` |

### The Anti-Jargon Filter (IP)
The agent uses an internal **KILL LIST** embedded in the System Message to surgically remove over a dozen common AI-generated buzzwords (e.g., *pivotal, synergy, delve, leverage*), ensuring the output passes human scrutiny.

---

## ⚙️ Setup & Deployment

### 1. Workflow Installation
1.  **Download:** Clone this repository or download the `The Humanizer 🧑💻 (2).json` file from the `workflows/` directory.
2.  **Import:** Import the JSON file directly into your n8n instance.
3.  **Credentials:** Open the **Agent's Brain** node and ensure your **Google Gemini API Key** is correctly configured in the credentials.

### 2. Mulerun Product Documentation

This agent is positioned as the ultimate tool for refining AI output.

#### **Overview***
**Humanize AI** instantly transforms cold, verbose LLM outputs into natural, flowing, and relatable human conversation, designed to eliminate algorithmic jargon and boost authenticity.

#### **Description***
**Humanize AI** is engineered to detect and eliminate over 50 common AI buzzwords—such as "delve," "pivotal," "synergy," and "leverage"—replacing them with clear, concise, and human-centric language. It features **Dynamic Tone Control** and **Audience Adaptation**, ensuring your message resonates authentically with any reader, from executives to casual chat groups.

#### **Product Advantages**
* **Zero AI Jargon:** Automatically filters out over 50 common robotic words.
* **100% Natural Flow:** Improves sentence variety and promotes active voice.
* **Instant Tone Shift:** Transforms text into multiple distinct personalities (Professional, Casual, Witty) in seconds.
* **High UX Output:** Renders the result in a clean, copy-enabled, branded HTML page.

---

## 📝 Dynamic Prompt Guide

The agent relies on clean, structured input for maximum effect.

| Field | Description | Default Value | Example Input |
| :--- | :--- | :--- | :--- |
| **Text for Humanize** | The core text to be processed. (Required) | *(N/A)* | `It is imperative that we strategically leverage...` |
| **TONE** | Stylistic intent for the rewrite (e.g., Casual, Sarcastic). | `Professional` | `Sarcastic` |
| **AUDIENCE** | Who is the final reader? (e.g., Manager, Students, Friends). | `General Public` | `Business Stakeholders` |
| **LANGUAGE** | Output language (e.g., English). | `English` | `English` |

### Example Prompt (Sarcastic Roast)
`Role: You are a witty, sarcastic writer who critiques corporate speak. Task: Rewrite this paragraph about "synergy" and "paradigm shifts" to playfully mock the original text while conveying its basic meaning. Constraints: Use dry humor and a subtly critical tone. Highlight the absurdity of the original phrasing.`

**Input Example:**
`To foster holistic growth, we must strategically pivot our initiatives to achieve scalable synergy, enabling us to democratize access to innovative solutions for all stakeholders.`

**Expected Output:**
