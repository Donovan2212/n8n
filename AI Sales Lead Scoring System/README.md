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

## 🏗️ Architectuuroverzicht

De workflow is opgebouwd als een lineaire en modulaire n8n-pipeline.  
Elke node heeft één duidelijke verantwoordelijkheid binnen het proces.

De architectuur bestaat uit de volgende stappen:

### 1. Webhook – Leadontvangst
- Ontvangt nieuwe salesleads via een HTTP POST-verzoek  
- Functioneert als het startpunt van het systeem  
- Simuleert een formulier, CRM-systeem of marketingtool  

### 2. Normalize Lead Data – Datacleaning
- Normaliseert de binnenkomende leaddata  
- Zorgt voor consistente veldnamen en datatypes  
- Verwijdert ongeldige of onvolledige invoer  

### 3. Mock Data Enrichment – Context toevoegen
- Verrijkt de lead met aanvullende (gesimuleerde) zakelijke context  
- Bijvoorbeeld: type bedrijf, functie of leadbron  
- Bereidt de data voor op verdere analyse  

### 4. AI Message Node – Bewust gedeactiveerd
- Deze node is aanwezig als toekomstig AI-integratiepunt  
- In de huidige versie bewust gedeactiveerd  
- Laat zien waar AI later kan worden toegevoegd zonder de workflow te herstructureren  

### 5. Mock AI Analysis – Regelgebaseerde analyse
- Analyseert salesintentie op basis van vaste regels  
- Simuleert AI-achtig redeneergedrag zonder gebruik van een echt model  
- Volledig transparant en uitlegbaar  

### 6. Lead Scoring – Scoreberekening
- Kent een numerieke score toe van 0 tot 100  
- Gebaseerd op vooraf gedefinieerde businessregels  
- Elke score is reproduceerbaar en controleerbaar  

### 7. Lead Classification – Segmentatie
- Classificeert leads als **Hot**, **Warm** of **Cold**  
- Op basis van vastgestelde score-drempels  
- Sluit aan op gangbare salesprocessen  

### 8. Lead Actions – Acties voor sales
- Activeert vervolgstappen voor het salesteam  
- Bijvoorbeeld: markeren voor opvolging of doorsturen naar een CRM  
- Vormt het eindpunt van de workflow  

---

*Deze architectuur is bewust opgezet met focus op duidelijkheid en uitlegbaarheid,  
zodat het systeem geschikt is voor zowel technische als niet-technische stakeholders.*


