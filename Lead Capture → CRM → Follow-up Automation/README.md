# Lead Capture → CRM Workflow (n8n)

## Overzicht
Dit project automatiseert het vastleggen van leads met **n8n**.  
Binnenkomende leads via een websiteformulier worden automatisch opgeslagen in een CRM (Airtable) en er wordt direct een Slack-notificatie verstuurd naar het team.

Het project laat zien hoe webhook-based automatisering handmatig werk vervangt door een schaalbare workflow.

---

## Wat doet deze workflow?
- Ontvangt leads via een HTTP Webhook
- Normaliseert en verwerkt de data
- Slaat leads op in Airtable (CRM)
- Stuurt een real-time Slack notificatie

---

## Workflow-opzet

Websiteformulier
→ Webhook (n8n)
→ Edit Fields
→ Airtable (Create Record)
→ Slack (Incoming Webhook)

