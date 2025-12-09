# Troubleshooting

Common issues and solutions for all projects in the JJB Gallery repository.

## General Issues

### Import Errors

**Problem**: `ModuleNotFoundError` or `ImportError`

**Solutions**:

{% code title="Reinstall / virtualenv / check python version" %}
```bash
# Reinstall dependencies
pip install --upgrade -r requirements.txt

# Use virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt

# Check Python version
python --version  # Should be 3.8+
```
{% endcode %}

### Port Already in Use

**Problem**: `Address already in use` or `Port XXXX is already in use`

**Solutions**:

{% code title="Find and free port / change port" %}
```bash
# Find process using port
lsof -i :5000  # Replace 5000 with your port

# Kill process
kill -9 <PID>

# Or change port in configuration

# iOS Chatbot: PORT=5001 in .env

# LiteLLM: PORT=8001 in .env

# ChatUi: Change in vite.config.js
```
{% endcode %}

### API Key Issues

**Problem**: API errors, authentication failures, or "Invalid API key"

**Solutions:**

{% stepper %}
{% step %}
### Verify API key is set

Check environment variables:

```bash
echo $OPENAI_API_KEY
echo $ANTHROPIC_API_KEY
```
{% endstep %}

{% step %}
### Check key is in .env file

```bash
cat .env | grep API_KEY
```
{% endstep %}

{% step %}
### Ensure key is valid

* Check key has credits/quota
* Verify key hasn't expired
* Check key has required permissions
{% endstep %}

{% step %}
### Remove extra spaces or quotes

```bash
# Bad
OPENAI_API_KEY="sk-... "

# Good
OPENAI_API_KEY=sk-...
```
{% endstep %}
{% endstepper %}

## Project-Specific Issues

### RAG Model

#### Import Errors

{% code title="Install dependencies" %}
```bash
# Install missing dependencies
pip install langchain faiss-cpu sentence-transformers

# For GPU support
pip install faiss-gpu
```
{% endcode %}

#### Ollama Connection Issues

{% code title="Check Ollama" %}
```bash
# Check if Ollama is running
curl http://localhost:11434/api/tags

# Start Ollama
ollama serve

# Verify model is available
ollama list
```
{% endcode %}

#### Memory Issues

* Reduce chunk size: `RAG_CHUNK_SIZE=500`
* Use smaller embedding model: `RAG_EMBEDDING_MODEL=sentence-transformers/all-MiniLM-L6-v2`
* Process documents in batches

### Psychometrics

#### No Issues Expected

Psychometrics uses only standard library. If you see errors:

{% code title="Verify python / permissions" %}
```bash
# Verify Python installation
python --version

# Check file permissions
chmod +x main.py
```
{% endcode %}

### ChatUi

#### Node.js Issues

{% code title="Clear cache and reinstall" %}
```bash
cd ChatUi
rm -rf node_modules package-lock.json
npm cache clean --force
npm install

# Check Node version
node --version  # Should be 18+
```
{% endcode %}

#### MongoDB Connection

{% code title="Check or start MongoDB" %}
```bash
# Check if MongoDB is running
docker ps | grep mongo

# Start MongoDB
docker run -d -p 27017:27017 --name mongo-chatui mongo:latest

# Or check connection string in .env.local
```
{% endcode %}

#### Build Errors

{% code title="Fix build errors" %}
```bash
# Update dependencies
npm update

# Clear build cache
rm -rf .svelte-kit
npm run build
```
{% endcode %}

### iOS Chatbot

#### Flask Errors

{% code title="Install Flask" %}
```bash
# Install Flask
pip install flask flask-cors python-dotenv

# Check Flask version
python -c "import flask; print(flask.__version__)"
```
{% endcode %}

#### CORS Issues

Update `app.py`:

{% code title="CORS update" %}
```python
CORS(app, resources={r"/api/*": {"origins": "*"}})
```
{% endcode %}

#### Template Not Found

Ensure directories exist:

{% code title="Create templates/static" %}
```bash
mkdir -p templates static
```
{% endcode %}

### LiteLLM

#### Import Errors

{% code title="Install LiteLLM" %}
```bash
# Install LiteLLM
pip install litellm

# Or with proxy extras
pip install 'litellm[proxy]'
```
{% endcode %}

#### Provider Connection Issues

{% code title="Test providers" %}
```bash
# Test OpenAI
python -c "from litellm import completion; completion(model='gpt-3.5-turbo', messages=[{'role': 'user', 'content': 'test'}])"

# Test Ollama
curl http://localhost:11434/api/tags
```
{% endcode %}

#### Proxy Server Not Starting

{% code title="Check / change proxy port" %}
```bash
# Check port
lsof -i :8000

# Change port
PORT=8001 python proxy_server.py
```
{% endcode %}

### CrewAI

#### LLM Provider Not Detected

{% code title="Check status / setup" %}
```bash
# Check status
python main.py --status

# Get setup instructions
python main.py --setup-llm
```
{% endcode %}

#### Agent Errors

{% code title="Debug agent" %}
```bash
# Check verbose mode
export VERBOSE=true
python main.py --run ml

# Verify tools are available
python -c "from tools import ml_tools; print('OK')"
```
{% endcode %}

### Terminal Agents

#### API Key Not Found

{% code title="Set API key" %}
```bash
# Set API key
export OPENAI_API_KEY=sk-...

# Or create .env file
echo "OPENAI_API_KEY=sk-..." > .env
```
{% endcode %}

#### Command Not Found

{% code title="Make executable or run with python" %}
```bash
# Make executable
chmod +x agent.py

# Or use Python directly
python agent.py interactive
```
{% endcode %}

## Environment-Specific Issues

### macOS

#### Permission Errors

{% code title="Fix permissions" %}
```bash
chmod +x setup_all.sh
chmod +x test_all.sh
```
{% endcode %}

#### Homebrew Issues

{% code title="Update Homebrew / reinstall Python" %}
```bash
# Update Homebrew
brew update

# Reinstall Python
brew reinstall python@3.11
```
{% endcode %}

### Linux

#### Missing System Dependencies

{% code title="Ubuntu/Debian / Fedora" %}
```bash
# Ubuntu/Debian
sudo apt-get update
sudo apt-get install python3-pip nodejs npm

# Fedora
sudo dnf install python3-pip nodejs npm
```
{% endcode %}

#### Permission Errors

{% code title="Use virtual environment" %}
```bash
python3 -m venv venv
source venv/bin/activate
```
{% endcode %}

### Windows

#### Path Issues

{% code title="Use full paths / add to PATH" %}
```bash
# Use full paths
python C:\path\to\project\main.py

# Or add to PATH
set PATH=%PATH%;C:\Python311;C:\Python311\Scripts
```
{% endcode %}

#### Line Ending Issues

{% code title="Convert line endings" %}
```bash
# Convert line endings
dos2unix setup_all.sh
```
{% endcode %}

## Performance Issues

### Slow Responses

* Use local models (Ollama) instead of cloud APIs
* Reduce chunk sizes in RAG Model
* Use smaller models for faster inference
* Enable caching where available

### Memory Issues

* Use virtual environments to isolate dependencies
* Process data in batches
* Use smaller models
* Close unused applications

### Network Issues

* Check internet connection
* Verify API endpoints are accessible
* Check firewall settings
* Use local models (Ollama) to avoid network

## Getting Help

### Before Asking for Help

{% stepper %}
{% step %}
Check error messages carefully
{% endstep %}

{% step %}
Review project READMEs
{% endstep %}

{% step %}
Search existing issues on GitHub
{% endstep %}

{% step %}
Check documentation
{% endstep %}
{% endstepper %}

### When Asking for Help

Include:

* Project name and version
* Error message (full traceback)
* Steps to reproduce
* Environment details (OS, Python version, etc.)
* Configuration (sanitized, no API keys)

### Resources

* [Installation Guide](/broken/pages/1ef7fbd556340561c91ecdefb653c9fccf8867a9)
* [Configuration Guide](/broken/pages/188b94520c748ba0fcc9ef6682a13b7689110cb0)
* [Quick Start](/broken/pages/cfeafa45fb7bace32386a4181d2928a86d919ded)
* Project-specific READMEs
* GitHub Issues

## Prevention Tips

1. Use virtual environments for Python projects
2. Keep dependencies updated
3. Use version control (Git)
4. Test in isolated environments
5. Document your setup
6. Backup configurations

## Related Documentation

* [Installation Guide](/broken/pages/1ef7fbd556340561c91ecdefb653c9fccf8867a9)
* [Configuration Guide](/broken/pages/188b94520c748ba0fcc9ef6682a13b7689110cb0)
* [Quick Start](/broken/pages/cfeafa45fb7bace32386a4181d2928a86d919ded)
