## Probleem:

Bij het handmatig screenen van sollicitaties kost het HR-teams veel tijd om elk CV te lezen, te beoordelen, en een passende reactie te sturen — zeker bij grote aantallen sollicitanten.

## Oplossing:

**Deze workflow automatiseert het volledige CV-screeningsproces:**

1. Een kandidaat uploadt zijn/haar CV via een online formulier
2. De workflow leest automatisch de tekst uit het PDF-bestand
3. Een lokaal AI-model (Ollama, Qwen3) analyseert het CV tegen de functie-eisen en genereert een samenvatting, sterke punten, en een match-score

**Op basis van de score routeert het systeem automatisch:**

1. Sterke match → automatische uitnodiging met gepersonaliseerde interviewvragen, plus interne notificatie naar HR
2. Twijfelgeval → notificatie naar een recruiter voor handmatige beoordeling
3. Geen match → nette, automatische afwijzing
4. Elke sollicitatie wordt gelogd in een overzicht (Google Sheets) voor rapportage
5. De workflow bevat ingebouwde foutafhandeling: als een CV niet leesbaar is (bv. een gescande afbeelding zonder tekst), wordt dit automatisch gemeld in plaats van de kandidaat te negeren
