# AI-Powered Lead Qualification & Growth Automation

## Overview

This project is an AI-powered lead qualification and growth automation workflow built with **n8n** and **Ollama**.

The workflow receives lead information through a webhook, uses AI to analyze and score the lead, and automatically decides whether the lead should receive personalized outreach.

The goal is to demonstrate how AI can be combined with workflow automation to support lead qualification and marketing processes.

## Problem

Manually reviewing and qualifying leads can take time, especially when there are many incoming leads.

A company needs a way to:

* Analyze incoming leads
* Identify high-quality leads
* Prioritize leads based on their potential
* Create personalized outreach
* Avoid sending unnecessary messages to low-quality leads

## Solution

This workflow automates the process from **lead intake to outreach**.

A lead sends JSON data to the webhook. Ollama analyzes the lead and generates a lead score, temperature, intent and reason.

JavaScript processes the AI response and keeps the lead information available for the next steps.

An IF node then checks the lead score:

* **Score ≥ 70:** The lead is considered qualified and receives an AI-generated personalized outreach message.
* **Score < 70:** The lead is marked as not qualified and is not contacted automatically.

## Workflow

```text
Lead / External Source
        ↓
     Webhook
        ↓
  AI Lead Analysis
        ↓
 JavaScript Processing
        ↓
 Lead Qualification
        ↓
    ┌───┴────┐
    ↓        ↓
 TRUE       FALSE
    ↓        ↓
AI Outreach  Not Qualified
    ↓
JavaScript
    ↓
 Gmail
```

## Technologies

* **n8n** — Workflow automation
* **Ollama** — Local AI/LLM processing
* **JavaScript** — Data processing and JSON parsing
* **Webhooks** — Receiving lead data
* **JSON** — Data format
* **Gmail** — Automated outreach

## AI Lead Analysis

The first AI step analyzes the incoming lead and determines:

* **Lead score** — numerical qualification score
* **Temperature** — HOT / other classification
* **Intent** — estimated level of interest
* **Reason** — explanation for the score

Example:

```json
{
  "lead_score": 85,
  "temperature": "HOT",
  "intent": "high",
  "reason": "Strong interest in AI automation."
}
```

## Qualification Logic

The workflow uses a score threshold of **70**.

```text
Lead score >= 70
        ↓
     Qualified
        ↓
Personalized outreach
```

```text
Lead score < 70
        ↓
   Not qualified
        ↓
No automated outreach
```

## Personalized Outreach

Qualified leads are sent to a second AI step.

Ollama generates a short personalized outreach message based on the available lead information, such as:

* Name
* Company
* Role
* Interest
* Lead score

The generated message is then prepared and sent through Gmail.

## Test Cases

The workflow was tested with multiple fictional leads:

### Test 1 — Qualified Lead

A lead with strong interest in AI automation received a high score and followed the **TRUE** branch.

**Result:** Personalized outreach was generated and sent through Gmail.

### Test 2 — Not Qualified Lead

A lead with low interest received a score below the qualification threshold.

**Result:** The lead followed the **FALSE** branch and was marked as not qualified.

### Test 3 — Additional Test

An additional fictional lead was used to verify that the workflow could process different lead information and route the result correctly.

## What I Learned

Through this project I practiced:

* Building webhook-based automations
* Working with JSON data
* Connecting local LLMs with n8n
* Using Ollama for AI analysis
* Processing AI output with JavaScript
* Creating conditional workflow logic
* Generating personalized AI content
* Connecting automation workflows to Gmail
* Testing different workflow outcomes

## Project Structure

```text
AI-Powered-Lead-Growth-Automation/
│
├── AI-Powered Lead Growth Automation.json
├── workflow-screenshot.png
└── README.md
```

## Disclaimer

All lead data used in this project is fictional and created for testing and demonstration purposes.
