# Mind Sync Smart Glasses Project**

# 🧠 Mind Sync Smart Glasses: AI-Powered Memory Recall System

This project is a full-stack AI wearable solution using smart glasses that autonomously capture images, convert them into structured memory using computer vision and NLP, and allow users to query their past visually and contextually using natural language.

> 📂 The system is divided across 4 repositories:

| Repository                                                             | Purpose                                            |
| ---------------------------------------------------------------------- | -------------------------------------------------- |
| [ESP32\_CAM](https://github.com/thejaAshwin62/ESP32_CAM)                | Firmware to capture and send images from ESP32-CAM |
| [FaceDetection](https://github.com/thejaAshwin62/face-service)         | Node.js service to detect and recognize faces      |
| [EmbeddingServices](https://github.com/thejaAshwin62/embedding-services) | Backend for image-to-text, vector embeddings       |
| [Frontend](https://github.com/thejaAshwin62/FE-Mind-Sync)                   | Web interface for query and memory visualization  |

---

## 🎯 Objective

To build a wearable system that captures visual experiences, processes them into searchable AI memory, and allows users to recall events through natural conversation.

---

## 🔧 Technologies Used

**Hardware:** ESP32-CAM, OV2640 camera, 3.7V Li-Po Battery
**Frontend:** React.js, Tailwind CSS, Vercel
**Backend:** Node.js, Express.js, MongoDB, Pinecone, HuggingFace, Together-AI
**Face Recognition:** face-api.js
**Deployment:** Render, Vercel, Ngrok (for development)

---

## ⚙️ How It Works

1. **Image Capture (ESP32-CAM)**

   * Captures images every 15 minutes
   * Sends via HTTP POST to backend

2. **Image Processing & OCR**

   * Extracts scene info using `facebook/detr-resnet-50`
   * Generates natural captions using `meta-llama`

3. **Embedding & Storage**

   * Creates 1024-d semantic vector using multilingual-e5
   * Stores embeddings in Pinecone

4. **Face Recognition**

   * Uses `face-api.js` to detect known individuals

5. **Frontend Query Interface**

   * Users ask: "Where was I last Monday at 3PM?"
   * Backend performs vector search and returns relevant event summary

---

## 🧩 Repository Overview

### 🔹 [ESP32\_CAM](https://github.com/thejaAshwin62/ESP32_CAM)

* Arduino sketch for ESP32
* Captures and transmits image data

### 🔹 [FaceDetection](https://github.com/thejaAshwin62/face-service)

* Express.js API with TensorFlow\.js & face-api.js
* Extracts and matches face vectors

### 🔹 [EmbeddingServices](https://github.com/thejaAshwin62/embedding-services)

* Main backend logic
* Handles image uploads, captioning, embedding, and semantic search

### 🔹 [Frontend](https://github.com/thejaAshwin62/FE-Mind-Sync)

* Built in React.js + Tailwind CSS
* Query interface with response viewer

---

## 🔐 Security & Privacy

* HTTPS for all data transfers
* Session-based user memory access
* Face embedding security and ID separation

---

## 🚀 Live Deployment

* Deployment [MindSync_AI Power Smart Glasses](https://mind-sync-eight.vercel.app/)

---

## 📌 Example Query

> **Q:** What did I do on Friday around 3 PM?

> **A:** You were with Surya attending a seminar on Ethical AI at 3:00 PM.

---

## 📈 Future Enhancements

* GPS-based memory tagging
* Speech input with real-time feedback
* Proactive reminders & activity tracking
* Biometric-secure login & memory access

---
