---
icon: vault
---

# SECURITY POLICY

Welcome to this repository! Security is a **top priority** for all contributors, maintainers, and users. This SECURITY.md document describes security practices, responsible disclosure, and guidance for keeping the repository safe for everyone.

***

## Supported Versions

| Version  | Supported            | Maintenance          |
| -------- | -------------------- | -------------------- |
| Latest   | :white\_check\_mark: | :white\_check\_mark: |
| Previous | :white\_check\_mark: | :x:                  |

_Only the latest version is actively maintained and receives security updates._

***

## Reporting a Vulnerability

**If you discover a security vulnerability, please follow these steps:**

{% stepper %}
{% step %}
### Privately disclose the issue

Email us at [jackjburleson@proton.me](mailto:jackjburleson@proton.me) or contact a maintainer directly. Avoid creating public GitHub issues for vulnerabilities.
{% endstep %}

{% step %}
### Include details

* Affected files and versions
* Steps to reproduce
* Any relevant logs or screenshots
* Your suggested mitigation or patch (if available)
{% endstep %}

{% step %}
### We will

* Respond within 2 business days
* Triage and validate the report
* Release a fix as quickly as possible
* Credit you (with permission) after a public disclosure
{% endstep %}
{% endstepper %}

***

## Production Security Hardening

For production deployments, we strictly recommend the following hardening measures:

### Network Security

* **TLS/SSL**: Enforce HTTPS for all services. Use HSTS headers.
* **Firewall**: Restrict inbound traffic to port 443 (HTTPS) and 80 (HTTP redirect).
* **VPC**: Run backend services (Databases, Vector Stores) in private subnets.

### Application Security

* **Secrets Management**: Do not store secrets in code or Docker images. Use environment variables or a secrets manager (e.g., AWS Secrets Manager, HashiCorp Vault).
* **Rate Limiting**: Implement strict rate limiting on all API endpoints, especially those triggering expensive LLM calls.
* **Input Validation**: Sanitize all user inputs to prevent Injection and XSS attacks.

### Container Security

* **Non-Root**: Run all containers as a non-root user.
* **Image Scanning**: Scan Docker images for vulnerabilities before deployment (e.g., using Trivy).
* **Minimal Base Images**: Use Alpine or distroless images to reduce the attack surface.

See [Production Hardening Guide](/broken/pages/111d11b89ef8baf9fc2924ceb05d2376e9f6c858) for detailed instructions.

***

## Monitoring and Incident Response

### Security Monitoring

* **Logs**: Centralize logs and monitor for suspicious patterns (e.g., repeated 401/403 errors).
* **Alerts**: Set up alerts for high error rates, unusual traffic spikes, or unauthorized access attempts.
* **Dependency Scanning**: Enable GitHub Dependabot or similar tools to monitor dependencies for CVEs.

### Incident Response Plan

{% stepper %}
{% step %}
### Identify

Confirm the breach or vulnerability.
{% endstep %}

{% step %}
### Contain

Isolate affected systems (e.g., take container offline).
{% endstep %}

{% step %}
### Eradicate

Patch the vulnerability or remove malicious artifacts.
{% endstep %}

{% step %}
### Recover

Restore systems from clean backups.
{% endstep %}

{% step %}
### Review

Conduct a post-mortem and update security policies.
{% endstep %}
{% endstepper %}

***

## Security Best Practices

### For Users

* **Keep up-to-date**: Always use the latest release.
* **Verify downloads**: Check for sha256 signatures when available.
* **Never share sensitive credentials** in issues, PRs, or chat logs.
* **Review third-party dependencies**: This repo uses several. Monitor for CVEs and update dependencies regularly.

### For Contributors

* **Sign your commits** ([Guide](https://docs.github.com/en/authentication/managing-commit-signature-verification/signing-commits)):

{% code title="Enable commit signing" %}
```bash
git config --global commit.gpgsign true
```
{% endcode %}

\- \*\*Do not include secrets\*\* (API keys, tokens) in code, configs, or docs. - \*\*Add unit/integration tests\*\* for all security fixes. - \*\*Run static analysis\*\* and linters before submitting code. - \*\*Lockdown GitHub Actions\*\*: Reference only trusted actions, pin to a specific commit SHA. - \*\*Follow the Principle of Least Privilege\*\* in all scripts and integrations.

***

## Third-Party Dependencies

This repository makes use of open-source tools and packages (see `requirements.txt` and `package.json`).

* Review the dependencies for newly announced vulnerabilities
* Use `pip-audit` and `npm audit`
* Managed dependencies are periodically updated by maintainers

***

## Security Contact

* Email: [jackjburleson@proton.me](mailto:jackjburleson@proton.me)
* Or contact a maintainer privately

***

Thank you for helping keep the project and its users secure!
