# 🦜🔗 Learning LangChain — Mein Lernprojekt

> Persönliches Repository zum Buch **"Learning LangChain"** von Mayo Oshin & Nuno Campos (O'Reilly, Februar 2025)

---

## 📖 Über das Buch

| | |
|--|--|
| **Titel** | Learning LangChain: Building AI and LLM Applications with LangChain and LangGraph |
| **Autoren** | Mayo Oshin, Nuno Campos |
| **Verlag** | O'Reilly Media |
| **Erschienen** | Februar 2025 |
| **Seiten** | 296 |
| **Niveau** | Anfänger bis Fortgeschrittene |
| **Sprache** | Python & JavaScript |

---

## 🗂️ Repository Struktur

```
learning-langchain/
│
├── README.md
├── .env                    # API Keys (nicht in GitHub!)
├── .gitignore
├── requirements.txt
│
├── chapter1/               # LLM Fundamentals
│   ├── 01_llm_basics.ipynb
│   ├── 02_prompt_templates.ipynb
│   ├── 03_output_parsers.ipynb
│   └── 04_lcel_chains.ipynb
│
├── chapter2/               # RAG Part I: Indexing
│   ├── 01_embeddings.ipynb
│   ├── 02_document_loaders.ipynb
│   ├── 03_text_splitters.ipynb
│   └── 04_vector_stores.ipynb
│
├── chapter3/               # RAG Part II: Chatting
│   ├── 01_retrieval.ipynb
│   ├── 02_query_transformation.ipynb
│   ├── 03_rag_fusion.ipynb
│   └── 04_query_routing.ipynb
│
├── chapter4/               # Memory mit LangGraph
│   ├── 01_stategraph.ipynb
│   ├── 02_memory.ipynb
│   └── 03_chat_history.ipynb
│
├── chapter5/               # Cognitive Architectures
│   ├── 01_llm_call.ipynb
│   ├── 02_chain.ipynb
│   └── 03_router.ipynb
│
├── chapter6/               # Agent Architecture
│   ├── 01_plan_do_loop.ipynb
│   ├── 02_langgraph_agent.ipynb
│   └── 03_tools.ipynb
│
├── chapter7/               # Agents II
│   ├── 01_reflection.ipynb
│   ├── 02_subgraphs.ipynb
│   └── 03_multi_agent.ipynb
│
├── chapter8/               # LLM Patterns
│   ├── 01_structured_output.ipynb
│   ├── 02_streaming.ipynb
│   └── 03_human_in_loop.ipynb
│
├── chapter9/               # Deployment
│   ├── 01_backend_api.ipynb
│   ├── 02_langgraph_platform.ipynb
│   └── 03_security.ipynb
│
├── chapter10/              # Testing & Evaluation
│   ├── 01_self_corrective_rag.ipynb
│   ├── 02_evaluation.ipynb
│   └── 03_monitoring.ipynb
│
└── projects/               # Eigene Projekte
    ├── rag_chatbot/
    └── langchain_agent/
```

---

## 📚 Inhaltsübersicht

### Kapitel 1 — LLM Fundamentals mit LangChain
> *Seite 1-22*

- **LLM Interface** — Das alte Interface für Text-Completion Modelle
- **Chat Model Interface** — Modernes Interface mit Rollen (system, human, assistant)
- **Prompt Templates** — Wiederverwendbare Vorlagen mit dynamischen Platzhaltern `{variable}`
  - `PromptTemplate` — Für einfache Text-Prompts
  - `ChatPromptTemplate` — Für Chat-basierte Prompts mit Rollen
- **Output Parser** — LLM-Antworten in strukturierte Formate umwandeln
  - JSON Output
  - CSV, XML und andere Formate
  - Structured Output mit Pydantic
- **Runnable Interface** — Einheitliche Schnittstelle für alle LangChain-Komponenten
  - `invoke()` — Einzelne Eingabe → Einzelne Ausgabe
  - `batch()` — Mehrere Eingaben gleichzeitig
  - `stream()` — Ausgabe Token für Token (wie ChatGPT)
  - `ainvoke()` — Asynchrone Version
- **Chains — Komponenten zusammenbauen**
  - **Imperative Composition** — Klassischer Python-Code mit `@chain` Decorator
  - **Declarative Composition (LCEL)** — `template | model` Pipe-Operator

---

### Kapitel 2 — RAG Part I: Indexing
> *Seite 23-56*

- **Was ist RAG?** — Eigene Dokumente dem LLM als Wissensbasis geben
- **Embeddings** — Text in Zahlen umwandeln für semantische Suche
  - Embeddings vor LLMs
  - LLM-basierte Embeddings
  - Semantische Embeddings erklärt
- **Dokumente laden** — `Document Loaders`
  - PDFs, Word-Dokumente, Webseiten, CSVs
- **Text Splitting** — Dokumente in Chunks aufteilen
  - Verschiedene Splitting-Strategien
  - Chunk Size und Overlap
- **Vektordatenbanken** — Embeddings speichern und suchen
  - PGVector Setup
  - Arbeiten mit Vector Stores
- **Indexing Optimierung**
  - MultiVectorRetriever
  - RAPTOR
  - ColBERT

---

### Kapitel 3 — RAG Part II: Chatting with your Data
> *Seite 57-92*

- **Retrieval-Augmented Generation** — Das komplette RAG-System
- **Relevante Dokumente abrufen** — Retrieval Strategien
- **LLM Antworten generieren** — Mit Kontext aus Dokumenten
- **Query Transformation** — Anfragen optimieren
  - Rewrite-Retrieve-Read
  - Multi-Query Retrieval
  - RAG-Fusion
  - Hypothetical Document Embeddings (HyDE)
- **Query Routing** — Anfragen an richtige Datenquellen leiten
  - Logical Routing
  - Semantic Routing
- **Query Construction**
  - Text-to-Metadata Filter
  - Text-to-SQL

---

### Kapitel 4 — Memory mit LangGraph
> *Seite 95-114*

- **Chatbot Memory System** — Warum Chatbots vergessen und wie man es löst
- **LangGraph Einführung** — Framework für komplexe AI Workflows
- **StateGraph** — Zustände und Übergänge definieren
- **Memory zu StateGraph hinzufügen**
- **Chat History verwalten**
  - Messages trimmen
  - Messages filtern
  - Aufeinanderfolgende Messages zusammenführen

---

### Kapitel 5 — Cognitive Architectures mit LangGraph
> *Seite 115-133*

- **Architecture #1: LLM Call** — Einfachster Anwendungsfall
- **Architecture #2: Chain** — Mehrere Schritte verbinden
- **Architecture #3: Router** — Dynamisch verschiedene Pfade wählen

---

### Kapitel 6 — Agent Architecture
> *Seite 135-153*

- **Plan-Do Loop** — Wie Agents denken und handeln
- **LangGraph Agent bauen** — Schritt für Schritt
- **Tools** — Was Agents benutzen können
  - Web Search, APIs, Datenbanken, Code-Ausführung
- **Immer zuerst ein Tool aufrufen**
- **Viele Tools verwalten**

---

### Kapitel 7 — Agents II
> *Seite 155-170*

- **Reflection** — Agent überprüft und verbessert eigene Antworten
- **Subgraphs in LangGraph**
  - Subgraph direkt aufrufen
  - Subgraph mit Funktion aufrufen
- **Multi-Agent Architectures** — Mehrere Agents zusammenarbeiten
  - Supervisor Architecture

---

### Kapitel 8 — Patterns für LLMs
> *Seite 171-189*

- **Structured Output** — LLM immer im gleichen Format antworten lassen
- **Intermediate Output** — Zwischenergebnisse anzeigen
- **Streaming Token für Token**
- **Human-in-the-Loop** — Mensch greift in AI-Prozess ein
- **Multitasking LLMs** — Mehrere Aufgaben gleichzeitig

---

### Kapitel 9 — Deployment
> *Seite 191-214*

- **Prerequisites** — Was man vorher braucht
- **Dependencies installieren**
- **Large Language Model** konfigurieren
- **Vector Store** einrichten
- **Backend API** bauen
- **LangSmith Account** — Monitoring und Debugging
- **LangGraph Platform API**
  - Data Models
  - Features
- **App auf LangGraph Platform deployen**
  - LangGraph API Config erstellen
  - Lokal testen
  - Aus LangSmith UI deployen
  - LangGraph Studio
- **Security** — Absicherung der Anwendung

---

### Kapitel 10 — Testing & Evaluation
> *Seite 215-250*

- **Testing über den gesamten Entwicklungszyklus**
- **Design Stage: Self-Corrective RAG**
- **Preproduction Stage**
  - Datasets erstellen
  - Evaluierungskriterien definieren
  - Regression Testing
  - Agent End-to-End Performance
- **Production**
  - Tracing
  - Feedback sammeln
  - Classification und Tagging
  - Fehler monitoren und beheben

---

### Kapitel 11 — Building with LLMs
> *Seite 251-257*

- **Interactive Chatbots**
- **Collaborative Editing mit LLMs**
- **Ambient Computing**

---

## ⚙️ Setup

### Voraussetzungen

- Python 3.10+
- pip

### Installation

```bash
# 1. Repository klonen
git clone https://github.com/DEIN-USERNAME/learning-langchain.git
cd learning-langchain

# 2. Virtual Environment erstellen
python -m venv venv

# 3. Virtual Environment aktivieren
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate

# 4. Dependencies installieren
pip install -r requirements.txt

# 5. Jupyter starten
jupyter notebook
```

### API Key setzen

```bash
# Windows:
set OPENAI_API_KEY=sk-dein-key-hier

# Mac/Linux:
export OPENAI_API_KEY=sk-dein-key-hier
```

### requirements.txt

```
langchain
langchain-openai
langchain-community
langchain-text-splitters
langchain-postgres
notebook
python-dotenv
```

---

## 🔑 Wichtige Konzepte

| Konzept | Beschreibung | Kapitel |
|---------|-------------|---------|
| **Chat Models** | Moderne LLMs mit Rollen (system, human, ai) | 1 |
| **Prompt Templates** | Wiederverwendbare Vorlagen mit Platzhaltern | 1 |
| **LCEL** | `template \| model` — Komponenten verbinden | 1 |
| **RAG** | Eigene Dokumente dem LLM geben | 2-3 |
| **Embeddings** | Text in Zahlen umwandeln | 2 |
| **Vektordatenbank** | Embeddings speichern und suchen | 2 |
| **Chunks** | Dokumente in kleine Stücke aufteilen | 2 |
| **Memory** | Chatbot merkt sich Konversation | 4 |
| **LangGraph** | Framework für komplexe Workflows | 4-7 |
| **Agents** | Autonome AI die selbst entscheidet | 6-7 |
| **Tools** | Was Agents benutzen können | 6 |
| **LangSmith** | Debugging und Monitoring | 9-10 |

---

## 📝 Meine Notizen

### Was ich gelernt habe
- [ ] Kapitel 1 — LLM Fundamentals
- [ ] Kapitel 2 — RAG Indexing
- [ ] Kapitel 3 — RAG Chatting
- [ ] Kapitel 4 — Memory
- [ ] Kapitel 5 — Cognitive Architectures
- [ ] Kapitel 6 — Agents
- [ ] Kapitel 7 — Agents II
- [ ] Kapitel 8 — LLM Patterns
- [ ] Kapitel 9 — Deployment
- [ ] Kapitel 10 — Testing
- [ ] Kapitel 11 — Building with LLMs

---

## 🚀 Eigene Projekte

| Projekt | Beschreibung | Status |
|---------|-------------|--------|
| RAG Chatbot | Chat mit eigenen Dokumenten | 🔜 Geplant |
| LangChain Agent | Autonomer Agent mit Tools | 🔜 Geplant |
| DSGVO-konformes RAG | RAG mit lokalen LLMs (Ollama) | 🔜 Geplant |

---

## 📌 Nützliche Links

- [LangChain Dokumentation](https://docs.langchain.com)
- [LangGraph Dokumentation](https://langchain-ai.github.io/langgraph/)
- [LangSmith](https://smith.langchain.com)
- [OpenAI API](https://platform.openai.com)
- [GitHub Repo zum Buch](https://github.com/langchain-ai/learning-langchain)
- [Ollama — Lokale LLMs](https://ollama.ai)

---

## ⚠️ .gitignore

```
venv/
.env
__pycache__/
.ipynb_checkpoints/
*.pyc
```

---

*Lernprojekt von Daniel — gestartet Juni 2026* 🚀
