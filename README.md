# AI Sales Operations Agent

An AI-powered automation agent that analyzes sales leads and decides which ones need follow-up — fully automated.

## What it does

- Fetches leads from CRM (Pipedrive/HubSpot/mock data)
- AI analyzes each lead individually
- Decides: action needed yes/no, priority level, suggested action
- Logs all results to Supabase/PostgreSQL
- Runs on a schedule — no manual input needed

## Why this matters

This is not a chatbot. It's an autonomous AI agent that makes decisions and takes actions without human input. Sales teams no longer need to manually go through their CRM every morning.

## Stack

- **n8n** — workflow orchestration
- **OpenAI GPT-4o-mini** — AI decision making
- **Supabase (PostgreSQL)** — results logging
- **Pipedrive API** — CRM data source (replaceable with any CRM)

## Architecture

Schedule Trigger (every morning 9:00)
→ Fetch leads from CRM
→ AI Agent analyzes each lead
→ Parse structured JSON response
→ Log to Supabase
→ Output summary

## Output per lead

- `lead_id` — identifier
- `action_needed` — true/false
- `priority` — high/medium/low
- `reason` — AI explanation
- `suggested_action` — what to do next

## Status

✅ Working with mock data  
🔜 Connecting to real CRM (Pipedrive)  
🔜 Schedule Trigger for daily automation  
🔜 Slack/email notification for priority leads
