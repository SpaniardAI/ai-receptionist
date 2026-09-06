\# Retell AI Conversation Flow



Agent: Andrea EN — Jennifer Saade — Production

Platform: Retell AI

Market: Eagle Pass, Texas, USA

Languages: English and Spanish



\## Overview



Andrea answers the call in English, offers Spanish assistance, identifies the caller’s intent, sends the caller through the appropriate intake path, confirms the collected details, and ends the call.



Spanish-speaking callers are routed to the Spanish agent flow.



\## Flow Diagram



```mermaid

flowchart TD

&#x20;   A\[Begin] --> B\[Welcome \& Language Check]

&#x20;   B -->|Spanish| C\[Spanish Agent Transfer]

&#x20;   B -->|English| D\[Identify Caller \& Intent]



&#x20;   D --> E\[Buyer Intake]

&#x20;   D --> F\[Seller Intake]

&#x20;   D --> G\[Renter Intake]

&#x20;   D --> H\[Landlord Intake]

&#x20;   D --> I\[Investor Intake]

&#x20;   D --> J\[Existing Client Message]

&#x20;   D --> K\[Professional \& Transaction Partner]

&#x20;   D --> L\[General Message \& Other]



&#x20;   E --> M\[Confirm Details]

&#x20;   F --> M

&#x20;   G --> M

&#x20;   H --> M

&#x20;   I --> M

&#x20;   J --> M

&#x20;   K --> M

&#x20;   L --> M



&#x20;   M --> N\[Final Goodbye]

&#x20;   N --> O\[End Call]

```



\## Nodes



\### 1. Begin



Entry point for every incoming call.



Transitions automatically to `Welcome \& Language Check`.



\### 2. Welcome \& Language Check



Greets the caller, identifies Andrea as Jennifer Saade’s virtual assistant, and offers assistance in Spanish.



Transitions:



\* Spanish detected or requested → `Spanish Agent Transfer`

\* Otherwise → `Identify Caller \& Intent`



\### 3. Spanish Agent Transfer



Routes Spanish-speaking callers to the Spanish-language Retell agent or workflow.



The Spanish workflow should preserve the same intake categories, safety rules, and lead fields used in the English workflow.



\### 4. Identify Caller \& Intent



Determines the caller’s primary reason for calling.



Supported caller types include:



\* Prospective buyer

\* Prospective seller

\* Prospective renter

\* Landlord

\* Investor

\* Existing client

\* Real estate agent

\* Lender

\* Title-company representative

\* Inspector

\* Vendor

\* Other caller



Transitions to the intake or message node corresponding to the caller’s intent.



\### 5. Buyer Intake



Collects buyer information naturally, one question at a time.



Information collected:



\* Full name

\* Best callback number

\* Email address

\* Specific property or MLS number, when applicable

\* Preferred location

\* Approximate price range

\* Desired bedrooms and bathrooms

\* Purchase timeframe

\* Financing status

\* Whether the caller is working with another agent



High-priority indicators include:



\* Purchase timeframe of one to three months

\* Mortgage pre-approval

\* Cash purchase



Transitions to `Confirm Details`.



\### 6. Seller Intake



Collects:



\* Full name

\* Best callback number

\* Email address

\* Property address

\* Property type

\* Bedrooms and bathrooms

\* Intended selling timeframe

\* Preferred callback time



High-priority indicators include sellers who are ready to list or plan to sell within one to three months.



Transitions to `Confirm Details`.



\### 7. Renter Intake



Collects:



\* Full name

\* Best callback number

\* Email address

\* Specific property, when applicable

\* Preferred area

\* Monthly rental budget

\* Desired bedrooms

\* Desired move-in timeframe



Transitions to `Confirm Details`.



\### 8. Landlord Intake



Collects:



\* Full name

\* Best callback number

\* Email address

\* Property address

\* Property type

\* Description of the assistance needed

\* Preferred callback time



Transitions to `Confirm Details`.



\### 9. Investor Intake



Collects:



\* Full name

\* Best callback number

\* Email address

\* Property or investment type

\* Preferred area

\* Approximate budget or price range

\* Investment timeframe

\* Financing status

\* Specific property address or MLS number, when applicable



Transitions to `Confirm Details`.



\### 10. Existing Client Message



Handles existing clients without repeating the complete new-lead qualification process.



Collects:



\* Full name

\* Best callback number

\* Property address or transaction involved

\* Reason for calling

\* Whether the matter is time-sensitive

\* Preferred callback time



Transitions to `Confirm Details`.



\### 11. Professional \& Transaction Partner



Handles calls from:



\* Real estate agents

\* Lenders

\* Title-company representatives

\* Inspectors

\* Vendors

\* Other transaction partners



Collects:



\* Full name

\* Company name

\* Professional role

\* Best callback number

\* Email address, when appropriate

\* Property address or transaction involved

\* Reason for calling

\* Whether the matter is time-sensitive



Transitions to `Confirm Details`.



\### 12. General Message \& Other



Handles callers who do not fit another intake path.



Collects:



\* Full name

\* Best callback number

\* Email address, when appropriate

\* Reason for calling

\* Property address, when relevant

\* Preferred callback time

\* Whether the matter is time-sensitive



Spam, telemarketing, robocalls, and unrelated solicitations should be declined politely.



Valid callers transition to `Confirm Details`.



\### 13. Confirm Details



This is the only workflow node permitted to provide the final recap.



Responsibilities:



\* Validate that a US callback number contains exactly 10 digits, excluding an optional leading country code of 1

\* Ask the caller to repeat incomplete or unclear numbers

\* Read a valid callback number back once

\* Summarize the reason for the call

\* Confirm the caller’s name and callback number

\* Confirm relevant property and appointment information

\* Apply corrections requested by the caller

\* Explain that Jennifer will follow up



Transitions to `Final Goodbye` once the caller confirms the information.



\### 14. Final Goodbye



Thanks the caller for contacting Jennifer Saade and explains that Jennifer will follow up as soon as possible.



Transitions to `End Call` without waiting for an additional caller response.



\### 15. End Call



Terminates the Retell call.



\## Important Constraints



\* Ask only one question at a time.

\* Do not repeat information already provided.

\* Do not independently confirm listing information.

\* Do not promise that an appointment is booked without an active calendar integration.

\* Do not provide legal, financial, tax, lending, appraisal, inspection, or contract advice.

\* Do not violate Fair Housing requirements.

\* Do not claim that Andrea is human.

\* Do not transfer calls until live call transfers are configured.

\* Only the confirmation node may provide the final recap.



\## Known Documentation Issue



The Global Prompt refers to the closing node as `Confirm Details \& Close`, while the Retell workflow currently names it `Confirm Details`.



The node name and Global Prompt reference should be standardized to prevent ambiguity.



\## Future Improvements



\* Activate calendar availability checking and appointment booking.

\* Add live call transfers.

\* Verify Spanish-agent parity with the English workflow.

\* Add integration-failure handling.

\* Add test coverage for every transition.

\* Version exported Retell configurations when export support is available.



