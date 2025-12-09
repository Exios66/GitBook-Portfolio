---
icon: clipboard-prescription
---

# Scripts Documentation

## 0. render\_gh\_pages.sh (Main GitHub Pages Renderer)

The `render_gh_pages.sh` script is the primary script for rendering all GitHub Pages content. It renders all Quarto pages defined in `_quarto.yml` for the complete website.

### What It Renders

This script renders all pages configured in `_quarto.yml`:

* ✅ `index.html` (Home page)
* ✅ `CHANGELOG.html`
* ✅ `SECURITY.html`
* ✅ `projects/CrewAI/README.html`
* ✅ `projects/terminal_agents/README.html`
* ✅ `Quarto/randomforest.html`

### Usage

```bash
# Standard rendering (cleans build artifacts first)
./scripts/render_gh_pages.sh

# Render without cleaning (faster, but may have stale artifacts)
./scripts/render_gh_pages.sh --no-clean

# Render and start preview server
./scripts/render_gh_pages.sh --preview

# Combine options
./scripts/render_gh_pages.sh --no-clean --preview
```

### Features

* Comprehensive rendering: Renders all website pages in one command
* Automatic cleanup: Removes old build artifacts before rendering
* Python environment detection: Automatically activates `.venv` or `venv` if available
* Build organization: Outputs organized in `_build/quarto/` directory
* Verification: Checks that all expected output files were created
* Preview server: Optional local preview with `--preview` flag
* Colored output: Easy-to-read status messages
* Error handling: Fails fast with clear error messages

### What It Does

{% stepper %}
{% step %}
### Checks prerequisites

Verifies Quarto installation and required tools.
{% endstep %}

{% step %}
### Activates Python virtual environment

Automatically activates `.venv` or `venv` if present.
{% endstep %}

{% step %}
### Cleans old artifacts

Removes old build artifacts (unless `--no-clean` is used).
{% endstep %}

{% step %}
### Renders pages

Renders all pages defined in `_quarto.yml`.
{% endstep %}

{% step %}
### Verifies outputs

Checks that all expected output files exist.
{% endstep %}

{% step %}
### Optional preview

Starts preview server when `--preview` is provided.
{% endstep %}
{% endstepper %}

### When to Use

* Before deploying to GitHub Pages
* After editing any Quarto/Markdown files
* Local development with `--preview`
* CI/CD pipelines for automated deployments

### Build Output

* HTML files: Rendered in repository root (e.g., `index.html`, `CHANGELOG.html`)
* Build artifacts: Organized in `_build/quarto/` (gitignored)
* Support files: CSS, JS, and other assets in `_build/quarto/site_libs/`

### Prerequisites

* Quarto CLI installed: https://quarto.org/docs/get-started/
* Python environment (optional, but recommended)
* All dependencies from `requirements/requirements.txt` installed

### Example Workflow

```bash
# 1. Make changes to Quarto/Markdown files

# 2. Render all pages
./scripts/render_gh_pages.sh

# 3. Review changes locally (optional)
./scripts/render_gh_pages.sh --preview

# 4. Commit and push to gh-pages branch
git add .
git commit -m "Update website content"
git push origin gh-pages
```

### Troubleshooting

<details>

<summary>Quarto not found</summary>

```bash
# macOS
brew install quarto

# Linux/Windows
# See: https://quarto.org/docs/get-started/installation/
```

</details>

<details>

<summary>Python environment issues</summary>

* Ensure virtual environment is set up: `python3 -m venv .venv`
* Install dependencies: `pip install -r requirements/requirements.txt`

</details>

<details>

<summary>Build artifacts in wrong location</summary>

* The script automatically moves old artifacts to `_build/quarto/`
* Check `.gitignore` to ensure `_build/` is ignored

</details>

***

## 1. render\_randomforest.sh

Run the `render_randomforest.sh` script to render the `randomforest.qmd` file to HTML and PDF. This script also starts a preview server on the default port 4343.

Run the script:

```bash
./scripts/render_randomforest.sh
```

Open the preview server in your browser:

```bash
open http://localhost:4343
```

***

## 2. free\_ram.sh

The `free_ram.sh` script is an enhanced tool that frees up unnecessary RAM, disk space, and compute resources by clearing extensive caches, temporary files, and idle processes. Useful when working with large Jupyter notebooks or when system resources are low.

### What it clears

Python & Development Tools

* Python cache files: `__pycache__`, `.pyc`, `.pyo`, `.py[cod]` files
* Jupyter/IPython checkpoints: `.ipynb_checkpoints`
* Quarto cache: Quarto freeze directories and user cache
* pip, Conda, Poetry, pipx caches
* Virtual environment caches: cache files in `.venv`, `venv`, `env`

Package Manager Caches

* npm cache
* yarn cache
* Homebrew cache (macOS)
* Cargo cache (Rust)
* Go module cache

System & Application Caches

* Docker cache: unused images, containers, volumes
* Browser caches: Chrome, Firefox, Safari (macOS)
* IDE caches: VS Code, PyCharm, IntelliJ IDEA
* System temporary files (7+ days)
* System logs (30+ days)
* Font cache (macOS)
* DNS cache

System Resources (Optional)

* System page cache (Linux; requires sudo)
* Swap files: clear/reset swap (Linux; requires sudo)

### Free RAM Usage

```bash
# Standard cleanup (safe, recommended)
./scripts/free_ram.sh

# Aggressive cleanup including idle processes (use with caution)
KILL_IDLE_PROCESSES=yes ./scripts/free_ram.sh
```

### Features

* Comprehensive cleanup across 20+ cache types
* Cross-platform support (macOS and Linux)
* Colored output and memory reporting
* Safe by default: only clears caches and temp files older than 7 days
* Space tracking and permission-aware behavior
* Optional idle process termination

### Advanced Options

#### Kill Idle Processes

To terminate idle or high-CPU processes (use with extreme caution):

```bash
KILL_IDLE_PROCESSES=yes ./scripts/free_ram.sh
```

Warning: This may close applications that appear idle but are actually working.

### Notes

* System-level operations require sudo and will be skipped if not available.
* Browser caches will be cleared — you may need to re-login to websites.
* IDE caches will be cleared — first launch after cleanup may be slower.

### What Gets Preserved

* Source code and project files
* Git history and repository data
* Installed packages (only caches are cleared)
* User preferences and settings
* Active application data

***

## 7. Rerender for GitHub Pages (rerender\_gh\_pages.sh)

### What Rerender Does

{% stepper %}
{% step %}
### Cleanup

Cleans up old `index.html` and Quarto cache/freeze directories.
{% endstep %}

{% step %}
### Activate venv

Activates the virtual environment (if available) to ensure correct dependencies.
{% endstep %}

{% step %}
### Render document

Renders `Quarto/randomforest.qmd` to HTML.
{% endstep %}

{% step %}
### Move output

Moves the output HTML to `index.html` in the repository root.
{% endstep %}

{% step %}
### Update support files

Moves/updates the support files directory (`randomforest_files`) to the repository root.
{% endstep %}
{% endstepper %}

### When to Use

Run this script whenever you edit `Quarto/randomforest.qmd` and want to update the public-facing page on GitHub Pages.

***

## Virtual Environment Management

Activate the Python virtual environment:

```bash
source .venv/bin/activate
```

Deactivate the Python virtual environment:

```bash
deactivate
```

***

## Manual System Cache Clearing (Linux)

Clear cached memory (requires sudo):

```bash
sudo sync; sudo sh -c 'echo 3 > /proc/sys/vm/drop_caches'
```

Note: This functionality is included in the `free_ram.sh` script on Linux when run with appropriate privileges.

***

## 3. Cloud Sandbox Setup (setup\_cloud\_sandbox.sh)

The `setup_cloud_sandbox.sh` script configures remote Python environments to avoid local disk space usage. Useful when you need to work with large Python packages like CrewAI but have limited local disk space.

### Cloud Sandbox Setup Usage

```bash
./scripts/setup_cloud_sandbox.sh
```

### Available Options

{% stepper %}
{% step %}
### GitHub Codespaces (Recommended)

* Free tier: 60 hours/month
* Automatic package installation
* Full VS Code in browser
* Zero local disk usage
{% endstep %}

{% step %}
### Remote SSH Server

* Use an existing remote server
* Execute Python remotely
{% endstep %}

{% step %}
### Docker Container

* Local containerized environment
* Minimal local disk usage
{% endstep %}

{% step %}
### Replit/CodeSandbox

* Browser-based development
* Free tiers available
{% endstep %}
{% endstepper %}

### Benefits

* No local disk space for Python packages
* Consistent environment, easy to reset/recreate
* Cost-effective (many free options)

***

## 4. Use Cloud Sandbox (use\_cloud\_sandbox.sh)

After setting up a cloud sandbox, use this script to execute Python commands in the remote environment.

### Use Cloud Sandbox Usage

```bash
# Execute a Python script remotely
./scripts/use_cloud_sandbox.sh python projects/CrewAI/main.py

# Start interactive session (SSH/Docker)
./scripts/use_cloud_sandbox.sh
```

### Prerequisites

* Cloud sandbox must be configured (run `setup_cloud_sandbox.sh` first)
* For SSH: valid SSH connection
* For Docker: Docker installed and running
* For Codespaces: Codespace already created

For detailed instructions, see `.cloud_sandbox/README.md`.

***

## 6. Git SSH Setup (setup\_git\_ssh.sh)

The `setup_git_ssh.sh` script configures SSH keys for GitHub and switches your repository to use SSH protocol. Eliminates password prompts and works better with automation tools.

### Why SSH?

* No password prompts during git operations
* Better integration with GitHub CLI and Codespaces
* More secure for automated workflows

### Git SSH Setup Usage

```bash
./scripts/setup_git_ssh.sh
```

### What SSH Setup Does

{% stepper %}
{% step %}
### Checks for SSH keys

Detects existing SSH keys.
{% endstep %}

{% step %}
### Generates key if needed

Creates an Ed25519 key if none present.
{% endstep %}

{% step %}
### Starts SSH agent

Starts the SSH agent and adds the key.
{% endstep %}

{% step %}
### Copies public key to clipboard

Copies the public key for adding to GitHub.
{% endstep %}

{% step %}
### Guides addition to GitHub

Provides instructions to add the key to your GitHub account.
{% endstep %}

{% step %}
### Tests connection & updates remote

Tests SSH connection and optionally updates git remote from HTTPS to SSH.
{% endstep %}
{% endstepper %}

### After Setup

* All `git push/pull` operations use SSH
* No password prompts required
* Works seamlessly with `gh` CLI and Codespaces

Current status: Your repository currently uses HTTPS protocol. To switch to SSH, run:

```bash
./scripts/setup_git_ssh.sh
```

For detailed Git protocol recommendations, see `docs/GIT_PROTOCOL_GUIDE.md`.

***

## 5. Auto-launch Codespace (launch\_codespace.sh)

The `launch_codespace.sh` script automatically creates and launches a GitHub Codespace in the free tier, providing an instant cloud development environment.

### Required Tools & Setup

* GitHub CLI (`gh`) installed
* Repository pushed to GitHub
* GitHub CLI authenticated (`gh auth login`)

### How to Use

```bash
./scripts/launch_codespace.sh
```

### What this script does

{% stepper %}
{% step %}
### Checks CLI

Verifies GitHub CLI installation.
{% endstep %}

{% step %}
### Verifies auth

Ensures `gh` is authenticated.
{% endstep %}

{% step %}
### Finds or creates Codespace

Creates or reuses an existing Codespace.
{% endstep %}

{% step %}
### Waits for readiness

Waits until the Codespace is ready.
{% endstep %}

{% step %}
### Opens editor

Opens in VS Code (if installed) or the web browser.
{% endstep %}

{% step %}
### Uses free tier

Uses free tier machine (2 cores, 4GB RAM) and auto-installs packages from `requirements/requirements.txt`.
{% endstep %}
{% endstepper %}

### Installation

macOS:

```bash
brew install gh
gh auth login
```

Linux:

```bash
# See https://cli.github.com/manual/installation
```

Windows:

```bash
winget install GitHub.cli
gh auth login
```

### Troubleshooting

* Ensure repository is pushed: `git push -u origin main`
* Verify authentication: `gh auth status`
* Check Codespace quota: `gh api user/codespaces`
* Manually create: GitHub → Code → Codespaces → Create codespace

***

For any scripts that interact with system-level operations or require elevated permissions, the scripts will generally skip steps requiring sudo if not available and provide informative status messages.
