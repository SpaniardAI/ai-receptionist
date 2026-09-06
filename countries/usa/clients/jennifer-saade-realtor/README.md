\# Jennifer Saade Realtor AI Receptionist



AI-powered telephone receptionist and lead-intake system for Jennifer Saade’s real estate business in the United States.



\## Purpose



The system answers incoming calls, identifies the caller’s needs, gathers structured lead information, and sends the information to the appropriate business systems.



Andrea, the virtual receptionist, can assist callers in English or Spanish.



\## Primary Use Cases



\* Buyer lead intake

\* Seller lead intake

\* Property and MLS inquiries

\* Appointment requests

\* Callback requests

\* Urgent-call identification

\* Bilingual English and Spanish assistance

\* Lead qualification and prioritization

\* Automated notifications and follow-up



\## System Architecture



1\. A caller contacts Jennifer’s business telephone number.

2\. Twilio handles the telephone connection.

3\. Retell AI runs Andrea’s voice conversation.

4\. Andrea collects and validates the caller’s information.

5\. Retell sends the call data to an automation webhook.

6\. Make or n8n processes and routes the data.

7\. Lead information is sent to:



&#x20;  \* Google Sheets

&#x20;  \* Outlook

&#x20;  \* WhatsApp

&#x20;  \* HubSpot

&#x20;  \* KW Command, when access becomes available

8\. The workflow records whether each integration succeeded or failed.



\## Technologies



| Technology    | Purpose                                                 |

| ------------- | ------------------------------------------------------- |

| Retell AI     | Voice agent and conversation management                 |

| Twilio        | Telephone numbers and call routing                      |

| Make          | Initial webhook and automation testing                  |

| n8n           | Workflow automation and future self-hosted integrations |

| Google Sheets | Temporary lead database and testing                     |

| Outlook       | Email notifications                                     |

| WhatsApp      | Immediate lead notifications and follow-up              |

| HubSpot       | CRM and lead management                                 |

| KW Command    | Jennifer’s final real estate CRM                        |

| GitHub        | Version control and project documentation               |



\## Project Structure



```text

jennifer-saade-realtor/

├── prompts/        Retell agent prompts and conversation instructions

├── retell/         Sanitized Retell configuration and documentation

├── n8n/            Exported n8n workflows and workflow documentation

├── twilio/         Telephone configuration and routing documentation

├── integrations/   CRM, email, Sheets, WhatsApp, and webhook mappings

├── tests/          Test scenarios and results

├── README.md       Project overview and architecture

├── STATUS.md       Current progress and pending work

└── CHANGELOG.md    Chronological record of project changes

```



\## Lead Data



The system may collect:



\* Caller name

\* Callback number

\* Email address

\* Caller type

\* Reason for calling

\* Property address or MLS number

\* Preferred area

\* Budget or price range

\* Bedrooms and bathrooms

\* Purchase or sale timeframe

\* Financing status

\* Existing agent relationship

\* Preferred callback time

\* Appointment request

\* Requested appointment time

\* Urgency status and reason

\* Lead priority

\* Call language



\## Environments



\### Testing



Testing may temporarily use Ramon’s:



\* Google account

\* Google Sheets

\* Outlook account

\* WhatsApp account

\* Automation connections



\### Production



Before launch, the system must be moved to Jennifer’s accounts and approved production environment.



Testing and production credentials must remain separate.



\## Security Rules



Never commit the following to GitHub:



\* API keys

\* Authentication tokens

\* Passwords

\* Twilio Auth Tokens

\* Retell API keys

\* Webhook secrets

\* OAuth credentials

\* Customer or caller personal information

\* Complete unredacted call transcripts

\* Production phone numbers when confidentiality is required



Secret values must be stored in approved credential managers or environment variables.



The repository may contain `.env.example` files showing variable names, but never real values.



\## Documentation Rules



Every major configuration change should be recorded in `CHANGELOG.md`.



Current progress, blockers, and pending work should be maintained in `STATUS.md`.



Exported workflows must be reviewed and sanitized before being committed because workflow exports can contain credentials, webhook URLs, account identifiers, or customer information.



\## Current Status



See \[STATUS.md](STATUS.md) for current progress and remaining work.



