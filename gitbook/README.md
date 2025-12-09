# README

[![GitHub](https://img.shields.io/badge/github-100000?style=for-the-badge\&logo=GitHub\&logoColor=E63786\&labelColor=black\&color=black)](https://github.com/Exios66)

Welcome! This GitHub repository serves as an evolving digital portfolio and gallery for **Jack J. Burleson**, showcasing a curated selection of previous work, open-source projects, previous research focuses, and presentations.

***

<p align="center"><a href="https://github.com/Exios66/JJB_Gallery/actions/workflows/pages/pages-build-deployment"><img src="https://github.com/Exios66/JJB_Gallery/actions/workflows/pages/pages-build-deployment/badge.svg" alt="Pages Build Deployment"> </a><a href="../LICENSE"><img src="https://img.shields.io/github/license/Exios66/GitBook-Portfolio?style=flat-square" alt="License: MIT"> </a><a href="https://github.com/Exios66/GitBook-Portfolio/releases"><img src="https://img.shields.io/github/v/release/Exios66/GitBook-Portfolio?style=flat-square&#x26;logo=github&#x26;label=Version" alt="Latest Release"> </a><a href="https://github.com/Exios66/GitBook-Portfolio/stargazers"><img src="https://img.shields.io/github/stars/Exios66/GitBook-Portfolio?style=flat-square" alt="Stars"> </a><a href="https://github.com/Exios66/GitBook-Portfolio/issues"><img src="https://img.shields.io/github/issues/Exios66/GitBook-Portfolio?style=flat-square" alt="Issues"> </a><a href="https://github.com/Exios66/GitBook-Portfolio/commits/main"><img src="https://img.shields.io/github/last-commit/Exios66/GitBook-Portfolio?style=flat-square" alt="Last Commit"></a></p>

***

## About Me

![image](<.gitbook/assets/a0d994ed 46e0 4185 886e 5568c9561843>)

Hi! I'm **Jack J. Burleson** – I am a data scientist, artificial intelligence-research engineer, a computational neuroscience researcher, and an open-source enthusiast.

I am passionate about broadening the traditional definitions of data science, in addition to distilling complex machine learning concepts and advanced statistical analytics democratically accessible, tangible, and meaningful through thoughtful discussion, wisdom passed onto me, and insightful visualizations.

This living portfolio highlights select projects in engineering, data analysis, machine learning, and technical writing.

![GitHub User's stars](https://img.shields.io/github/stars/Exios66?style=social) ![GitHub followers](https://img.shields.io/github/followers/Exios66?style=social)

***

## **📂 Repository Map**

![GitHub Tag](https://img.shields.io/github/v/tag/Exios66/GitBook-Portfolio?include_prereleases\&sort=date\&style=social) ![GitHub Release](https://img.shields.io/github/v/release/Exios66/GitBook-Portfolio?include_prereleases\&sort=date\&display_name=release\&style=social)

```bash
GitBook Portfolio (main branch)
├── index.html
├── theme-switcher.html
├── search.json
├── projects/
│   ├── agentswarm/
│   ├── terminal_agents
│   ├── chat_ui
│   ├── random_forests
│   └── NATD # The Neural Architecture of Truth and Deception Research Project & Directive
├── scripts/
│   └── (helper or build scripts)
├── requirements/
│   ├── requirements.txt
│   ├── requirements-minimal.txt
│   └── requirements-micro.txt
├── config/
│   └── pip.conf
├── docs/
│   ├── QUICK_START.md
│   └── setup/
│       ├── NPM_SETUP.md
│       ├── EXTERNAL_STORAGE_SETUP.md
│       └── ...
├── LICENSE
├── README.md
├── CHANGELOG.md
└── SECURITY.md
```

![GitHub repo size](https://img.shields.io/github/repo-size/Exios66/JJB_Gallery?style=for-the-badge)

***

## Project Gallery

| Project                             | Description                           | Link                                                                                 |
| ----------------------------------- | ------------------------------------- | ------------------------------------------------------------------------------------ |
| **CrewAI Multi-Agent Swarm System** | Multi-agent architecture using CrewAI | [CrewAI/README.md](/broken/pages/9833a9c14a9db6120496fae085e9919857d513d5)           |
| **Terminal Agents**                 | AI coding agents for the terminal     | [terminal\_agents/README.md](/broken/pages/f0162fa1ec76503ed24a73f97c7cd49a631f4e3f) |
| **Random Forest Essentials**        | Theory + application Quarto docs      | [Quarto/RandomForest](/broken/pages/00d2caeb080ba92ceeeafb9149dec827f6ffd235)        |
| **Jupyter ML & Pandas Notebooks**   | Machine learning workflow demos       | [notebooks/](/broken/pages/a89c84c38be5726340f1b7a3d529780471a86e6f)                 |
| **PyPI-Ready Python Template**      | Full CI/CD + packaging starter        | [Template Repo](https://github.com/Exios66/python-template)                          |
| **RAG Model Application**           | Retrieval-Augmented Generation system | [RAG\_Model/README.md](/broken/pages/1d7cb1cba295f4b354acac4052e225966a4b1410)       |
| **Psychometrics (NASA TLX)**        | Workload assessment toolkit           | [Psychometrics/README.md](/broken/pages/86028eafe1374cc309347477bd27702932651d4c)    |
| **Chat UI**                         | Modern SvelteKit chat interface       | [ChatUi/README.md](/broken/pages/96ff088efa7e0ccc752281b1c659fb40cd2f86ba)           |
| **LiteLLM Integration**             | Unified LLM API proxy                 | [litellm/README.md](/broken/pages/a0a44e524389436a8a87b3666217cdb637efb4c2)          |

***

## Production & Deployment

This repository maintains production-grade standards for all included projects. Each major project is designed for scalability, reliability, and ease of deployment.

### Deployment Options

{% stepper %}
{% step %}
### Docker Containers

Most applications (ChatUi, iOS Chatbot, LiteLLM) include Dockerfiles for containerized deployment.
{% endstep %}

{% step %}
### Cloud Platforms

Ready for deployment on AWS, Google Cloud, Azure, Vercel, and Netlify.
{% endstep %}

{% step %}
### Self-Hosted

Comprehensive guides for running on bare metal or virtual machines.
{% endstep %}
{% endstepper %}

### Production Readiness

* **CI/CD**: GitHub Actions workflows for automated testing and linting.
* **Security**: Regular dependency scanning, API key management best practices, and security headers.
* **Monitoring**: Health check endpoints and logging configuration.
* **Documentation**: Detailed setup guides, API references, and troubleshooting.

For detailed deployment guides, please refer to individual project READMEs or the [Quick Start Guide](/broken/pages/dbfc490dcaeab20b679114126a3df533950f5999).

### Operational Runbooks

* **Health Checks**: `/health` endpoints available on API services.
* **Logging**: Structured logging configured for major services.
* **Backup**: Procedures for backing up vector databases and chat history.

***

## Architecture Overview

The repository follows a modular architecture designed for interoperability and maintainability.

### Core Components

1. **Frontend Layer**: SvelteKit (ChatUi) and Flask templates (iOS Chatbot) providing user interfaces.
2. **API Layer**: RESTful APIs and WebSocket connections handling communication.
3. **Intelligence Layer**:
   * **Orchestration**: CrewAI for multi-agent coordination.
   * **Inference**: LiteLLM proxy for unified model access (OpenAI, Anthropic, Ollama).
   * **Retrieval**: RAG Model with FAISS vector database.
4. **Data Layer**:
   * **Vector Store**: FAISS for semantic search.
   * **Storage**: File-based storage and support for external drives (optimized for large models).
5. **Infrastructure**: Docker containers and Python virtual environments.

### Performance Considerations

* **Caching**: Utilization of external storage for large model weights and pip/npm caches.
* **Async Processing**: Asynchronous API calls for non-blocking operations in ChatUi and LiteLLM.
* **Optimized Builds**: Minimal docker images and tree-shaking for frontend assets.

***

## Recent Additions

* CrewAI Swarm System overhaul
* Terminal Coding Agents improvements
* Random Forest Quarto docs expansion
* Production deployment guides for all major projects
* Enhanced security policies and operational documentation

***

## Skills

* **Programming:** Python, R, JavaScript, TypeScript, SvelteKit, Flask
* **ML & Data:** Pandas, NumPy, scikit-learn, TensorFlow, PyTorch
* **Visualization:** Matplotlib, Seaborn, Quarto, D3.js
* **EngOps:** GitHub Actions, Docker, Kubernetes, pre-commit
* **Documentation:** Jupyter, Markdown, Quarto, Technical Writing
* **AI Engineering:** RAG, Vector Databases, LLM Integration, Agent Systems

***

## Presentations

* _Random Forest Essentials_ – 2024
* _Talking to Agents_ – 2024
* _(More added continuously…)_

***

## Preferred Contact Methods

📩 [jackjburleson@proton.me](mailto:jackjburleson@proton.me) (Business)\
📩 [jjburleson@wisc.edu](mailto:jjburleson@wisc.edu) (Academic)\
🌐 [https://github.com/Exios66](https://github.com/Exios66)\
🔗 [https://linkedin.com/in/jack-j-burleson](https://linkedin.com/in/jack-j-burleson)

***

## Socials

* [GitHub](https://github.com/Exios66)
* [HuggingFace](https://huggingface.co/Exios66)
* [Twitter/X](https://twitter.com/Exios66)

***

## Further Reading

* [CrewAI System](/broken/pages/9833a9c14a9db6120496fae085e9919857d513d5)
* [Terminal Agents](/broken/pages/f0162fa1ec76503ed24a73f97c7cd49a631f4e3f)
* [Documentation Index](/broken/pages/1debacff0870a71d93f50a7fab07ec4309018e0a) - Comprehensive documentation
* [CHANGELOG.md](/broken/pages/d532a8f3864e3e0ccd0e19ee7c00119fdb4b8509)

## 📚 Documentation

Comprehensive documentation is available in the [`docs/`](/broken/pages/18688bb33204805ec90d35badd6ca076ad73980c) directory:

* [**Setup & Configuration**](/broken/pages/9a382109f8979080de0192c8dc5b35a2cfb64caa) - Setup guides and configuration
* [**Development**](/broken/pages/c2719d7d005f70f5bf1f230a98288783bfd076dc) - Development guides
* [**Security**](/broken/pages/c0d45804786cfa5cc58cdd8f722d95182c0393ba) - Security policies
* [**Scripts**](/broken/pages/bcccc4e759378c3c112410f45e78e0f8d93f40d0) - Script documentation
* [**Projects**](/broken/pages/446756191ce9766c4330a4c126810f3521689a78) - Project-specific documentation

***
