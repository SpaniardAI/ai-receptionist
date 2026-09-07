# Retell-to-n8n Webhook Payload



## Purpose



This document defines the Retell post-call webhook structure received by n8n for Jennifer Saade’s AI receptionist.



The corresponding sanitized example is stored in `sample-payload.json`.



## Event



The workflow processes the following event:



- Event name: `call_analyzed`

- n8n path: `body.event`

- n8n expression: `{{ $json.body.event }}`



Other Retell events should not proceed through the post-call lead workflow.



## Main Payload Structure



```text

body

├── event

├── call

│   ├── call_id

│   ├── call_type

│   ├── agent_id

│   ├── agent_version

│   ├── agent_name

│   ├── collected_dynamic_variables

│   ├── call_status

│   ├── start_timestamp

│   ├── end_timestamp

│   ├── duration_ms

│   └── call_analysis

│       ├── call_summary

│       ├── in_voicemail

│       ├── user_sentiment

│       ├── call_successful

│       └── custom_analysis_data

└── event_timestamp

