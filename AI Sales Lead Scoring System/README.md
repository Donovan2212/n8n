# AI Sales Lead Scoring Systeem (n8n)

Een end-to-end **AI-gedreven sales lead scoring systeem**, gebouwd met **n8n**, met focus op **zakelijke logica, uitlegbaarheid en schaalbaarheid**.

Dit project laat zien hoe AI praktisch kan worden ingezet in salesprocessen, zonder dat het een ondoorzichtige “black box” wordt.

---

## 🚀 Wat doet dit project?

Het systeem:
- Ontvangt automatisch nieuwe leads via een webhook
- Schoont en normaliseert leaddata
- Verrijkt leads met zakelijke context
- Analyseert sales-intentie (mock AI-laag)
- Kent een transparante score toe (0–100)
- Classificeert leads als **Hot / Warm / Cold**
- Activeert duidelijke vervolgstappen voor sales

---

## 🧠 Waarom is dit project sterk?

In plaats van AI blind beslissingen te laten nemen:
- Combineert dit systeem **AI-inzichten met expliciete business rules**
- Is elke score **uitlegbaar en controleerbaar**
- Sluit het aan op hoe echte sales- en CRM-processen werken

Deze aanpak wordt veel gebruikt in **enterprise automation**, **CRM-systemen** en **sales operations**.

---

## 🏗️ Architectuur overzicht

De workflow is opgebouwd als een lineaire, modulaire n8n-pipeline.
Elke node heeft één duidelijke verantwoordelijkheid.

De architectuur bestaat uit de volgende stappen:

1. Webhook – Lead intake
- Ontvangt nieuwe sales leads via een HTTP POST
- Functioneert als entry-point van het systeem
- Simuleert een formulier, CRM of marketingtool

2. Normalize Lead Data – Datacleaning
- Normaliseert inkomende leaddata
- Zorgt voor consistente veldnamen en datatypes
- Verwijdert ruis en ongeldige input

3. Mock Data Enrichment – Context toevoegen
- Verrijkt de lead met aanvullende (gesimuleerde) zakelijke context
- Bijvoorbeeld: bedrijfstype, rol of leadbron
- Bereidt data voor op analyse

4. AI Message Node – Bewust gedeactiveerd
- Deze node is aanwezig als AI-integratiepunt
- In de huidige versie gedeactiveerd
- Laat zien waar AI later kan worden toegevoegd zonder refactor

5. Mock AI Analysis – Rule-based analyse
- Analyseert sales-intentie met vaste logica
- Simuleert AI-achtig redeneergedrag
- Volledig transparant en uitlegbaar

6. Lead Scoring – Scoreberekening
- Kent een numerieke score toe (0–100)
- Gebaseerd op vooraf gedefinieerde business rules
- Elke score is reproduceerbaar

7. Lead Classification – Segmentatie
- Classificeert leads als Hot, Warm of Cold
- Op basis van score-drempels
- Sluit aan op sales workflows

8. Lead Actions – Acties voor sales
- Activeert vervolgstappen
- Bijvoorbeeld: markeren voor opvolging of doorsturen
- Eindpunt van de workflow

