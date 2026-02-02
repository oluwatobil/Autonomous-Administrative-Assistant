# Autonomous Admin Assistant

An n8n workflow that handles the repetitive "find contact → draft email → send" cycle through a conversational interface.

Instead of switching between Google Sheets and Gmail manually, I can just tell it "email Bola about the project" and it figures out the rest.

## What It Does

You chat with the agent like you would a human assistant:

**Agent:** 
- Searches your Google Sheets contact database
- Finds Bola's email
- Drafts a professional message
- Sends it via Gmail

The agent maintains context throughout the conversation, so you can ask it to revise the message or add recipients without starting over.

## Why I Built This

I was spending too much time doing the same manual workflow:
1. Open Google Sheets
2. Search for contact
3. Copy email
4. Switch to Gmail  
5. Paste, write, send
6. Repeat multiple times daily

This collapses all of that into a single conversation.

## How It Works

The workflow uses GPT-4o-mini to:
- **Understand intent** - Figures out what information is missing from your request
- **Query autonomously** - Searches Google Sheets when it needs contact info
- **Maintain memory** - Remembers the conversation context using Window Buffer Memory
- **Execute professionally** - Drafts and sends emails with appropriate tone

It's not following a rigid script—it reasons through what needs to happen based on what you tell it.

## Tech Stack

- **n8n** - Workflow orchestration
- **OpenAI GPT-4o-mini** - Reasoning and decision-making
- **Google Sheets API** - Contact database
- **Gmail API** - Email sending

## Set Up
Import `AI_Support_Agent_2.json` into n8n and configure your OpenAI + Google credentials.

## What I Learned

The technical implementation was straightforward. The interesting challenge was designing the decision-making process—teaching it where to look for information, how to maintain professional tone, and what to validate before sending.

It's less about the tools and more about designing good workflows that an LLM can execute reliably.
* **Standard Operating Procedure (SOP)**: The agent follows a specific protocol I wrote into the system message to ensure data integrity and tone consistency.
* **Tool Calling**: This setup demonstrates how to give an AI "hands" by connecting it to real-world APIs.


