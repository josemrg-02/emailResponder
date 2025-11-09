# 🤖 AI Email Auto-Responder + FAQ Updater (n8n + OpenAI + Gmail + Pinecone)

[![n8n](https://img.shields.io/badge/built%20with-n8n-orange?logo=n8n&logoColor=white)](https://n8n.io)
[![OpenAI](https://img.shields.io/badge/powered%20by-OpenAI-blue?logo=openai&logoColor=white)](https://openai.com)
[![Pinecone](https://img.shields.io/badge/vector%20db-pinecone-blueviolet?logo=pinecone&logoColor=white)](https://www.pinecone.io)
[![Gmail API](https://img.shields.io/badge/API-Gmail-red?logo=gmail&logoColor=white)](https://developers.google.com/gmail/api)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

An **AI-powered customer-support automation suite** built with **n8n**, **OpenAI GPT-4o**, **Gmail API**, **Google Drive**, and **Pinecone**.  
It contains two integrated workflows:

1. ✉️ **AI Email Auto-Responder** – reads, classifies, and replies to emails automatically.  
2. 📄 **FAQ Updater** – downloads your FAQ from Google Drive and uploads it to Pinecone to keep your vector database fresh.

---

## 🧠 Overview

Together, these workflows form a full **AI Customer Support System**:

- The **Auto-Responder** handles new customer emails with context-aware, friendly answers.  
- The **FAQ Updater** ensures your AI agent always uses the latest internal knowledge.

---

## 🚀 Features

### ✉️ AI Email Auto-Responder (`emailRespond.json`)
- 📥 Real-time Gmail trigger for incoming emails  
- 🧠 GPT-4o JSON classifier returning a real boolean (`true` / `false`)  
- 💬 AI support agent with a professional, empathetic tone  
- 📚 Pinecone integration for FAQ-based responses  
- 📤 Automatic Gmail replies  
- 🧾 Modular design (easily extendable with Sheets, Notion, or Slack)

### 📄 FAQ Updater (`PDF to PINECONE.json`)
- ⬇️ Downloads your **FAQ document** from **Google Drive**  
- 🔍 Splits the content intelligently into text chunks  
- 🧠 Generates **OpenAI embeddings**  
- 📦 Uploads the vectors into your **Pinecone** index (`customerSupport` namespace)  
- 🔁 Keeps your knowledge base synchronized with the latest document version

---

## 🧩 Tech Stack

| Component | Role |
|------------|------|
| **n8n** | Workflow automation platform |
| **OpenAI GPT-4o** | Text understanding + generation |
| **Gmail API** | Email trigger & replies |
| **Google Drive API** | Download FAQ documents |
| **Pinecone** | Vector DB for semantic search |
| **OpenAI Embeddings** | Text vectorization for Pinecone |

---

## ⚙️ How It Works

### Workflow 1 – AI Email Auto-Responder
1. **Gmail Trigger** → detects new emails.  
2. **OpenAI JSON Classifier** → decides if it’s a support case.  
3. **Switch Node** → routes relevant emails.  
4. **AI Support Agent** → generates a friendly, context-aware reply.  
5. **Pinecone Vector Store** → retrieves related FAQ content.  
6. **Gmail Reply** → sends the generated message back automatically.  

### Workflow 2 – FAQ Updater
1. **Manual Trigger** → click “Execute Workflow” in n8n.  
2. **Google Drive Node** → downloads the FAQ file.  
3. **Text Splitter** → divides the text into chunks.  
4. **OpenAI Embeddings** → creates vector representations.  
5. **Pinecone Vector Store** → inserts data into the `customerSupport` namespace.

