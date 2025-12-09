# QUICK\_START

## 🚀 First Time Setup

{% hint style="danger" %}
**IMPORTANT: Before installing anything, configure the external USB drive to store all caches and dependencies.**
{% endhint %}

{% stepper %}
{% step %}
### Configure External Storage

Run the setup script to configure the external drive:

{% code title="shell" %}
```bash
npm run setup:external
```
{% endcode %}

This will:

* Configure npm to use external drive for cache
* Configure pip to use external drive for cache
* Set up Python virtual environments on external drive
* Add environment variables to your shell

Then reload your shell:

{% code title="shell" %}
```bash
source ~/.zshrc  # or ~/.bashrc
```
{% endcode %}
{% endstep %}

{% step %}
### Verify Configuration

Run the verification script:

{% code title="shell" %}
```bash
npm run verify:storage
```
{% endcode %}
{% endstep %}

{% step %}
### Install Dependencies

Install Python and NPM dependencies:

{% code title="shell" %}
```bash
# Python dependencies
pip install -r requirements-minimal.txt

# NPM dependencies
npm install
```
{% endcode %}
{% endstep %}
{% endstepper %}

## 📦 Available Commands

### Storage Management

{% code title="shell" %}
```bash
npm run setup:external    # Configure external storage
npm run verify:storage    # Verify configuration
npm run clean:disk        # Clean up disk space
```
{% endcode %}

### Development

{% code title="shell" %}
```bash
npm run dev               # Start ChatUi dev server
npm run build             # Build ChatUi
npm run format            # Format code
```
{% endcode %}

### API Testing

{% code title="shell" %}
```bash
npm run test:apis         # Test all API connections
npm run examples          # Run API client examples
```
{% endcode %}

## 🔧 Troubleshooting

<details>

<summary>Disk Space Issues</summary>

If you get `ENOSPC: no space left on device`, follow these steps:

Run cleanup:npm run clean:diskVerify external storage:npm run verify:storageRe-run setup if needed:npm run setup:external

</details>

<details>

<summary>External Drive Not Found</summary>

Steps to resolve:

Mount the USB driveVerify path:ls /Volumes/SEALED/DSHB/GALLERYRe-run setup:npm run setup:external

</details>

## 📚 Documentation

* [NPM Setup](/broken/pages/dc2a2520ba8d4b08ac4c3af06671b63ba1c6755b) - Complete NPM configuration guide
* [External Storage Setup](/broken/pages/1387c08552bb7720e6ed358ad99cc7ca5f8ddb7b) - External drive configuration
* [API Integrations](/broken/pages/b32220f2f9be9fb4a4cceeab391561f331227a3e) - API client usage
