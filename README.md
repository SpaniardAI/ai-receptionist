# AI Receptionist

A bilingual AI receptionist for answering calls, qualifying leads, and automating follow-up workflows.

## Project status

Currently under development. The first prototype is Andrea, a Spanish-speaking AI receptionist for AFP Seguros.

## Planned capabilities

- Answer inbound calls in Spanish and English
- Understand customer questions
- Qualify insurance leads
- Collect contact information
- Transfer calls to a human
- Trigger automated follow-up workflows
- Connect with CRM, email, calendar, and WhatsApp
- Generate call summaries and structured lead data

## Architecture

Caller → Telephony provider → Retell AI → n8n → Business systems

## Current technology

- Retell AI for the voice agent
- n8n for workflow automation
- Telnyx or another SIP provider for telephony
- Python for custom backend services
- OpenAI models where required

## Repository structure

- `docs/` — Architecture and setup documentation
- `prompts/` — Voice-agent prompts
- `src/` — Application source code
- `tests/` — Automated tests
- `integrations/retell/` — Retell configurations
- `integrations/n8n/` — Sanitized n8n workflows
- `integrations/telephony/` — Telephony integration documentation

## Security

Credentials and customer information must never be committed to this repository. Use local environment variables for API keys and other secrets.