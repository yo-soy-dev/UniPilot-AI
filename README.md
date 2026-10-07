# 🎓 UniPilot AI — Agentic College Assistant

UniPilot AI is an **Agentic AI-powered College Assistant** built with **LangGraph, LangChain, Groq, RAG, FAISS, Hugging Face Embeddings, and Streamlit**.

It intelligently analyzes a student's query and decides whether to retrieve information from official college documents or answer using general knowledge.

## 🚀 Features

- 🤖 Agentic AI workflow using LangGraph
- 🧠 Intelligent query classification
- 📘 Academic information retrieval using RAG
- 💰 Fee-related information retrieval using RAG
- 💬 General questions answered using LLM knowledge
- 🎓 Personalized responses based on student's programme
- 🔎 FAISS vector search
- 📄 PDF document processing
- ⚡ Groq LLM for fast responses
- 🖥️ Interactive Streamlit chat interface
- 🗂️ Separate knowledge sources for academics and fees
- 🧹 Clear chat functionality
- 🏷️ Displays the detected query category

## 🧠 How It Works

UniPilot AI uses an agentic workflow to route every student query.

```text
                    User Query
                        │
                        ▼
                ┌───────────────┐
                │   Classifier  │
                └───────┬───────┘
                        │
            ┌───────────┼───────────┐
            ▼           ▼           ▼
       Academic       Fee        General
           │           │           │
           ▼           ▼           ▼
      Academic RAG   Fee RAG    Direct LLM
           │           │           │
           └───────────┼───────────┘
                       ▼
                Response Generator
                       │
                       ▼
                  Final Answer
```

### Query Routing

| Query Type | Source |
|------------|--------|
| Academic | Academic Handbook PDF |
| Fee | Fee Structure PDF |
| General | LLM General Knowledge |

## 🛠️ Tech Stack

### AI / LLM

- Python
- LangGraph
- LangChain
- Groq
- `openai/gpt-oss-120b`

### RAG

- PyPDF
- Recursive Character Text Splitter
- Hugging Face Embeddings
- FAISS

### Frontend

- Streamlit

### Environment

- Python Virtual Environment
- python-dotenv

## 📁 Project Structure

```text
LANGGRAPH/
│
├── .venv/
├── .env
├── .gitignore
│
├── academics_handbook.pdf
├── fee_structure.pdf
│
├── app.py
├── conditional_RAG.py
├── humanintheloop.py
├── iterative_tools.py
├── parallel_reducers.py
├── sequential_base.py
├── states.py
│
├── requirement.txt
└── README.md
```

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yo-soy-dev/unipilot-ai.git
cd unipilot-ai
```

### 2. Create Virtual Environment

Using `uv`:

```bash
uv venv
```

Activate it on Windows:

```powershell
.venv\Scripts\activate
```

### 3. Install Dependencies

```bash
uv pip install -r requirement.txt
```

Or using pip:

```bash
pip install -r requirement.txt
```

## 🔐 Environment Variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
```

Do **not** commit your `.env` file to GitHub.

## 📄 Knowledge Base

UniPilot AI currently uses two PDF documents:

```text
academics_handbook.pdf
fee_structure.pdf
```

The documents are:

1. Loaded using `PyPDFLoader`
2. Split into smaller chunks
3. Converted into embeddings
4. Stored in FAISS
5. Retrieved based on the student's query

## ▶️ Run the Application

Start the Streamlit application:

```bash
streamlit run app.py
```

The application will open in your browser.

## 🎓 Supported Programmes

Currently, students can select:

- BCA
- BBA
- B.Com (H)

The selected programme is used to personalize AI responses.

## 🔄 Example

### Student Query

```text
What are the attendance requirements for my course?
```

### Agent Workflow

```text
Student Query
     ↓
Classifier
     ↓
Academic
     ↓
Academic Handbook RAG
     ↓
Relevant Document Chunks
     ↓
Groq LLM
     ↓
Personalized Response
```

## 🧩 LangGraph Experiments

This repository also contains examples demonstrating different LangGraph concepts.

### `sequential_base.py`

Demonstrates sequential LangGraph workflow.

```text
Input → Scriptwriter → Translator → Output
```

### `parallel_reducers.py`

Demonstrates parallel execution and reducers.

```text
              ┌─ Copyright Analysis
Input ────────┼─ Cultural Analysis
              └─ Toxicity Analysis
                       ↓
                    Reducer
```

### `conditional_RAG.py`

Demonstrates conditional routing with RAG.

```text
Query
  ↓
Classifier
  ↓
Academic / Fee / General
```

### `humanintheloop.py`

Demonstrates a human-in-the-loop workflow.

### `iterative_tools.py`

Demonstrates iterative tool-based agent workflows.

## 🔑 Key Concepts

This project demonstrates:

- LangGraph StateGraph
- Nodes
- Edges
- Conditional Edges
- State Management
- Reducers
- Agentic Routing
- Retrieval-Augmented Generation (RAG)
- Vector Search
- Embeddings
- LLM Integration
- Human-in-the-Loop
- Tool Calling
- Streamlit
- Session State

## 🚧 Future Improvements

- 🔐 User authentication
- 💾 Persistent conversation history
- 📚 More college knowledge sources
- 🧑‍💼 Admin dashboard for document management
- 🔍 Better document citations
- 🧠 More specialized AI agents
- 🗃️ Database-backed student profiles
- 📊 Student analytics
- 🌐 Cloud deployment
- 🎤 Voice-based interaction

## 👨‍💻 Author

**Devansh Kumar Tiwari**

Full-Stack Developer | AI & Agentic AI Enthusiast

## ⭐ Project

If you find this project useful, consider giving it a ⭐ on GitHub.
