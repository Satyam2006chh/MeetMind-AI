⭐ MeetMind AI — Your Smart AI Meeting Intelligence Hub

Upload any Zoom meeting recording → get instant summaries, tasks, decisions, risks, and a full AI chatbot that answers questions about the meeting.


🔥 Overview
MeetMind AI is a modern, AI-powered meeting assistant that transforms any meeting recording into structured, actionable insights.
Simply upload your Zoom meeting recording, and the system automatically:

🎙️ Transcribes the meeting using Whisper AI
📄 Generates a professional summary
✅ Extracts tasks, owners, and deadlines
🎯 Identifies key decisions made
⚠️ Analyzes risks in those decisions
✉️ Creates follow-up email drafts
🤖 Builds an AI chatbot to answer questions about the meeting


🎯 Key Features
⭐ 1. Upload Meeting Recording

Supported formats: .mp4, .wav, .mp3, .m4a
Automatically stores and processes files

⭐ 2. Whisper-Based Transcription

High-quality speech-to-text conversion
Handles long meetings and multiple speakers
Optional timestamps

⭐ 3. AI Summary Generator

Clean, structured summary
Bullet-point breakdown of meeting highlights
Easy to read and share

⭐ 4. Action Items Extraction
Automatically identifies:

Task description
Assigned owner
Deadlines
Status (optional)

⭐ 5. Decision Extraction

Detects all key decisions made during the meeting
Saves them into the database for tracking

⭐ 6. Decision Risk Analyzer
AI evaluates each decision and checks for:

Missing information
Budget concerns
Technical risks
Conflicts with other decisions
Feasibility issues
Dependencies

Risk Levels: 🟢 Low | 🟡 Medium | 🔴 High
⭐ 7. Follow-Up Email Generator
Generates a polished email including:

Meeting summary
Key decisions
Action items with owners
Next steps

You can copy, edit, and send directly!
⭐ 8. Ask-Your-Meeting Chatbot
Powered by semantic search, ask questions like:

"What tasks were assigned to Riya?"
"What was the deadline for the AWS migration?"
"Summarize only the marketing discussion."

Technology: Chroma/FAISS vector store + LangChain RetrievalQA
⭐ 9. Meeting Dashboard
Comprehensive view displaying:

📊 Summary
✅ Action items
🎯 Decisions
⚠️ Risk analysis
✉️ Follow-up email draft
💬 Chat interface
⬇️ Download options


🧠 Architecture
MeetMind AI follows a clean, scalable, and production-ready architecture.
High-Level Flow
Upload File → Whisper Transcription → LLM Pipelines → JSON Structured Output → 
Embeddings → Vector Store → Dashboard + Chatbot
🔷 Core Components
ComponentPurposeFlask BackendHandles upload, processing, API responses, routingWhisper TranscriptionConverts speech → textLangChain PipelinesSummary, Task extraction, Decision extraction, Risk analysis, Email generationVector StoreChroma/FAISS for semantic search in chatbotFrontendBootstrap + JavaScript for UI, upload, chatDatabaseSQLite (dev) / PostgreSQL (prod) for storing meeting data

🧱 Tech Stack
Backend

Flask — REST APIs & server logic
Python — Core language
LangChain — LLM orchestration
Whisper — AI transcription
Chroma / FAISS — Vector database
Gunicorn — Production WSGI server

Frontend

HTML5 / Bootstrap — Clean, responsive UI
JavaScript — File uploads, chat interface

Database

SQLite — Local development
PostgreSQL — Production (Render deployment)

Deployment

Render.com — Direct GitHub deployment (no Docker required)


📁 Folder Structure
ai_meeting_hub/
├── run.py                  # Flask entry point
├── requirements.txt        # Python dependencies
├── README.md               # Project documentation
│
├── app/
│   ├── __init__.py        # create_app(), DB setup
│   ├── routes.py          # API routes (upload, dashboard, chat)
│   ├── models.py          # SQLAlchemy models
│   ├── chains.py          # LangChain pipelines (summary, actions, risks, email)
│   ├── transcription.py   # Whisper helper
│   ├── vectorstore.py     # Embeddings & vector DB logic
│   ├── utils.py           # Formatters, helpers
│   │
│   ├── templates/
│   │   ├── base.html      # Base template
│   │   ├── upload.html    # Upload interface
│   │   ├── dashboard.html # Results dashboard
│   │   └── chat.html      # Chatbot interface
│   │
│   └── static/
│       ├── css/           # Stylesheets
│       └── js/            # JavaScript files
│
└── uploads/               # Uploaded meeting files

⚙️ How It Works (Step-By-Step)
1️⃣ User uploads meeting recording
File is stored securely under /uploads
2️⃣ Whisper transcribes the audio
Outputs:

Full transcript
Optional timestamps

3️⃣ LangChain processes the transcript
Runs multiple AI chains:

Summary Chain
Action Items Chain
Decision Chain
Decision Risk Analyzer Chain
Email Generator Chain

4️⃣ Vector Store created for Chatbot
Transcript → chunks → embeddings → stored in Chroma/FAISS
Used to answer user queries with semantic search
5️⃣ Dashboard displays results
User sees:

📄 Summary
✅ Tasks
🎯 Decisions
⚠️ Risks
✉️ Email
💬 Chatbot interface

6️⃣ User can ask questions
Retrieve relevant transcript chunks → LLM → contextual answer

🚀 Deployment (Render.com)
Step 1: Push project to GitHub
Ensure you include:

requirements.txt
run.py
All project files

Step 2: Create Web Service on Render

Create → Web Service
Connect GitHub repository
Build command:

bash  pip install -r requirements.txt

Start command:

bash  gunicorn run:app
Step 3: Add Environment Variables
OPENAI_API_KEY=your_openai_api_key
SECRET_KEY=your_flask_secret_key
DATABASE_URL=postgresql://... (Render auto-creates)

🧪 Future Enhancements

🎤 Real-time transcription
🤝 Zoom SDK bot joining live meetings
👥 Multi-speaker diarization
🌍 Multi-language support
🏢 Admin dashboard for organizations
📊 Analytics & insights across multiple meetings


🤝 Contributors
Satyam — Developer
AI Pair Programmer — Designed architecture & AI pipeline logic

📄 License
MIT License
Free to use, modify, and build upon.
