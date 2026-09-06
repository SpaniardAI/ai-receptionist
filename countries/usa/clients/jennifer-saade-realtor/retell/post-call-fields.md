# Retell Post-Call Extraction Fields



Agent: Andrea EN - Jennifer Saade - Production  

Market: Eagle Pass, Texas, USA  

Extraction model: GPT-4.1



## Purpose



These fields form the data contract between Retell AI and downstream integrations such as n8n, Google Sheets, Outlook, WhatsApp, HubSpot, and KW Command.



Field names and selector values should not be changed without updating every connected workflow.



## Built-In Retell Fields



| Field | Type | Purpose |

|---|---|---|

| Call Summary | Text | Retell-generated summary of the call |

| Call Successful | Boolean | Indicates whether the call achieved its intended purpose |

| User Sentiment | Text | Retell-generated assessment of caller sentiment |



## Custom Fields



| Field | Type | Expected content |

|---|---|---|

| caller_name | Text | Caller’s full name |

| callback_number | Text | Confirmed callback number |

| email | Text | Caller’s email address, when provided |

| caller_type | Selector | Classification of the caller |

| reason_for_call | Text | Concise reason for the call |

| property_address_or_mls | Text | Property address or MLS number, when applicable |

| preferred_area | Text | Caller’s preferred location or area |

| budget_or_price_range | Text | Purchase, rental, sale, or investment range |

| bedrooms | Number | Desired or existing number of bedrooms |

| bathrooms | Number | Desired or existing number of bathrooms |

| timeframe | Text | Intended purchase, sale, rental, or investment timeframe |

| financing_status | Selector | Caller’s financing position |

| working_with_agent | Selector | Whether the caller is already represented |

| preferred_callback_time | Text | Preferred date or time for follow-up |

| appointment_requested | Boolean | Whether the caller requested an appointment |

| requested_appointment_time | Text | Requested appointment date and time |

| is_urgent | Boolean | Whether the matter requires urgent attention |

| urgency_reason | Text | Reason the call was classified as urgent |

| lead_priority | Selector | Lead-priority classification |

| call_language | Selector | Language used during the call |



## Selector Values



### caller_type



Allowed values:



- Buyer

- Seller

- Renter

- Landlord

- Investor

- Existing Client

- Real Estate Agent

- Lender

- Title Company

- Inspector

- Vendor

- Other



### financing_status



Allowed values:



- Pre-approved

- Cash

- Needs Lender

- Financing Not Confirmed

- Not Applicable



### working_with_agent



Allowed values:



- Yes

- No

- Unknown

- Not Applicable



### lead_priority



Allowed values:



- High

- Normal

- Low

- Spam



High-priority indicators include:



- Intends to buy, sell, rent, or invest within one to three months

- Pre-approved buyer

- Cash buyer

- Seller ready to list

- Urgent transaction matter



### call_language



Allowed values:



- English

- Spanish

- Mixed

- Unknown



## Field Handling Rules



- Keep telephone numbers as text so leading digits and formatting are not lost.

- Do not guess or repair incomplete telephone numbers.

- Use the exact selector values documented above.

- Preserve empty or unavailable information without inventing a value.

- Boolean fields should be transmitted as `true` or `false`.

- Number fields should contain numeric values when provided.

- Do not include API credentials or authentication tokens in extracted fields.

- Do not store real caller records in this GitHub repository.



## Integration Requirements



Every downstream integration must:



1. Accept the exact field names documented here.

2. Map selector values consistently.

3. Handle empty or unavailable fields.

4. Preserve the original Retell call ID for traceability.

5. Record the processing status and any integration error.

6. Avoid logging credentials or unnecessary caller information.

7. Use test data rather than real customer information during development.



## Change Control



If a field is renamed, removed, added, or given new selector values:



1. Update this document.

2. Update the Retell post-call extraction configuration.

3. Update the automation workflow.

4. Update Google Sheets and CRM mappings.

5. Update applicable tests.

6. Record the change in `CHANGELOG.md`.

