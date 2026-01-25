AI Gmail E-mail Classifier & Auto-Responder (n8n)
Dit project is een AI-gestuurde Gmail-inboxautomatisering, gebouwd met n8n en OpenAI.
Het systeem classificeert automatisch binnenkomende e-mails en stuurt ze door naar de juiste workflow op basis van inhoud en betrouwbaarheid (confidence).
🚀 Wat doet het?
Luistert naar nieuwe binnenkomende Gmail-e-mails
Haalt afzender, onderwerp en inhoud op
Gebruikt OpenAI om elke e-mail in exact één categorie te classificeren:
Sales
Support
HR
Overig
Geeft een confidence score terug
Routeert e-mails met conditionele logica (IF + Switch)
Ontworpen om eenvoudig uit te breiden met:
Gmail-labels
Automatische antwoorden
CRM- of ticketsystemen
🧠 Hoe werkt het? (hoog niveau)
Gmail Trigger detecteert een nieuwe e-mail
Gmail Get Message haalt de volledige e-mailinhoud op
JavaScript-node schoont en normaliseert de e-mailtekst
OpenAI classificeert de e-mail en retourneert JSON:
{
  "category": "Support",
  "confidence": 0.85
}

## 🎯 Doel van dit project
Dit project is gebouwd om te laten zien hoe AI kan worden ingezet
voor e-mailautomatisering, classificatie en workflow-routing in n8n.
