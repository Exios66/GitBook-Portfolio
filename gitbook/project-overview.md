# Project Overview

Comprehensive overview of all projects in the JJB Gallery repository.

## Project Categories

### AI & Machine Learning

#### RAG Model

**Location**: `projects/RAG_Model/`

A complete Retrieval-Augmented Generation system with:

* Vector database (FAISS)
* Document embeddings
* Semantic search
* LLM integration

**Use Cases**: Document Q\&A, knowledge bases, research assistants

**Tech Stack**: Python, LangChain, FAISS, Sentence Transformers

#### Psychometrics

**Location**: `projects/Psychometrics/`

NASA Task Load Index (TLX) assessment tool for:

* Workload measurement
* Cognitive load assessment
* User experience research

**Use Cases**: UX research, human factors engineering, training evaluation

**Tech Stack**: Python (standard library)

### Chat Interfaces

#### ChatUi

**Location**: `projects/ChatUi/`

Modern SvelteKit chat interface for:

* LLM interactions
* Multiple model support
* Real-time streaming
* Message history

**Use Cases**: Chat applications, AI assistants, customer support

**Tech Stack**: SvelteKit, TypeScript, MongoDB

#### iOS Chatbot

**Location**: `projects/ios_chatbot/`

iOS-inspired chatbot with:

* Beautiful gradient UI
* Flask backend
* RESTful API
* Easy LLM integration

**Use Cases**: Chat applications, mobile web apps, demos

**Tech Stack**: Flask, JavaScript, HTML/CSS

### LLM Integration

#### LiteLLM Integration

**Location**: `projects/litellm/`

Unified LLM API access with:

* Proxy server
* Multiple provider support
* OpenAI-compatible API
* Configuration management

**Use Cases**: LLM abstraction layer, multi-provider support, API gateway

**Tech Stack**: Python, FastAPI, LiteLLM

#### CrewAI Multi-Agent System

**Location**: `projects/Crewai/`

Multi-agent framework with:

* Specialized agent swarms
* Domain-specific tools
* Web and CLI interfaces
* Multiple LLM providers

**Use Cases**: Complex workflows, research automation, code generation

**Tech Stack**: Python, CrewAI, Streamlit

#### Terminal Agents

**Location**: `projects/terminal_agents/`

AI coding agents for terminal with:

* Code analysis
* Code generation
* Interactive chat
* Rich terminal UI

**Use Cases**: Code assistance, debugging, learning

**Tech Stack**: Python, OpenAI API

## Project Comparison

| Project         | Type        | API Keys | Complexity | Best For          |
| --------------- | ----------- | -------- | ---------- | ----------------- |
| RAG Model       | ML/AI       | Optional | Medium     | Document Q\&A     |
| Psychometrics   | Assessment  | None     | Low        | UX Research       |
| ChatUi          | Web App     | Optional | Medium     | Chat Apps         |
| iOS Chatbot     | Web App     | Optional | Low        | Simple Chat       |
| LiteLLM         | Integration | Required | Medium     | LLM Abstraction   |
| CrewAI          | Framework   | Required | High       | Complex Workflows |
| Terminal Agents | CLI Tool    | Required | Low        | Code Assistance   |

## Technology Stack Summary

### Languages

* **Python**: Most projects
* **JavaScript/TypeScript**: ChatUi
* **HTML/CSS**: iOS Chatbot

### Frameworks

* **Flask**: iOS Chatbot
* **SvelteKit**: ChatUi
* **FastAPI**: LiteLLM proxy
* **Streamlit**: CrewAI web interface

### ML/AI Libraries

* **LangChain**: RAG Model
* **LiteLLM**: LiteLLM Integration
* **CrewAI**: CrewAI System
* **Sentence Transformers**: RAG Model

### Databases

* **FAISS**: RAG Model (vector database)
* **MongoDB**: ChatUi (chat history)

## Getting Started Recommendations

### For Beginners

{% stepper %}
{% step %}
### Psychometrics

* Simplest, no API keys needed
{% endstep %}

{% step %}
### iOS Chatbot

* Simple web app, easy to understand
{% endstep %}

{% step %}
### RAG Model

* Good introduction to ML concepts
{% endstep %}
{% endstepper %}

### For Intermediate Users

{% stepper %}
{% step %}
### ChatUi

* Modern web development
{% endstep %}

{% step %}
### LiteLLM

* API integration patterns
{% endstep %}

{% step %}
### Terminal Agents

* CLI tool development
{% endstep %}
{% endstepper %}

### For Advanced Users

{% stepper %}
{% step %}
### CrewAI

* Complex multi-agent systems
{% endstep %}

{% step %}
### RAG Model

* Advanced ML/AI concepts
{% endstep %}

{% step %}
### Full Stack Integration

* Combine multiple projects
{% endstep %}
{% endstepper %}

## Project Dependencies

### Common Dependencies

Most Python projects share:

* `pydantic` - Data validation
* `python-dotenv` - Environment variables
* `requests` - HTTP clients

### Project-Specific

* **RAG Model**: langchain, faiss-cpu, sentence-transformers
* **ChatUi**: @sveltejs/kit, mongodb, openai
* **CrewAI**: crewai, crewai-tools, streamlit
* **LiteLLM**: litellm, fastapi, uvicorn

## Integration Possibilities

### Combine Projects

{% stepper %}
{% step %}
### ChatUi + LiteLLM

Use LiteLLM proxy with ChatUi
{% endstep %}

{% step %}
### iOS Chatbot + RAG Model

Add RAG capabilities to chatbot
{% endstep %}

{% step %}
### CrewAI + RAG Model

Use RAG for research agents
{% endstep %}

{% step %}
### Terminal Agents + LiteLLM

Unified LLM access
{% endstep %}
{% endstepper %}

### Use Cases

* **Research Assistant**: RAG Model + CrewAI
* **Customer Support**: ChatUi + LiteLLM
* **Code Helper**: Terminal Agents + CrewAI
* **UX Testing**: Psychometrics + ChatUi

## Project Status

All projects are:

* ✅ **Complete**: Fully implemented
* ✅ **Documented**: Comprehensive READMEs
* ✅ **Tested**: Basic functionality verified
* ✅ **Maintained**: Active development

## Next Steps

{% stepper %}
{% step %}
### Choose a Project

Based on your interests and skill level
{% endstep %}

{% step %}
### Read Documentation

Check project-specific READMEs
{% endstep %}

{% step %}
### Install Dependencies

Follow installation guides
{% endstep %}

{% step %}
### Run Examples

Test with provided examples
{% endstep %}

{% step %}
### Customize

Adapt to your needs
{% endstep %}
{% endstepper %}

## Related Documentation

* [Installation Guide](/broken/pages/1ef7fbd556340561c91ecdefb653c9fccf8867a9)
* [Quick Start](/broken/pages/cfeafa45fb7bace32386a4181d2928a86d919ded)
* [Configuration Guide](/broken/pages/188b94520c748ba0fcc9ef6682a13b7689110cb0)
* Individual project pages
