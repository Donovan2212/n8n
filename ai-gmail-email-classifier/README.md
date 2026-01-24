# AI Gmail Email Classifier & Auto-Responder (n8n)

This project is an AI-powered Gmail inbox automation built with **n8n** and **OpenAI**.

It automatically classifies incoming emails and routes them into the correct workflow based on content and confidence.

---

## 🚀 What it does

- Listens for new incoming Gmail emails
- Extracts sender, subject, and body
- Uses OpenAI to classify emails into exactly one category:
  - Sales
  - Support
  - HR
  - Other
- Returns a confidence score
- Routes emails using conditional logic (IF + Switch)
- Designed to be extended with:
  - Gmail labels
  - Auto-replies
  - CRM or ticketing systems

---

## 🧠 How it works (high level)

1. **Gmail Trigger** detects a new email
2. **Gmail Get Message** retrieves full email content
3. **JavaScript node** cleans and normalizes the email text
4. **OpenAI** classifies the email and returns JSON:
   ```json
   {
     "category": "Support",
     "confidence": 0.85
   }
