# 📊 AI Digital Brain - Interactive Flowcharts & Diagrams

This guide contains interactive flowchart visualizations of the system architecture and data flows.

---

## System Architecture Diagram

```mermaid
graph TB
    User["👤 User"]
    Frontend["🎨 Frontend (React)<br/>localhost:5173"]
    Extension["🔌 Browser Extension"]
    Backend["⚙️ FastAPI Backend<br/>localhost:8000"]
    Ollama["🤖 Ollama LLM<br/>localhost:11434"]
    ChromaDB["📚 ChromaDB<br/>Vector DB"]
    SQLite["💾 SQLite<br/>Local DB"]
    Rembg["🖼️ rembg<br/>BG Remover"]
    Internet["🌐 Internet<br/>(Optional)"]
    YouTube["▶️ YouTube API"]
    WebAPI["🌍 Web APIs"]
    
    User -->|Interact| Frontend
    User -->|Browser| Extension
    Frontend -->|HTTP| Backend
    Extension -->|HTTP| Backend
    Backend -->|Query| Ollama
    Ollama -->|Response| Backend
    Backend -->|Store/Search| ChromaDB
    Backend -->|Persist| SQLite
    Backend -->|Process| Rembg
    Backend -->|Optional| Internet
    Internet -->|Data| YouTube
    Internet -->|Data| WebAPI
    YouTube -->|Return| Backend
    WebAPI -->|Return| Backend
    
    style User fill:#FF6B6B
    style Frontend fill:#4ECDC4
    style Extension fill:#FFE66D
    style Backend fill:#95E1D3
    style Ollama fill:#A8DADC
    style ChromaDB fill:#F1FAEE
    style SQLite fill:#E8F4F8
    style Rembg fill:#FFD8D8
    style Internet fill:#FFA07A
    style YouTube fill:#FF0000,color:#FFF
    style WebAPI fill:#1E88E5,color:#FFF
```

---

## Feature Categories Flow

```mermaid
graph LR
    Start["🧠 AI Digital Brain"]
    
    Start -->|Offline| Offline["✅ OFFLINE<br/>15 Features"]
    Start -->|Online| Online["🌐 ONLINE<br/>5 Features"]
    Start -->|Hybrid| Hybrid["🔄 HYBRID<br/>6 Features"]
    
    Offline -->|Chat| O1["💬 Chat System"]
    Offline -->|Images| O2["🖼️ Background Remover"]
    Offline -->|Docs| O3["📄 Document Processing"]
    Offline -->|Search| O4["📚 Knowledge Base"]
    Offline -->|Text| O5["✂️ Summarization"]
    Offline -->|Create| O6["🎨 Web Creator"]
    Offline -->|Multi-Agent| O7["🤖 Multi-Agent System"]
    Offline -->|Monitor| O8["📊 Dashboard"]
    Offline -->|Extend| O9["🔌 Browser Extension"]
    
    Online -->|Video| On1["▶️ YouTube Summary"]
    Online -->|Web| On2["🌍 URL Summary"]
    Online -->|Search| On3["🔍 Web Research"]
    Online -->|Download| On4["📥 Model Download"]
    Online -->|Language| On5["🗣️ Translation"]
    
    Hybrid -->|Smart Chat| H1["💬 Chat<br/>Local/API"]
    Hybrid -->|Creator+| H2["🎨 Web Creator<br/>Enhanced"]
    Hybrid -->|Smart Summary| H3["✂️ Summary<br/>Combined"]
    Hybrid -->|Extensible| H4["🤖 Multi-Agent<br/>Extended"]
    
    style Offline fill:#90EE90
    style Online fill:#87CEEB
    style Hybrid fill:#DDA0DD
    style O1 fill:#E0FFE0
    style O2 fill:#E0FFE0
    style O3 fill:#E0FFE0
    style O4 fill:#E0FFE0
    style O5 fill:#E0FFE0
    style O6 fill:#E0FFE0
    style O7 fill:#E0FFE0
    style O8 fill:#E0FFE0
    style O9 fill:#E0FFE0
    style On1 fill:#E0F4FF
    style On2 fill:#E0F4FF
    style On3 fill:#E0F4FF
    style On4 fill:#E0F4FF
    style On5 fill:#E0F4FF
    style H1 fill:#F0E0FF
    style H2 fill:#F0E0FF
    style H3 fill:#F0E0FF
    style H4 fill:#F0E0FF
```

---

## User Request Decision Tree

```mermaid
graph TD
    A["What do you want to do?"]
    
    A -->|Analyze text| B["Summarize"]
    A -->|Remove background| C["Background Remover"]
    A -->|Chat/Ask| D["Chat System"]
    A -->|Upload document| E["Document Processing"]
    A -->|Create website| F["Web Creator"]
    A -->|Research task| G["Web Research"]
    A -->|Fetch video| H["YouTube Summary"]
    A -->|Fetch website| I["URL Summary"]
    
    B -->|Connected?| B1{"Internet<br/>Available?"}
    B1 -->|No| B2["✅ Offline<br/>Local Summarize"]
    B1 -->|Yes| B3["✅ Hybrid<br/>Local+Enhanced"]
    
    C -->|Check Network| C1{"Internet?"}
    C1 -->|No| C2["✅ Offline<br/>Fast/Balanced/High"]
    C1 -->|Yes| C3["✅ Hybrid<br/>Download Models"]
    
    D -->|Mode| D1{"Offline<br/>Mode?"}
    D1 -->|Yes| D2["✅ Offline<br/>Ollama/Mistral"]
    D1 -->|No| D3["✅ Hybrid<br/>Groq/OpenAI"]
    
    E -->|Files| E1["✅ Always Offline<br/>Local Storage"]
    
    F -->|Generate| F1["✅ Offline<br/>Basic HTML/CSS"]
    F -->|Assets| F2["⚠️ Needs Internet<br/>Templates/CDN"]
    
    G -->|Search| G1["🌐 REQUIRES<br/>INTERNET"]
    
    H -->|Download| H1["🌐 REQUIRES<br/>INTERNET"]
    
    I -->|Fetch| I1["🌐 REQUIRES<br/>INTERNET"]
    
    style A fill:#FFE66D
    style B fill:#87CEEB
    style C fill:#87CEEB
    style D fill:#87CEEB
    style E fill:#87CEEB
    style F fill:#87CEEB
    style G fill:#87CEEB
    style H fill:#87CEEB
    style I fill:#87CEEB
    style B2 fill:#90EE90
    style B3 fill:#DDA0DD
    style C2 fill:#90EE90
    style C3 fill:#DDA0DD
    style D2 fill:#90EE90
    style D3 fill:#DDA0DD
    style E1 fill:#90EE90
    style F1 fill:#90EE90
    style F2 fill:#FFB6C6
    style G1 fill:#FFB6C6
    style H1 fill:#FFB6C6
    style I1 fill:#FFB6C6
```

---

## Chat System - Offline vs Online

```mermaid
graph TB
    subgraph Offline["⚙️ OFFLINE MODE"]
        O1["User Input"]
        O2["FastAPI Backend"]
        O3["Ollama LLM<br/>localhost:11434"]
        O4["Response Generated<br/>Locally"]
        O1 -->|HTTP| O2
        O2 -->|Query| O3
        O3 -->|Response| O2
        O2 -->|Return| O4
    end
    
    subgraph Online["🌐 ONLINE MODE"]
        On1["User Input"]
        On2["FastAPI Backend"]
        On3["Groq/OpenAI API"]
        On4["Response from Cloud"]
        On1 -->|HTTP| On2
        On2 -->|HTTP| On3
        On3 -->|Response| On2
        On2 -->|Return| On4
    end
    
    style Offline fill:#E0FFE0
    style Online fill:#E0F4FF
    style O1 fill:#FFFFFF
    style O2 fill:#FFFFFF
    style O3 fill:#FFFFFF
    style O4 fill:#90EE90
    style On1 fill:#FFFFFF
    style On2 fill:#FFFFFF
    style On3 fill:#FFFFFF
    style On4 fill:#87CEEB
```

---

## Background Remover Pipeline

```mermaid
graph LR
    Start["📤 Upload Image"]
    Check{"Model Downloaded?"}
    Download["⬇️ Download<br/>~170MB<br/>3-5 min"]
    Cache["💾 Cache<br/>Local Device"]
    Process["⚙️ Process<br/>ONNX Neural Net"]
    Quality{"Quality<br/>Setting?"}
    Fast["⚡ Fast<br/>1-2s"]
    Balanced["⚖️ Balanced<br/>2-3s"]
    High["🎯 High<br/>3-5s"]
    Alpha["🔄 Alpha Matting<br/>Edge Refinement"]
    Output["🎨 Output PNG<br/>Transparent BG"]
    
    Start --> Check
    Check -->|No| Download
    Check -->|Yes| Process
    Download --> Cache
    Cache --> Process
    Process --> Quality
    Quality -->|1| Fast
    Quality -->|2| Balanced
    Quality -->|3| High
    Fast --> Alpha
    Balanced --> Alpha
    High --> Alpha
    Alpha --> Output
    
    style Start fill:#FFE66D
    style Download fill:#FFA07A
    style Cache fill:#90EE90
    style Process fill:#95E1D3
    style Quality fill:#FFE66D
    style Fast fill:#F0F8FF
    style Balanced fill:#F0F8FF
    style High fill:#F0F8FF
    style Alpha fill:#E8DAEF
    style Output fill:#90EE90
```

---

## Document Processing Pipeline

```mermaid
graph LR
    Upload["📤 Upload File"]
    Type{"File Type?"}
    PDF["📕 PDF"]
    DOCX["📗 DOCX"]
    TXT["📄 TXT"]
    Extract["🔍 Extract Text"]
    Classify["🏷️ Auto-Classify"]
    Store["💾 Store Locally"]
    Index["🔎 Index in ChromaDB"]
    Search["🔍 Semantic Search"]
    Result["✅ Ready to Query"]
    
    Upload --> Type
    Type -->|PDF| PDF
    Type -->|DOCX| DOCX
    Type -->|TXT| TXT
    PDF --> Extract
    DOCX --> Extract
    TXT --> Extract
    Extract --> Classify
    Classify --> Store
    Store --> Index
    Index --> Search
    Search --> Result
    
    style Upload fill:#FFE66D
    style PDF fill:#E8F4F8
    style DOCX fill:#E8F4F8
    style TXT fill:#E8F4F8
    style Extract fill:#95E1D3
    style Classify fill:#A8DADC
    style Store fill:#90EE90
    style Index fill:#F1FAEE
    style Search fill:#FFD8D8
    style Result fill:#90EE90
```

---

## Knowledge Base - Search Flow

```mermaid
graph TB
    Query["❓ User Query"]
    Embed["🧮 Embed Query"]
    Search["🔎 Search ChromaDB<br/><100ms"]
    Rank["📊 Rank Results<br/>by Relevance"]
    Select["✅ Select Top K"]
    Context["📝 Build Context"]
    LLM["🤖 Send to Ollama"]
    Generate["✍️ Generate Answer<br/>5-10s"]
    Output["✅ Output to User"]
    
    Query --> Embed
    Embed --> Search
    Search --> Rank
    Rank --> Select
    Select --> Context
    Context --> LLM
    LLM --> Generate
    Generate --> Output
    
    style Query fill:#FFE66D
    style Embed fill:#95E1D3
    style Search fill:#A8DADC
    style Rank fill:#DDA0DD
    style Select fill:#DDA0DD
    style Context fill:#F1FAEE
    style LLM fill:#A8DADC
    style Generate fill:#E0FFE0
    style Output fill:#90EE90
```

---

## Privacy Levels - Comparison

```mermaid
graph TB
    All["🔒 Privacy Levels"]
    
    All -->|Level 1| Max["🔐 MAXIMUM<br/>Offline Mode"]
    All -->|Level 2| Good["✅ Good<br/>Hybrid Mode<br/>Optional Online"]
    All -->|Level 3| Limited["⚠️ Limited<br/>Full Online Mode"]
    All -->|Level 4| Cloud["❌ Minimal<br/>Cloud Dependent"]
    
    Max -->|Features| M1["15 Offline<br/>Full Capability"]
    Max -->|Data| M2["100% Local<br/>No internet"]
    Max -->|Privacy| M3["🔒🔒🔒🔒🔒<br/>Maximum"]
    
    Good -->|Features| G1["15 Offline<br/>+ 6 Hybrid"]
    Good -->|Data| G2["~95% Local<br/>Optional internet"]
    Good -->|Privacy| G3["🔒🔒🔒⚠️⚠️<br/>Good"]
    
    Limited -->|Features| L1["All 26<br/>Full System"]
    Limited -->|Data| L2["~70% Local<br/>Online fallback"]
    Limited -->|Privacy| L3["🔒⚠️⚠️⚠️⚠️<br/>Limited"]
    
    Cloud -->|Features| C1["All 26<br/>Cloud Native"]
    Cloud -->|Data| C2["Cloud<br/>Dependent"]
    Cloud -->|Privacy| C3["⚠️⚠️⚠️⚠️⚠️<br/>Minimal"]
    
    style Max fill:#90EE90
    style Good fill:#DDA0DD
    style Limited fill:#FFB6C6
    style Cloud fill:#FF6B6B
    style M1 fill:#E0FFE0
    style M2 fill:#E0FFE0
    style M3 fill:#E0FFE0
    style G1 fill:#F0E0FF
    style G2 fill:#F0E0FF
    style G3 fill:#F0E0FF
    style L1 fill:#FFE4E1
    style L2 fill:#FFE4E1
    style L3 fill:#FFE4E1
    style C1 fill:#FFB6C6
    style C2 fill:#FFB6C6
    style C3 fill:#FFB6C6
```

---

## Setup & Installation Flow

```mermaid
graph TD
    Start["🚀 Installation Start"]
    
    Check1{"Ollama<br/>Installed?"}
    Install1["⬇️ Download Ollama<br/>ollama.ai"]
    Run1["▶️ ollama serve"]
    
    Check2{"Dependencies<br/>Installed?"}
    Install2["⬇️ pip install -r<br/>requirements.txt"]
    
    Check3{"Node Modules<br/>Installed?"}
    Install3["⬇️ npm install<br/>frontend"]
    
    Backend["🟢 Start Backend<br/>python run.py"]
    Frontend["🟢 Start Frontend<br/>npm run dev"]
    
    Done["✅ Ready to Use<br/>localhost:5173"]
    
    Start --> Check1
    Check1 -->|No| Install1
    Check1 -->|Yes| Check2
    Install1 --> Run1
    Run1 --> Check2
    
    Check2 -->|No| Install2
    Check2 -->|Yes| Check3
    Install2 --> Check3
    
    Check3 -->|No| Install3
    Check3 -->|Yes| Backend
    Install3 --> Backend
    
    Backend --> Frontend
    Frontend --> Done
    
    style Start fill:#FFE66D
    style Check1 fill:#FFE66D
    style Check2 fill:#FFE66D
    style Check3 fill:#FFE66D
    style Install1 fill:#FFA07A
    style Install2 fill:#FFA07A
    style Install3 fill:#FFA07A
    style Run1 fill:#87CEEB
    style Backend fill:#90EE90
    style Frontend fill:#90EE90
    style Done fill:#90EE90
```

---

## Multi-Agent System - Logic Flow

```mermaid
graph TB
    Query["❓ User Query"]
    Orch["🎯 Orchestrator Agent"]
    
    Orch -->|Analyze| Analyze{"What type<br/>of query?"}
    
    Analyze -->|Research| RA["🔬 Research Agent<br/>Find information"]
    Analyze -->|Web Data| WA["🕷️ Web Agent<br/>Search & scrape"]
    Analyze -->|Analysis| AA["📊 Analyst Agent<br/>Extract insights"]
    Analyze -->|Review| RV["✅ Reviewer Agent<br/>Quality check"]
    
    RA --> ProcessRA["Process Results"]
    WA --> ProcessWA["Process Results"]
    AA --> ProcessAA["Process Results"]
    RV --> ProcessRV["Final Review"]
    
    ProcessRA --> Combine["🔗 Combine Responses"]
    ProcessWA --> Combine
    ProcessAA --> Combine
    ProcessRV --> Combine
    
    Combine --> Final["✅ Final Response<br/>to User"]
    
    style Query fill:#FFE66D
    style Orch fill:#4ECDC4
    style Analyze fill:#FFE66D
    style RA fill:#DDA0DD
    style WA fill:#DDA0DD
    style AA fill:#DDA0DD
    style RV fill:#DDA0DD
    style ProcessRA fill:#F0E0FF
    style ProcessWA fill:#F0E0FF
    style ProcessAA fill:#F0E0FF
    style ProcessRV fill:#F0E0FF
    style Combine fill:#A8DADC
    style Final fill:#90EE90
```

---

## YouTube Summary - Data Flow

```mermaid
graph LR
    Start["🎬 YouTube URL"]
    Fetch["⬇️ Download<br/>Captions/Metadata"]
    Extract["🔍 Extract Text"]
    Local["📝 Prepare<br/>for LLM"]
    Ollama["🤖 Ollama<br/>Summarize"]
    Summary["✅ Summary<br/>Generated"]
    
    Start -->|Via yt-dlp<br/>Requires Internet| Fetch
    Fetch -->|Local Process| Extract
    Extract -->|Local Process| Local
    Local -->|100% Offline| Ollama
    Ollama -->|Return| Summary
    
    style Start fill:#FFE66D
    style Fetch fill:#FFA07A
    style Extract fill:#95E1D3
    style Local fill:#F1FAEE
    style Ollama fill:#A8DADC
    style Summary fill:#90EE90
```

---

## URL Summary - Data Flow

```mermaid
graph LR
    Start["🌍 Website URL"]
    Fetch["⬇️ Download<br/>HTML/Content"]
    Clean["🧹 Extract Text<br/>Remove Boilerplate"]
    Process["📝 Prepare<br/>for LLM"]
    Ollama["🤖 Ollama<br/>Summarize"]
    Summary["✅ Summary<br/>Generated"]
    
    Start -->|Via BeautifulSoup<br/>Requires Internet| Fetch
    Fetch -->|Local Process| Clean
    Clean -->|Local Process| Process
    Process -->|100% Offline| Ollama
    Ollama -->|Return| Summary
    
    style Start fill:#FFE66D
    style Fetch fill:#FFA07A
    style Clean fill:#95E1D3
    style Process fill:#F1FAEE
    style Ollama fill:#A8DADC
    style Summary fill:#90EE90
```

---

## Data Storage Architecture

```mermaid
graph TB
    Root["./data/"]
    
    Root -->|Documents| Docs["uploads/<br/>PDF, DOCX, TXT"]
    Root -->|Vector DB| VecDB["chromadb/<br/>Embeddings<br/>Semantic Search"]
    Root -->|Images| Imgs["bg_uploads/<br/>bg_outputs/<br/>Processed Images"]
    Root -->|Database| DB["sqlite.db<br/>Chats, Metadata"]
    Root -->|Generated| Gen["generated/<br/>HTML/CSS/JS<br/>Created Projects"]
    
    Docs -->|✅ Offline| Local1["🔒 Private<br/>100% Local"]
    VecDB -->|✅ Offline| Local2["🔒 Private<br/>100% Local"]
    Imgs -->|✅ Offline| Local3["🔒 Private<br/>100% Local"]
    DB -->|✅ Offline| Local4["🔒 Private<br/>100% Local"]
    Gen -->|✅ Offline| Local5["🔒 Private<br/>100% Local"]
    
    style Root fill:#FFE66D
    style Docs fill:#E8F4F8
    style VecDB fill:#E8F4F8
    style Imgs fill:#E8F4F8
    style DB fill:#E8F4F8
    style Gen fill:#E8F4F8
    style Local1 fill:#90EE90
    style Local2 fill:#90EE90
    style Local3 fill:#90EE90
    style Local4 fill:#90EE90
    style Local5 fill:#90EE90
```

---

## Performance Timeline - Single Requests

```mermaid
graph LR
    Start["0ms"]
    C1["Chat<br/>Request<br/>1-5s"]
    BG["Background<br/>Remover<br/>1-3s"]
    SUM["Summarize<br/>Text<br/>5-10s"]
    SEARCH["Search Docs<br/>100ms"]
    YT["YouTube<br/>Summary<br/>10-30s"]
    URL["URL Summary<br/>3-10s"]
    
    Start --> SEARCH
    Start --> C1
    Start --> BG
    Start --> SUM
    Start --> YT
    Start --> URL
    
    style Start fill:#FFE66D
    style C1 fill:#E0FFE0
    style BG fill:#E0FFE0
    style SUM fill:#E0FFE0
    style SEARCH fill:#E0FFE0
    style YT fill:#FFA07A
    style URL fill:#FFA07A
```

---

## Mode Switching Logic

```mermaid
graph TB
    Boot["🚀 System Boot"]
    Check{"Check<br/>app_state.py<br/>mode=?"}
    
    Check -->|"offline"| Offline["✅ OFFLINE MODE"]
    Check -->|"online"| Online["🌐 ONLINE MODE"]
    
    Offline -->|Initialize| O1["Load Ollama<br/>localhost:11434"]
    Offline -->|Initialize| O2["Load ChromaDB<br/>Vector search"]
    Offline -->|Initialize| O3["Load SQLite<br/>Local Database"]
    
    Online -->|Initialize| On1["Load API Keys<br/>.env"]
    Online -->|Initialize| On2["Connect Groq/OpenAI<br/>Cloud API"]
    Online -->|Initialize| On3["Enable Web Services<br/>YouTube, URLs"]
    
    O1 --> Offline_Ready["✅ Ready"]
    O2 --> Offline_Ready
    O3 --> Offline_Ready
    
    On1 --> Online_Ready["✅ Ready"]
    On2 --> Online_Ready
    On3 --> Online_Ready
    
    Offline_Ready -->|Service| Service1["15 Features"]
    Online_Ready -->|Service| Service2["21+ Features"]
    
    style Boot fill:#FFE66D
    style Check fill:#FFE66D
    style Offline fill:#90EE90
    style Online fill:#87CEEB
    style O1 fill:#E0FFE0
    style O2 fill:#E0FFE0
    style O3 fill:#E0FFE0
    style On1 fill:#E0F4FF
    style On2 fill:#E0F4FF
    style On3 fill:#E0F4FF
    style Offline_Ready fill:#90EE90
    style Online_Ready fill:#87CEEB
    style Service1 fill:#90EE90
    style Service2 fill:#87CEEB
```

---

## Browser Extension - Integration

```mermaid
graph TB
    Browser["🌐 Browser"]
    Tab["Current Tab"]
    Menu["Right-click Menu"]
    
    Browser -->|Tab Active| Tab
    Tab -->|Right-click| Menu
    
    Menu -->|Summarize| S1["Send Content<br/>to Backend"]
    Menu -->|Remove BG| S2["Extract Image<br/>Process"]
    Menu -->|Quick Chat| S3["Open Popup<br/>Chat Interface"]
    
    S1 --> Backend1["Backend<br/>localhost:8000"]
    S2 --> Backend1
    S3 --> Backend1
    
    Backend1 -->|Process| P1["Summarize"]
    Backend1 -->|Process| P2["Remove Background"]
    Backend1 -->|Process| P3["Chat Response"]
    
    P1 -->|Return| Result["✅ Result<br/>to Extension"]
    P2 -->|Return| Result
    P3 -->|Return| Result
    
    Result -->|Display| Browser
    
    style Browser fill:#FFE66D
    style Tab fill:#FFE66D
    style Menu fill:#FFE66D
    style S1 fill:#DDA0DD
    style S2 fill:#DDA0DD
    style S3 fill:#DDA0DD
    style Backend1 fill:#95E1D3
    style P1 fill:#A8DADC
    style P2 fill:#A8DADC
    style P3 fill:#A8DADC
    style Result fill:#90EE90
```

---

## Error Handling & Recovery

```mermaid
graph TB
    Error["❌ Error Detected"]
    Type{"Error Type?"}
    
    Type -->|Network| Net["🌐 Network Error"]
    Type -->|Model| Model["🤖 Model Error"]
    Type -->|Storage| Store["💾 Storage Error"]
    Type -->|API| API["📡 API Error"]
    
    Net -->|Offline Mode| NetFix["✅ Continue Offline<br/>No internet needed"]
    Net -->|Online Mode| NetFix2["⚠️ Switch to Fallback"]
    
    Model -->|Not Downloaded| ModelFix["⬇️ Download<br/>Retry"]
    Model -->|Corrupted| ModelFix2["🔄 Reload<br/>Cache"]
    
    Store -->|Full| StoreFix["🧹 Cleanup<br/>Old Files"]
    Store -->|Corrupted| StoreFix2["🔧 Repair<br/>Database"]
    
    API -->|Timeout| APIFix["🔄 Retry<br/>Exponential backoff"]
    API -->|Invalid| APIFix2["🔧 Check<br/>API Key"]
    
    NetFix -.->|Resolved| Done["✅ Recovery<br/>Complete"]
    NetFix2 -.->|Resolved| Done
    ModelFix -.->|Resolved| Done
    ModelFix2 -.->|Resolved| Done
    StoreFix -.->|Resolved| Done
    StoreFix2 -.->|Resolved| Done
    APIFix -.->|Resolved| Done
    APIFix2 -.->|Resolved| Done
    
    style Error fill:#FF6B6B
    style Type fill:#FFE66D
    style Net fill:#FFA07A
    style Model fill:#FFA07A
    style Store fill:#FFA07A
    style API fill:#FFA07A
    style NetFix fill:#FFD8D8
    style NetFix2 fill:#FFD8D8
    style ModelFix fill:#FFD8D8
    style ModelFix2 fill:#FFD8D8
    style StoreFix fill:#FFD8D8
    style StoreFix2 fill:#FFD8D8
    style APIFix fill:#FFD8D8
    style APIFix2 fill:#FFD8D8
    style Done fill:#90EE90
```

---

**These flowcharts provide visual representations of:**
- System architecture
- Data flows
- Feature organization
- Privacy levels
- Installation process
- Multi-agent logic
- Mode switching
- Integration points

**To view these diagrams:**
1. Open this file in VS Code with Markdown Preview
2. Install "Markdown Preview Mermaid Support" extension
3. View diagrams in real-time

