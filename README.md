# AutoTube-AI-Photos-Sounds-N8N 

# 🎬 AutoTube-AI: Automated Video Creation & YouTube Publishing System

A fully automated, production-ready AI video generation and publishing pipeline built entirely using **n8n**. This workflow orchestrates advanced AI agents to transform a text prompt or form input into a fully rendered, high-quality video with voiceovers and dynamic visuals, then automatically publishes it directly to YouTube. 🚀

> ### 📝 Repository Description (سطرين للوصف الخارجي)
> A self-hosted n8n pipeline that automates the entire video production lifecycle—generating voiceovers via ElevenLabs, visuals via Fal.ai/Replicate, rendering through Shotstack, and auto-publishing directly to YouTube.

---

## 🌟 Key Features

### 1. 📝 Input & Multi-Agent Orchestration
* **📋 Dynamic Form Input:** Starts with a custom `Movie Generation Form` node to capture user scripts or content ideas.
* **🧠 Split AI Orchestration:** Utilizes twin **OpenAI Chat Model** instances behind specialized AI Agents to concurrently process the creative script into audio and visual blueprints.

### 2. 🎙️ Parallel Production Pipeline
* **🗣️ Audio Generation Branch:** Connects to the **ElevenLabs API** to generate lifelike AI voiceovers and stores the resulting audio file.
* **🎨 Visual Generation Branch:** Connects to high-performance image generation clouds (**Fal.ai / Replicate API**), extracting prediction IDs and polling dynamically until the visual assets are fully generated and ready.

### 3. 🎬 Cloud Rendering & Auto-Publishing
* **🔀 Smart Branch Merging:** Combines the generated audio paths and visual assets into a unified payload using data transformation code nodes.
* **🎞️ Shotstack Integration:** Submits the compiled elements to the **Shotstack API** to programmatically render a high-definition MP4 video file.
* **📺 Automated YouTube Upload:** Monitors the video render status, downloads the final MP4, and uses the **YouTube Upload** node to push the finished video straight to your channel completely hands-free.

---

## 🏗️ Architecture & Workflow

Based on the system design in `image_ea9f79.jpg`, the architecture functions as a parallel distributed pipeline:

---

## 🛠️ Prerequisites & Tech Stack

* **🔗 n8n** (Self-hosted or Cloud instance)
* **🧠 OpenAI API Key** (For driving the twin creative AI Agents)
* **🗣️ ElevenLabs API Key** (For professional voiceover generation)
* **🎨 Fal.ai / Replicate API Key** (For state-of-the-art image generation models)
* **🎞️ Shotstack API Key** (For cloud-based video editing and rendering)
* **📺 Google Developer Console Credentials** (With YouTube Data API v3 enabled for publishing)

---

## 🚀 Setup Instructions

1. **📥 Import the Workflow:**
   * Download the `.json` file of this workflow.
   * Open your n8n instance, create a new workflow, and click on **Import from File** (or paste the JSON).

2. **🔑 Configure Node Credentials:**
   * Link your **OpenAI**, **ElevenLabs**, and **Shotstack** credentials inside their respective API nodes.
   * Configure your Cloud Image Generator endpoint credentials (e.g., **Fal.ai**).
   * Authenticate your **YouTube OAuth2** credentials to grant n8n uploading permissions.

3. **⚡ Run & Automate:**
   * Trigger the `Movie Generation Form`, fill in your topic, and execute the workflow.
   * Watch n8n manage the parallel processes, wait for rendering to complete, and check your YouTube Studio for the newly uploaded video!

---

## 📝 License
This project is open-source and available under the MIT License.
