---
icon: file-chart-pie
---

# PROJECTS

This directory contains multiple AI and ML projects, each with its own implementation and documentation.

## Available Projects

### 🤖 [RAG\_Model](/broken/pages/3d9a228fed6814ed0ca2d013f5da30f262d6614a)

Retrieval-Augmented Generation system with vector database, embeddings, and intelligent document retrieval.

**Quick Start:**

```bash
cd RAG_Model
pip install -r requirements.txt
python main.py
```

### 📊 [Psychometrics](/broken/pages/9e658a1a539062c69de7150208587c35da788ee4)

NASA Task Load Index (TLX) assessment tool for measuring workload and cognitive demand.

**Quick Start:**

```bash
cd Psychometrics
pip install -r requirements.txt
python main.py
```

### 💬 [ChatUi](/broken/pages/f43ffcfbdda03b622a6547ca7ac38e4ee74b40a2)

Modern SvelteKit chat interface for interacting with LLM models.

**Quick Start:**

```bash
cd ChatUi
npm install
npm run dev
```

### 📱 [ios\_chatbot](/broken/pages/7c2b4f745ac2b959b7ad7de028bf929f3bb3823d)

iOS-inspired chatbot with Flask backend and beautiful gradient UI.

**Quick Start:**

```bash
cd ios_chatbot
pip install -r requirements.txt
python app.py
```

### 🔌 [litellm](/broken/pages/6f12322bea3aa3319f72dee6b1aaf6eadd25257e)

LiteLLM integration with proxy server for unified LLM API access.

**Quick Start:**

```bash
cd litellm
pip install -r requirements.txt
python proxy_server.py
```

### 🤝 [CrewAI](/broken/pages/4fe85f52381da51e732721e273df7118cee54cae)

Multi-agent system using CrewAI for complex workflows and task automation.

**Quick Start:**

```bash
cd Crewai
pip install -r requirements.txt
python main.py --setup
```

### ⌨️ [terminal\_agents](/broken/pages/ce3814607f0c3105dbc68c0cbeabb8099c139776)

AI coding agents for the terminal, similar to OpenCode.

## Setup

### Quick Setup (All Projects)

```bash
# Install all dependencies
chmod +x setup_all.sh
./setup_all.sh
```

### Individual Setup

See [SETUP\_GUIDE.md](/broken/pages/23af0abc1d80415f70cd9a39c2e4abf97cb23fdd) for detailed instructions.

## Testing

### Test All Projects

```bash
chmod +x test_all.sh
./test_all.sh
```

### Test Individual Projects

See each project's README for specific testing instructions.

## Documentation

* [**SETUP\_GUIDE.md**](/broken/pages/23af0abc1d80415f70cd9a39c2e4abf97cb23fdd) - Complete setup instructions
* [**QUICK\_START.md**](/broken/pages/e63bdfce992b5de7dd53bf2c6ad8afa8129bf385) - Quick start guide
* Each project has its own README with detailed documentation

## Requirements

{% hint style="info" %}
* Python 3.8+
* Node.js 18+ (for ChatUi)
* pip and npm
{% endhint %}

## Optional Dependencies

* Ollama (for local LLM models)
* MongoDB (for ChatUi chat history)
* API Keys (OpenAI, Anthropic, etc.)

## Project Status

| Project          | Status     | Dependencies | API Keys Required |
| ---------------- | ---------- | ------------ | ----------------- |
| RAG\_Model       | ✅ Complete | Python       | Optional          |
| Psychometrics    | ✅ Complete | Python       | No                |
| ChatUi           | ✅ Complete | Node.js      | Optional          |
| ios\_chatbot     | ✅ Complete | Python       | Optional          |
| litellm          | ✅ Complete | Python       | Optional          |
| CrewAI           | ✅ Complete | Python       | Yes               |
| terminal\_agents | ✅ Complete | Python       | Yes               |

## Getting Started

{% stepper %}
{% step %}
### Read setup guide

Read [SETUP\_GUIDE.md](/broken/pages/23af0abc1d80415f70cd9a39c2e4abf97cb23fdd) for detailed setup instructions.
{% endstep %}

{% step %}
### Choose a project

Select a project that interests you from the Available Projects list.
{% endstep %}

{% step %}
### Follow project README

Follow the chosen project's README for specific instructions.
{% endstep %}

{% step %}
### Set environment variables

Set up environment variables required by the project as described in its documentation.
{% endstep %}

{% step %}
### Test the project

Run the project's tests or quick start commands to ensure it works.
{% endstep %}
{% endstepper %}

## Contributing

{% stepper %}
{% step %}
### Read the project's README

Open the README for the project you want to contribute to and follow its contribution guidelines.
{% endstep %}

{% step %}
### Follow coding standards

Adhere to the project's coding standards and style.
{% endstep %}

{% step %}
### Test your changes

Run tests and verify your changes work as expected.
{% endstep %}

{% step %}
### Update documentation

Update any relevant documentation to reflect your changes.
{% endstep %}
{% endstepper %}

## Support

<details>

<summary>How to get help</summary>

1. Check the project's README
2. Review [SETUP\_GUIDE.md](/broken/pages/23af0abc1d80415f70cd9a39c2e4abf97cb23fdd)
3. Check the main repository documentation

</details>

## License

See the main repository LICENSE file.
