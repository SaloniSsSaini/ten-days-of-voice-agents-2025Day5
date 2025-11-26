# 🎙️ Day 5 — Simple FAQ SDR + Lead Capture Voice Agent  
### Murf AI Voice Agent Challenge — 10 Days of Voice Agents

This project implements a **Sales Development Representative (SDR)** voice agent that can:

✅ Answer company FAQs using RAG  
✅ Talk naturally with users  
✅ Ask lead-qualification questions  
✅ Capture lead details into JSON  
✅ Detect end-of-call and generate a summary  
✅ Uses **Murf Falcon — the fastest TTS API**

Built using **LiveKit Agents**, **Python**, **Next.js**, and **Murf Falcon**.

---

## 🚀 Features (Day 5 Requirements)

### 🔹 1. FAQ-Based Question Answering  
- Loads FAQ content from `day5/shared-data/day5_company_faq.json`  
- Uses a simple **TF-IDF RAG model** to find the best FAQ answer  
- Agent answers strictly from FAQ (no hallucinations)  

### 🔹 2. SDR Persona  
Agent behaves like a friendly SDR:
- Greets warmly  
- Asks what brought the user here  
- Understands user needs  
- Gives short, helpful answers  
- Keeps conversation on track  

### 🔹 3. Lead Capture  
The agent collects:
- Name  
- Company  
- Role  
- Email  
- Use case  
- Team size  
- Timeline (now / soon / later)

All details are stored in:  
📁 `day5/shared-data/leads.json`

### 🔹 4. End-of-Call Summary  
When user says *“That’s all”, “I’m done”, “Thanks”*:
- Agent summarizes the lead information  
- Saves lead JSON  
- Ends the call politely  

---

## 🛠️ Tech Stack

| Layer | Tech |
|------|------|
| Voice Streaming | LiveKit Agents |
| STT / VAD | LiveKit + Silero |
| TTS | **Murf Falcon API** |
| FAQ Retrieval | Python + TF-IDF |
| Frontend | Next.js (App Router) |
| Backend | Python (Agent server) |
| Storage | Local JSON files |

---

## 📂 Project Structure

```
day5/
 ├── backend/
 │    ├── src/
 │    │    ├── agent.py               # Main SDR Agent logic
 │    │    ├── murf_tts.py            # Murf Falcon TTS
 │    │    └── test files
 │    └── .env.example
 │
 ├── frontend/
 │    ├── app/                        # UI for Voice Agent
 │    └── components/
 │
 ├── shared-data/
 │    ├── day5_company_faq.json       # FAQ content for RAG
 │    └── leads.json                  # Captured leads saved here
 │
 ├── start_app.sh                     # Start frontend + backend
 └── README.md
```

---

## ▶️ How to Run Locally

### 1️⃣ Install dependencies  
**Backend:**
```bash
cd day5/backend
pip install -r requirements.txt
```

**Frontend:**
```bash
cd day5/frontend
pnpm install
```

---

### 2️⃣ Add Environment Variables  
Copy and edit:

```
day5/backend/.env.example → .env
day5/frontend/.env.example → .env
```

Add:
- LIVEKIT URL  
- LIVEKIT API Key  
- LIVEKIT Secret  
- **MURF_API_KEY**  

---

### 3️⃣ Start App (Easy way)
From project root:

```bash
./start_app.sh
```

This will:

- Start backend agent  
- Start frontend  
- Open the UI in browser  
- Connect mic → begin voice conversation  

---

## 🧪 How It Works (Flow)

1. User speaks → STT converts speech to text  
2. Agent checks:  
   - Is this FAQ question? → Run RAG → speak answer  
   - Is user giving lead info? → Store values  
3. After collecting all fields → Agent shows summary  
4. User says "thanks" → save lead → end session  

---

## 🎥 Demo  
👉 *Add your video link here after uploading on LinkedIn.*

---

## 📝 Day 5 Submission  
This project completes the **Primary Goal** of Day 5:

✔ FAQ SDR  
✔ Lead Capture  
✔ Summary Generation  
✔ Murf Falcon TTS  
✔ LiveKit Agent Integration  
✔ Working Frontend + Backend  

---

## 📌 Developer  
**Saloni Saini**

---

If you like this project, ⭐ star the repo!

