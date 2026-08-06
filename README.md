# FlowForge-Ava-AI-Lead-Operating-System
FlowForge Ava is a production-ready AI lead operating system for WhatsApp. It qualifies leads, maintains conversation memory, books meetings, syncs with Airtable CRM, hands off to humans with context, and automates follow-ups—helping businesses convert conversations into customers.

![n8n](https://img.shields.io/badge/n8n-workflow-EA4B71?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-containerized-2496ED?style=flat-square)
![Groq](https://img.shields.io/badge/Groq-Llama%203.3%2070B-F55036?style=flat-square)
![WhatsApp](https://img.shields.io/badge/WhatsApp-Business%20API-25D366?style=flat-square)
![Airtable](https://img.shields.io/badge/Airtable-CRM-18BFFF?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

# FlowForge AVA

**A production-ready multi-agent AI system that automates WhatsApp lead qualification, customer support, CRM synchronization, and appointment booking.**

---

## Table of Contents

- [Problem](#problem)
- [Solution](#solution)
- [Business Impact](#business-impact)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [Workflow](#workflow)
- [Tech Stack](#tech-stack)
- [Engineering Decisions](#engineering-decisions)
- [Engineering Challenges](#engineering-challenges)
- [System Characteristics](#system-characteristics)
- [Future Improvements](#future-improvements)

## Problem

Businesses lose qualified WhatsApp leads because replies are slow, follow-ups are inconsistent, and manual qualification doesn't scale.

## Solution

FlowForge AVA replaces manual WhatsApp lead handling with a coordinated system of four AI agents. Incoming messages are routed through an **Orchestrator Agent** to specialized agents for **Q&A**, **Scheduling**, and **CRM** — qualifying leads, answering questions, and booking meetings automatically, with a clean handoff to a human whenever the conversation actually needs one.

## Business Impact

- Allows sales teams to focus on qualified prospects instead of repetitive conversations
- Ensures every lead receives a consistent qualification experience regardless of time or staff availability
- Automates first-response handling to eliminate manual response delays
- Removes manual data entry between chat, CRM, and calendar

## Key Features

- 🎯 AI lead qualification
- 🧠 Conversation memory across the full interaction
- 🤝 Human handoff when it matters
- 🔄 CRM synchronization
- 📅 Calendar booking
- 💬 WhatsApp automation
- 🔔 Admin notifications

## Architecture

<p align="center">
<img src="assets/architecture.png" width="900">
</p>

## Workflow

1. Customer sends WhatsApp message
2. Webhook validates payload
3. Orchestrator analyzes intent
4. Specialist agent selected (Q&A / Scheduling / CRM)
5. Memory updated
6. CRM synchronized
7. Meeting booked
8. Admin notified

## Tech Stack

| Layer | Tool |
|---|---|
| Orchestration | n8n |
| AI Inference | OpenAI GPT-4.1 |
| Messaging | WhatsApp Business API |
| CRM / Data | Airtable |
| Scheduling | Google Calendar |
| Deployment | Docker |

## Engineering Decisions

**Why n8n over a code-first framework like LangGraph?** n8n gives fast iteration on multi-agent orchestration and visual debugging of the flow, which matters when you're tuning routing logic constantly. The tradeoff is less flexibility than a pure-code framework — acceptable given the pace of iteration needed.

**Why OpenAI GPT-4.1?**
GPT-4.1 was chosen for its strong instruction following, reliable function calling, and consistent performance in multi-step conversational workflows. These capabilities are critical for orchestrating specialized agents, preserving context, and handling lead qualification with predictable behavior.

**Why Airtable over a traditional database?** Airtable provides a lightweight CRM with an intuitive interface, allowing non-technical business teams to view, update, and manage leads without requiring a custom dashboard. It also integrates seamlessly with n8n, enabling rapid iteration while keeping operational complexity low.

**Why WhatsApp Business API?** For many businesses, WhatsApp is already the primary communication channel for inbound leads. Building directly on that channel removes friction, requires no additional app downloads, and lets customers interact on a platform they already trust.

## Engineering Challenges

**Agent routing accuracy.** With four agents sharing one conversation, the hardest problem wasn't building each agent — it was getting the Orchestrator to reliably decide which agent should handle a given message. A lead asking *"how much does this cost, and can we do 3pm Thursday?"* is both a Q&A question and a scheduling request in the same sentence.

**Conversation memory across agent handoffs.** Each agent needed to know what the others had already said, without re-sending the full conversation history on every call and blowing up latency and cost. Getting memory to persist correctly across a handoff — say, from Q&A to Scheduling — without the lead having to repeat themselves, took real iteration.

**Keeping responses fast on WhatsApp.** A chat feels broken the moment replies lag. Running everything through Groq's Llama 3.3 70B was a deliberate tradeoff — prioritizing the low-latency inference that a real-time conversation demands.

**Human handoff without losing context.** Deciding *when* an AI-handled conversation should escalate to a human, and making sure that human doesn't have to scroll through a wall of history to catch up.

**Reliability.** Current version focuses on conversation quality and orchestration. Robust retry logic, circuit breakers, and fallback handling for upstream API failures are planned for the next iteration to improve production resilience.

## Lessons Learned

Building the individual agents was straightforward. Designing reliable coordination between them was significantly harder. Most of the engineering effort went into routing decisions, preserving conversational context across handoffs, and balancing latency against reasoning quality.

## System Characteristics

- Coordinates 4 specialized AI agents
- Maintains persistent conversation memory
- Supports automated CRM synchronization
- Fully containerized deployment using Docker

## Repository Structure

.
├── workflow/
├── docs/
├── assets/
├── README.md
└── LICENSE


## Future Improvements

1. Retry logic and circuit breakers for upstream API failures
2. Monitoring and logging for production visibility
3. Analytics dashboard: qualification rate, booking rate, drop-off points
4. Multi-language support for non-English-speaking leads
5. Additional CRM integrations
6. Sentiment detection to flag frustrated leads for immediate human handoff

## Disclaimer

This project was built as a production-oriented portfolio project to demonstrate multi-agent workflow orchestration, AI integration, and business process automation. API credentials and sensitive configuration have been removed before publication.

---

Designed and engineered by

**Oyekola Ololade**

AI Systems & Integration Engineer

Passionate about designing intelligent business systems that combine AI, automation, and cloud technologies.

- LinkedIn: https://www.linkedin.com/in/ololade-oyekola-5b1797397/
- Portfolio: Coming soon
- Email: oyekolaololade6982@gmail.com
