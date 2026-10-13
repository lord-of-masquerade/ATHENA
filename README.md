# ATHENA — Personal AI

**A private personal AI assistant that remembers, acts, and respects your control.**

ATHENA is a personal AI assistant designed to help users manage everyday workflows through persistent memory, reusable skills, and controlled access to tools. Powered by an NVIDIA open model and built with privacy and security in mind, ATHENA aims to make AI assistance more personal, useful, and trustworthy.

> Built for the Nebius × NVIDIA Global AI Hackathon — Personal AI Track.

## ✨ Vision

Most AI assistants are useful during a conversation but may not retain relevant context across sessions or give users enough control over how tools are used.

ATHENA aims to address this by combining:

- **Persistent Memory:** Store and retrieve user-approved information across sessions.
- **AI Agent:** Interpret requests, reason through tasks, and coordinate available tools.
- **Reusable Skills:** Organize repeatable workflows into modular capabilities.
- **Controlled Tool Access:** Restrict sensitive actions through explicit permissions.
- **Activity Logging:** Record important actions so users can understand what the assistant did.
- **Privacy by Design:** Keep user data under user control and avoid unnecessary data collection.

## 🚀 Planned Features

- Natural-language chat interface
- Long-term memory using SQLite
- Memory retrieval and management
- Reusable task skills
- Document and text analysis
- Task planning and summarization
- Permission checks before sensitive actions
- Activity and audit logs
- NVIDIA open-model integration
- Nebius infrastructure integration
- Optional speech input and voice responses

*Features will be marked complete only after they are implemented and tested.*

## 🧠 Technology Stack

| Component | Technology |
|---|---|
| Language | Python |
| AI model | NVIDIA Nemotron or another eligible NVIDIA open model |
| Model inference | Compatible Nebius or NVIDIA endpoint |
| Memory | SQLite |
| Interface | Streamlit |
| Agent logic | Python |
| Security | Permission checks, tool allowlists, audit logging |
| Version control | Git and GitHub |

The final model, inference provider, and deployment configuration will depend on availability, hackathon requirements, and resource limits.

## 🏗️ Architecture

```text
                  USER
                   |
                   v
          ATHENA Chat Interface
                (Streamlit)
                   |
                   v
             Agent Controller
                   |
          +--------+--------+
          |        |        |
          v        v        v
       Memory    Skills   Permissions
       (SQLite)  Registry  & Approval
          |        |        |
          +--------+--------+
                   |
                   v
              Model Client
                   |
                   v
       NVIDIA Open Model / Endpoint
                   |
                   v
          Approved Tool Execution
                   |
                   v
          Activity / Audit Logs
```

## 📁 Project Structure

```text
ATHENA-Personal-AI/
├── app.py
├── requirements.txt
├── .env.example
├── .gitignore
├── README.md
├── LICENSE
│
├── core/
│   ├── __init__.py
│   ├── agent.py
│   ├── model_client.py
│   └── config.py
│
├── memory/
│   ├── __init__.py
│   └── store.py
│
├── skills/
│   ├── __init__.py
│   ├── registry.py
│   ├── summarizer.py
│   └── task_planner.py
│
├── tools/
│   ├── __init__.py
│   └── document_tools.py
│
├── security/
│   ├── __init__.py
│   ├── permissions.py
│   └── audit.py
│
├── data/
│   └── .gitkeep
│
└── tests/
    ├── test_memory.py
    ├── test_permissions.py
    └── test_agent.py
```

## ⚙️ Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/ATHENA-Personal-AI.git
cd ATHENA-Personal-AI
```

### 2. Create a virtual environment

**Windows:**

```bash
python -m venv .venv
.venv\Scripts\activate
```

**Linux/macOS:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Copy `.env.example` to `.env` and enter the required configuration.

Example:

```env
MODEL_API_KEY=your_api_key_here
MODEL_BASE_URL=your_model_endpoint_here
MODEL_NAME=your_model_name_here
DATABASE_PATH=data/athena.db
```

Use the actual endpoint, model identifier, and authentication method provided by your selected inference service.

**Never commit `.env` or real API keys to GitHub.**

### 5. Run the application

```bash
streamlit run app.py
```

## 🔐 Security Principles

ATHENA is designed around the following principles:

- Request only the permissions a task needs.
- Allowlist available tools instead of permitting arbitrary execution.
- Require confirmation for sensitive or irreversible actions.
- Log important tool calls and their outcomes.
- Keep secrets out of source control.
- Provide a way to inspect and delete stored memories.
- Avoid sending private information to external services unless needed and authorized.

These are design goals; their actual enforcement depends on the implemented controls and deployment environment.

## 🧪 Testing

Run the automated tests with:

```bash
pytest
```

Tests should cover memory persistence, permission enforcement, tool execution, and agent behavior.

## 👥 Team Contributions

The project is organized for parallel development:

- **AI & Agent Engineering:** Model integration, agent controller, and skill execution.
- **Memory & Application Engineering:** SQLite memory, user interface, and workflow integration.
- **Security & Infrastructure Engineering:** Permissions, audit logs, deployment, testing, and documentation.

## 🗺️ Roadmap

- [ ] Establish the model connection
- [ ] Build the basic chat interface
- [ ] Implement persistent memory
- [ ] Add reusable skills
- [ ] Add controlled tool execution
- [ ] Implement permission checks and audit logging
- [ ] Integrate and test all components
- [ ] Validate the required NVIDIA and Nebius integrations
- [ ] Prepare a working demo and documentation

## 🌌 Why ATHENA?

ATHENA is built around a simple idea: a personal AI should not only answer questions. It should help users accomplish tasks, remember useful context with their permission, and remain accountable for the actions it takes.

**An AI that remembers you, works for you, and respects your control.**

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for details.

Third-party models, libraries, and services remain subject to their respective licenses and terms.