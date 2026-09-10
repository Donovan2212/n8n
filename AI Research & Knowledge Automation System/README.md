## AI Research & Knowledge Automation System

Een n8n-workflow die een onderzoeksvraag van een gebruiker omzet in een goed onderbouwd, AI-gegenereerd antwoord. De workflow plant onderzoeksstappen, doorzoekt het web, slaat bevindingen op in een vectordatabase, en haalt relevante context op (RAG) om een onderbouwd eindantwoord te genereren.

## Overzicht

De workflow bestaat uit drie fasen:

1. Research Planning — ontvangt een vraag, valideert deze, en laat een AI-agent een onderzoeksplan opstellen.
2. Data Collection & Storage — doorzoekt het web naar informatie, maakt embeddings van de resultaten, en slaat deze op in een Supabase vectordatabase.
3. Answer Generation — haalt de meest relevante opgeslagen documenten op en gebruikt een tweede AI-agent (RAG) om het uiteindelijke antwoord te genereren, dat vervolgens wordt gevalideerd en teruggestuurd.

## Architectuur

Fase 1 — Research Planning
1. Receive Research Request — webhook die de onderzoeksvraag ontvangt
2. Input Validation — controleert of de binnenkomende data geldig is
3. Normalize Input — brengt de input naar een consistent formaat
4. AI Research Agent — genereert een onderzoeksplan, gebruikt Ollama Chat Model
5. Parse Research Plan — verwerkt het plan naar bruikbare zoekopdrachten

Fase 2 — Data Collection & Storage
6. Tavily Research API — doorzoekt het web op basis van het onderzoeksplan
7. API Response Validation — controleert de zoekresultaten
8. Store Documents and Embeddings — maakt embeddings en slaat documenten op, gebruikt Embeddings Ollama en Default Data Loader
9. Prepare Retrieval — bereidt de zoekvraag voor de retrieval-fase voor

Fase 3 — Answer Generation
10. Generate Final Answer — de AI-agent die het uiteindelijke antwoord genereert, gebruikt Answer Chat Model als taalmodel en heeft Search Documents Tool als tool
    Search Documents Tool haalt op zijn beurt relevante documenten op via Retrieve Relevant Documents, met Retrieval Embeddings voor de embeddings en Retrieval Tool Chat Model als taalmodel
11. Format Agent Output — zet de ruwe agent-output om naar een bruikbaar formaat
12. Check Answer Success — controleert of er daadwerkelijk een geldig antwoord is gegenereerd
13. Bij een geldig antwoord: Format Success Response. Bij een fout: Format Error Response
14. Send Final Response — stuurt de uiteindelijke response terug naar de aanroeper

## Gebruikte technologie

- n8n voor de workflow-orkestratie
- Ollama voor lokale taalmodellen en embeddings, met nomic-embed-text als embedding-model
- Tavily voor het doorzoeken van het web
- Supabase met pgvector als vectordatabase voor het opslaan en terugvinden van documenten

## Vereisten

- Een draaiende n8n-instance
- Ollama, lokaal of extern bereikbaar, met een chat-model en het embedding-model nomic-embed-text geïnstalleerd
- Een Supabase-project met de vector-extensie ingeschakeld
- Een Tavily API-sleutel

## Supabase-configuratie

Voordat de workflow kan draaien, moet in Supabase de vector-extensie worden ingeschakeld, moet er een tabel voor de documenten worden aangemaakt (met kolommen voor onder andere de inhoud, metadata en de embedding-vector), en moet er een zoekfunctie worden aangemaakt die door de Supabase Vector Store node in n8n wordt aangeroepen om documenten op te zoeken op basis van gelijkenis. De naam van deze functie ligt vast vanuit n8n en moet ongewijzigd blijven; alleen de tabel waarnaar de functie verwijst kun je zelf benoemen. De dimensie van de embedding-kolom moet overeenkomen met het gebruikte embedding-model — bij nomic-embed-text is dat 768.

## Aanvraag en antwoord

De workflow wordt aangeroepen met een POST-verzoek naar de webhook-URL, met daarin de onderzoeksvraag van de gebruiker.

Bij succes stuurt de workflow terug: een bevestiging dat het gelukt is, het gegenereerde antwoord, en een tijdstempel.

Bij een fout stuurt de workflow terug: een aanduiding dat het is mislukt, een foutmelding, en een tijdstempel.

## Opmerkingen

- De retrieval-tool (Search Documents Tool) hangt als Tool aan de laatste AI-agent, zodat de agent zelf beslist wanneer de vectordatabase geraadpleegd wordt, in plaats van dat dit bij elke aanroep verplicht gebeurt.
- De node "Respond to Webhook" moet geactiveerd zijn, anders geeft de workflow geen response terug aan de aanroeper.
