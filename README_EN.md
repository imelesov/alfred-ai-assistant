# Alfred — AI Assistant with Graph Memory & Decay Mechanism

[![Python](https://img.shields.io/badge/Python-3.11%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Groq API](https://img.shields.io/badge/Groq-API-orange?logo=groq&logoColor=white)](https://groq.com/)
[![Obsidian](https://img.shields.io/badge/Obsidian-Compatible-purple?logo=obsidian&logoColor=white)](https://obsidian.md/)
[![License](https://img.shields.io/badge/License-Proprietary-red)](https://github.com/imelesov)

> **Alfred** is a personal AI assistant designed to solve the context-loss problem of modern LLMs. Instead of just storing a flat chat history, Alfred builds a dynamic **knowledge graph** that can be visualized in Obsidian.

> ⚠️ **Note:** This is a proprietary project. The source code is closed. This repository is intended for documentation, architecture overview, and release tracking only.

## 🧠 Core Features

* **Hybrid Memory System:** Combines a static core (Markdown prompts) with a dynamic graph memory. Facts (people, goals, emotions) are stored as nodes and edges in a JSON format via `NetworkX`.
* **Decay Mechanism (Auto-Forgetting):** Nodes have a `weight` and `last_seen` timestamp. If a topic is not mentioned for a long time, its weight decreases. When weight drops below `0.1`, the node is automatically archived. This keeps the "brain" clean and relevant.
* **Dynamic Graph Updates:** Alfred analyzes the dialogue using Groq API (JSON function calling) to automatically extract new entities and relationships without user intervention.
* **Obsidian Integration:** The JSON graph is automatically converted into Markdown files with wiki-links (`[[node]]`). Users can open the Obsidian Graph View and literally see the assistant's "brain" as an interactive web of thoughts.
* **Jarvis Persona:** Features a polite, concise, and slightly sarcastic British tone. It addresses the user respectfully and acts as a proactive assistant.

## 🛠 Tech Stack

* **Language:** Python 3.11+
* **LLM Provider:** Groq API (Primary: `llama-3.3-70b-versatile`, Fallback: `llama-3.1-8b-instant`)
* **Graph & Data:** NetworkX, JSON
* **Visualization:** Obsidian (Markdown + wiki-links)
* **Current Interface:** CLI (Terminal with `colorama`)
* **Upcoming Interface:** CustomTkinter (Desktop GUI in development)

## 🚀 Roadmap & Status

* **Status:** Beta version. Closed source.
* **Distribution:** Compiling to `.exe` (Bring Your Own API Key model — zero server costs for the developer).
* **Next steps:**
  - [ ] Release the desktop GUI application (CustomTkinter).
  - [ ] Implement offline Voice Interaction (TTS via `pyttsx3`).
  - [ ] Add Smart Home integration.

## 🔗 Links & Media

* **Official Website:** [melesov.netlify.app/alfred.html](https://melesov.netlify.app/alfred.html)
* **Telegram Channel (Dev Log):** [@alfred_ai_assistant](https://t.me/alfred_ai_assistant)
* **Author:** Abdula Melesov (mls)
  * [GitHub Profile](https://github.com/imelesov)
  * [Telegram](https://t.me/melesov)
  * [VC.ru Technical Article](https://vc.ru/dev/3227646-sozdanie-ii-assistenta-s-grafovoy-pamyatyu)

## 📄 License

Copyright (c) 2026 Abdula Melesov. All rights reserved. 
The code, architecture, and distribution rights belong exclusively to the author.
