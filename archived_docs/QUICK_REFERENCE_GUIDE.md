# 🧠 AI Digital Brain - Quick Reference (Offline/Online/Hybrid)

## 📊 Feature Summary at a Glance

```
OFFLINE (15 Features)        ONLINE (5 Features)         HYBRID (6 Features)
│                            │                           │
├─ Background Remover        ├─ YouTube Summary          ├─ Chat System
├─ Local Chat                ├─ URL Summary              ├─ Web Creator
├─ Documents                 ├─ Web Research             ├─ Summarization
├─ Knowledge Base            ├─ Model Download           ├─ Multi-Agent
├─ Text Summary              ├─ Translation (online)     ├─ Knowledge Base
├─ Web Creator               │                           ├─ Document Proc
├─ Dashboard                 │
├─ Multi-Agent               │
├─ Auth/Sessions             │
├─ File Management           │
├─ PDF/OCR                   │
├─ Image Processing          │
├─ Browser Extension         │
├─ Chat History              │
└─ Model Management          │
```

---

## 🚀 Getting Started

### Setup (One Time)

1. **Install Ollama** → Download from ollama.ai
2. **Start Ollama** → `ollama serve` (background)
3. **Backend** → `cd backend && python run.py`
4. **Frontend** → `npm run dev`

### Access Points

| Interface | URL | Purpose |
|-----------|-----|---------|
| **Webapp** | http://localhost:5173 | Main UI |
| **API Docs** | http://localhost:8000/docs | All endpoints |
| **Dashboard** | In webapp | System monitoring |
| **Extension** | Browser right-click | Quick access |

---

## 💡 Use By Scenario

### **Scenario A: No Internet (Pure Offline)**

What works:
```
✅ Chat with AI
✅ Remove image backgrounds
✅ Upload & search documents
✅ Summarize text you paste
✅ Generate websites
✅ View chat history
✅ Monitor system
```

What doesn't work:
```
❌ Summarize YouTube videos
❌ Summarize web articles
❌ Search the internet
```

### **Scenario B: Internet Available (Hybrid)**

Additional features:
```
✅ Everything from Scenario A
✅ YouTube video summaries (10-30s)
✅ Web article summaries (3-10s)
✅ Internet research
✅ Cloud chat (if enabled)
✅ Download new models (caches them)
```

### **Scenario C: Privacy Critical**

Use only:
```
✅ Offline features only
✅ Internet fully disabled
✅ All files deleted after use
✅ Use VPN for setup
```

---

## 🎯 Feature Guide

### **Background Remover** (Offline ✅)
```
Image → Upload → Choose Model →
Clean PNG → Download
Time: 1-3 seconds
Models: 6 choices (isnet-general-use recommended)
```

### **Chat** (Offline ✅ / Hybrid 🔄)
```
Message → Local LLM (Ollama) → Response
Time: 1-5 seconds per message
Models: Mistral, Llama2, Tinyllama, more
Privacy: 100% local
```

### **Document Upload** (Offline ✅)
```
PDF/DOCX/TXT → Extract Text →
Classify Type → Store in DB →
Ready to Search
Time: <2 seconds
Search: <100ms
```

### **YouTube Summary** (Online 🌐)
```
URL → Fetch Captions from YouTube →
Local Summarization → Results
Time: 10-30 seconds
Requires: Internet
Privacy: YouTube sees IP
```

### **URL Summary** (Online 🌐)
```
URL → Fetch Website → Extract Text →
Local Summarization → Results
Time: 3-10 seconds
Requires: Internet
Privacy: Target website sees IP
```

### **Web Creator** (Offline ✅)
```
Description → AI Generates Code →
HTML/CSS/JS → Export/Preview
Time: 2-5 seconds
Export: Self-contained HTML
```

### **Multi-Agent Analysis** (Offline ✅)
```
Question → Orchestrator Routes to Agents →
Research Agent (search) + Analyst (analyze) +
Reviewer (quality check) → Combined Response
Time: 2-10 seconds
All Local: No external calls
```

---

## 🔐 Privacy Levels

### 🔒 Maximum Privacy (Offline Only)
- Everything on your machine
- No internet connection
- Zero data leaves device
- Best for: Sensitive documents

### 🔓 Good Privacy (Hybrid - Use Selectively)
- Core features offline
- Internet only for specific features
- Some IP exposure (YouTube, URLs)
- Best for: Balanced use

### 🌐 Regular Privacy (All Features Enabled)
- Full feature access
- Internet required for some features
- Standard privacy practices
- Best for: Maximum capability

---

## ⚡ Speed Expectations

| Operation | Time | Mode |
|-----------|------|------|
| Upload file | <1s | Offline |
| Search docs | <100ms | Offline |
| Chat reply | 1-5s | Offline |
| Summarize text | 5-10s | Offline |
| Remove BG | 1-3s | Offline |
| Summarize URL | 3-10s | Online |
| Summarize YT | 10-30s | Online |
| Download model | 2-5m | Online (once) |

---

## 📁 File Locations

```
YOUR MACHINE
│
├── Frontend (React)
│   └── localhost:5173
│
├── Backend (FastAPI)
│   ├── http://localhost:8000
│   └── Code: backend/ folder
│
├── Data (All Private)
│   ├── ./data/uploads/         ← Your documents
│   ├── ./data/chromadb/        ← Embeddings
│   ├── ./data/bg_uploads_adv/  ← BG images
│   ├── ./data/bg_outputs_adv/  ← BG results
│   ├── ./data/projects/        ← Web projects
│   └── ./data/sqlite.db        ← Chat, history
│
├── Models (Downloaded Once)
│   └── ~/.cache/rembg/         ← Cached BG models
│
└── Ollama (Local LLM)
    └── Running on localhost:11434
```

---

## 🎮 Dashboard Controls

In the web interface, you'll see:

```
┌─ SYSTEM STATUS ─┐
│ CPU: 45%        │
│ RAM: 8GB / 16GB │
│ Disk: 200GB /   │
└─────────────────┘

┌─ AI MODELS ─────┐
│ Ollama: ✅      │
│ Model:  Mistral │
│ Status: Ready   │
└─────────────────┘

┌─ MODE TOGGLE ───┐
│ ☐ Offline       │  ← Toggle here
│ ☑ Online        │  for online mode
└─────────────────┘

┌─ QUICK STATS ───┐
│ Chats: 42       │
│ Docs: 15        │
│ Projects: 3     │
└─────────────────┘
```

---

## 🔧 Switching Modes

### Enable Online Mode
1. Get API key (Groq.com or OpenAI)
2. Go to Dashboard → Settings
3. Toggle "Online Mode" ✓
4. Enter API key
5. System switches to cloud LLM

### Disable Online Mode
1. Dashboard → Settings
2. Toggle "Online Mode" ✗
3. Reverts to Ollama locally

---

## 📱 Browser Extension

Right-click anywhere on page:

```
Summarize this page
  ↳ Extracts text, summarizes locally
  
Remove image background
  ↳ Copy image URL, uses local models
  
AI Assistant
  ↳ Opens sidebar with chat
```

All operations use localhost:8000 → Completely local

---

## 🚨 Troubleshooting Quick Guide

| Issue | Offline | Online |
|-------|---------|--------|
| Chat not working | Start Ollama | Check internet |
| Slow chat | Use Tinyllama | Check API |
| Models missing | Download (once) | Check internet |
| BG remover failing | Check image format | Check internet |
| Can't access app | Check localhost:8000 | Check frontend |

### Quick Fixes
```
✅ Backend not running?
   → python run.py

✅ Ollama not connected?
   → ollama serve (new terminal)

✅ Frontend not loading?
   → npm run dev

✅ Models missing?
   → First-time download (3-5 min)

✅ Slow on old PC?
   → Use Tinyllama model
```

---

## 💾 Backup Your Data

```
Important folders to backup:
✅ ./data/chromadb/     ← Knowledge base
✅ ./data/uploads/      ← Your documents
✅ ./data/projects/     ← Web projects
✅ ./data/sqlite.db     ← Chat history

Backup frequency:
- Daily if actively used
- Weekly minimum
- Before major updates
```

---

## 🔐 Security Checklist

- [ ] Set strong JWT secret in .env
- [ ] Keep Ollama port blocked from internet (11434)
- [ ] Regular backups of ./data/ folder
- [ ] Delete temp files periodically
- [ ] Review stored chats monthly
- [ ] Update dependencies: `pip install -r requirements.txt --upgrade`
- [ ] Check for sensitive data in uploaded documents

---

## 📊 Performance Tips

### Make It Faster (Offline)
```
✅ Use smaller model (Tinyllama)
✅ Use "fast" mode in BG remover
✅ Limit chat history length
✅ Clean up old files
✅ Disable logging if not needed
```

### Improve Quality (Takes Longer)
```
✅ Use Mistral or Llama2 model
✅ Use "high" mode in BG remover
✅ Longer chat context
✅ More detailed instructions
```

### Make It More Private
```
✅ Disable internet
✅ Delete temp files after use
✅ Clear browser cache
✅ Regular backups to secure drive
```

---

## 🎯 Feature Matrix (Quick Reference)

```
                 Offline  Online  Hybrid  Speed    Privacy
Background         ✅       ❌      ✅    1-3s     🔒🔒🔒
Chat               ✅       ❌      ✅    1-5s     🔒🔒🔒
Documents          ✅       ❌      ✅    <1s      🔒🔒🔒
Knowledge Search   ✅       ❌      ✅    <100ms   🔒🔒🔒
Text Summary       ✅       ❌      ✅    5-10s    🔒🔒🔒
YouTube Summary    ❌       ✅      ✅    10-30s   🔒🌐⚠️
URL Summary        ❌       ✅      ✅    3-10s    🔒🌐⚠️
Web Creator        ✅       ❌      ✅    2-5s     🔒🔒🔒
Multi-Agent        ✅       ❌      ✅    2-10s    🔒🔒🔒
Dashboard          ✅       ❌      ✅    Real-time 🔒🔒🔒
Browser Ext        ✅       ❌      ✅    Instant  🔒🔒🔒
History            ✅       ❌      ✅    Instant  🔒🔒🔒
```

Legend: 🔒 = Secure/Offline,  ⚠️ = IP Exposed, 🌐 = Internet Needed

---

## 📞 Need Help?

1. Check Backend Connection: BACKEND_CONNECTION_FIX.md
2. Check Full Guide: DETAILED_OFFLINE_ONLINE_HYBRID_GUIDE.md
3. Check API Docs: http://localhost:8000/docs
4. Check Dashboard Health: In web interface
5. Check Logs: backend/ folder, look for errors

---

**Last Updated:** March 24, 2026  
**Version:** 2.0.0  
**Privacy Rating:** ⭐⭐⭐⭐⭐ (with offline mode)

