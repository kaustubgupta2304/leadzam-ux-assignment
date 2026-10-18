# 3–5 minute walkthrough script

Use this as a guide, not a claim that all validation is complete. Replace the evidence section with screenshots from your actual LeadZam test workspace.

## 0:00–0:30 — Context
“LeadZam supports sales teams that capture leads from multiple channels and manage follow-ups. I reviewed the public product experience and began an audit. I could not verify the authenticated app in the public page review, so I treat the in-app items as hypotheses until I inspect the test workspace.”

## 0:30–1:15 — Audit and prioritization
“Rather than listing visual polish issues, I prioritized user tasks. On the public website, I noted the trial/demo choice and the breadth of feature discovery as areas to validate. For the app, I plan to validate follow-up triage, lead context and recovery states. My selected concept is follow-up triage because it is a repeated sales task and small enough to prototype.”

## 1:15–2:00 — Design reasoning
“The proposed queue separates overdue, due-today and upcoming work, offers search and source filters, and keeps the selected lead’s next follow-up and context beside the queue. The aim is to reduce scanning and context switching. This is a hypothesis, not a measured improvement yet.”

## 2:00–3:30 — Live prototype
- Switch between Overdue, Due today, Upcoming and All follow-ups.
- Search for a lead and change the source filter.
- Select a lead and explain the details panel.
- Mark a follow-up complete and show the queue updating.
- Add a lead; try submitting the form without a name to show validation.
- Resize to mobile width and show the responsive layout.

## 3:30–4:15 — Trade-offs and next steps
“The prototype uses local mock data and does not connect to real customer records, calling or WhatsApp. Before shipping, I would observe sales reps using the current flow, compare time-to-completion and task success, test keyboard/mobile accessibility, and align the concept with the existing product components.”

## Before recording
- [ ] Run `npm run build` and resolve any errors.
- [ ] Use only mock/dummy data.
- [ ] Show the actual current-state screenshots in the audit.
- [ ] Keep the walkthrough between 3 and 5 minutes.
- [ ] Explain what is implemented versus what is only proposed.
