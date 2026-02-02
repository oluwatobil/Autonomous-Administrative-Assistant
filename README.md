# Autonomous Admin Assistant: n8n + GPT-4o-mini

This repository contains the logic for an autonomous agent I built to handle the "lookup and book" cycle of administrative work. By connecting a reasoning engine to my actual tools, I've created a system that doesn't just chat, but actually executes tasks across my database and inbox.

## Why I Built This
Administrative friction is a major bottleneck in project management. I wanted to see if I could use **LLM Orchestration** to bridge the gap between a static **Google Sheets** contact list and active **Gmail** communication without manual data entry.

## How the Logic Works
Unlike a standard linear automation, this agent uses a **"Chain of Thought"** approach:
* **Triage**: The agent reads the request and decides what information is missing.
* **Database Query**: It autonomously searches my **Google Sheets** "Single Source of Truth" to find verified emails.
* **Memory**: It remembers the context of the conversation using **Window Buffer Memory**, so it can handle follow-up edits easily.
* **Professional Output**: It drafts and sends a personalized message via **Gmail**, ensuring the tone is always concise and professional.

## Strategic Impact & ROI
Beyond the technical implementation, this project delivers measurable value to business operations:
* **Operational Efficiency**: Eliminates the cognitive load and time wasted switching between databases and inboxes, automating the end-to-end "Lookup-and-Send" cycle.
* **Data Integrity**: Maintains a "Single Source of Truth" by pulling directly from verified contact data, removing the risk of manual typing errors.
* **Scalable Presence**: Demonstrates how a single project manager can use AI as a "Force Multiplier" to handle high-volume correspondence without losing personal touch or professional standards.

## Technical Stack
* **Orchestration**: n8n
* **Reasoning**: OpenAI GPT-4o-mini
* **Data & Comms**: Google Sheets & Gmail APIs

## Implementation Notes
* **Standard Operating Procedure (SOP)**: The agent follows a specific protocol I wrote into the system message to ensure data integrity and tone consistency.
* **Tool Calling**: This setup demonstrates how to give an AI "hands" by connecting it to real-world APIs.
