
# Social Media Content Generator & Planner

An automated social media content workflow built with **n8n** and **Notion**.  
This project demonstrates how to fetch, process, schedule, and publish content using workflow automation and external APIs.

---

## 🚀 Overview

The workflow retrieves content from a Notion database, filters items marked as **Ready**, formats them into social media posts, schedules publishing, and sends them via an HTTP request (API/webhook).

The goal of this project is to demonstrate practical automation skills, API integration, and state-based workflow logic.

---

## ✨ Features

- Fetches content from a Notion database
- Filters items by status (`Ready`)
- Formats social media post text dynamically
- Supports scheduled posting using wait logic
- Sends posts via HTTP request (API / webhook)
- Prevents duplicate or premature posting
- Modular and readable workflow design

---

## 🧠 Workflow Logic (High Level)

1. Trigger workflow manually
2. Search Notion database for content
3. Process and format post content
4. Apply conditional logic (If nodes)
5. Wait until scheduled publish time
6. Send post via HTTP request
7. End workflow cleanly

---

## 🛠 Tech Stack

- **n8n** – Workflow automation
- **Notion API** – Content source
- **JavaScript** – Custom logic (Code nodes)
- **HTTP / Webhooks** – External API communication

---

## 📦 Why This Project

This project was built to demonstrate:

- Workflow automation design
- API-based integrations
- Conditional and state-driven logic
- Asynchronous processing (scheduled execution)
- Clean project structure and completion

It reflects real-world automation use cases commonly found in startups and agencies.

---

## 📌 Status

✅ Completed  
✅ Portfolio-ready  
✅ Suitable for junior or internship-level roles

---

## 📄 Notes

This project focuses on workflow logic and integration.  
Authentication and platform-specific posting (e.g. LinkedIn API) can be added as extensions.

---

## 👤 Author

Built by **[Your Name]**  
