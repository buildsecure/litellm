# Data Privacy and Security (WIP)

## Security Measures

### LiteLLM Github

- All commits run through Github's CodeQL checking

### Self-hosted Instances LiteLLM

- **No data or telemetry is stored on LiteLLM Servers when you self host**
- For installation and configuration, see: [Self-hosting guided](https://docs.litellm.ai/docs/proxy/deploy)
- **Telemetry** We run no telemetry when you self host LiteLLM


:::info
✨ SSO is free for up to 5 users. After that, an enterprise license is required. [Get Started with Enterprise here](https://www.litellm.ai/enterprise)
:::

### LiteLLM Cloud

- We encrypt all data stored using your `LITELLM_MASTER_KEY` and in transit using TLS.
- Our database and application run on GCP, AWS infrastructure, partly managed by NeonDB.
    - US data region: Northern California (AWS/GCP `us-west-1`) & Virginia (AWS `us-east-1`)
    - EU data region Germany/Frankfurt (AWS/GCP `eu-central-1`)
- All users have access to SSO (Single Sign-On) through OAuth 2.0 with Google, Okta, Microsoft, KeyCloak. 
- Audit Logs with retention policy
- Control Allowed IP Addresses that can access your Cloud LiteLLM Instance

For security inquiries, please contact us at support@berri.ai

#### Supported data regions for LiteLLM Cloud

LiteLLM supports the following data regions:

- US, Northern California (AWS/GCP `us-west-1`)
- Europe, Frankfurt, Germany (AWS/GCP `eu-central-1`)

All data, user accounts, and infrastructure are completely separated between these two regions

### Security Vulnerability Reporting Guidelines

We value the security community's role in protecting our systems and users. To report a security vulnerability:

- Email support@berri.ai with details
- Include steps to reproduce the issue
- Provide any relevant additional information

We'll review all reports promptly. Note that we don't currently offer a bug bounty program.

### Security Checklist

Use this checklist to verify your LiteLLM deployment meets security best practices:

- [ ] `LITELLM_MASTER_KEY` is set to a strong, unique secret and not exposed in version control
- [ ] All API keys are stored as environment variables, not hardcoded in config files
- [ ] TLS/HTTPS is enabled for all endpoints (proxy and any upstream services)
- [ ] Database credentials are rotated regularly and access is restricted by IP
- [ ] SSO is configured and direct password-based login is disabled where possible
- [ ] Allowed IP address restrictions are configured for your LiteLLM Cloud or self-hosted instance
- [ ] Audit logs are enabled and retention policy is set according to your compliance requirements
- [ ] Dependency updates and security patches are applied regularly
- [ ] CodeQL or equivalent static analysis is enabled on your fork/deployment pipeline
- [ ] Access to the admin UI and management endpoints is restricted to authorized personnel only
