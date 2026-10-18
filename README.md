# LeadZam UX Improvement — Follow-up Queue

A focused React + TypeScript prototype exploring how a sales representative can triage follow-ups, inspect lead context, and mark work complete.

## Status and scope

This is a **proposed concept**, not a claim that the current authenticated LeadZam app has the same layout or verified usability defects. Public product pages describe an all-channel lead inbox, lead timeline, follow-up queue, tasks, WhatsApp conversations, calls and reports. The authenticated workspace was not accessible through the public page review used for this draft. Before submitting, sign in normally to your own test workspace, inspect the relevant screens, capture screenshots, and update the audit with verified observations.

## Run locally

Requirements: Node.js 18+

```bash
npm install
npm run dev
```

Check the production build with:

```bash
npm run build
```

## Chosen improvement

**Hypothesis to validate:** sales reps may benefit from a single prioritized queue that makes overdue, due-today and upcoming work distinguishable, while keeping the lead's owner, stage, source, next follow-up and latest note visible.

The prototype includes:
- Overdue, due-today and upcoming counts
- Tabs to prioritize follow-ups
- Search by lead, company, owner or source
- Source filter
- Lead details panel
- Mark-follow-up-complete action with confirmation feedback
- Add-lead modal with required-field validation
- Empty state and reset-to-all action
- Responsive layout and keyboard focus styles

The data is local mock data. Changes reset on refresh. Call and WhatsApp actions are illustrative and do not contact anyone; other navigation items are placeholders.

## Preliminary audit — public website vs. unverified app

Do not submit unverified app hypotheses as confirmed findings. Use `AUDIT.md` to record the public-site observations and complete the in-app evidence after exploring with your own test account.

## Figma handoff

Create a Figma file with these frames:
1. **Queue / desktop default** — show the tabs, counts, lead list and selected lead details.
2. **Queue / completed state** — remove the completed item and show a brief success message.
3. **Add lead / validation state** — show required name field and source selector; demonstrate missing-name validation.
4. **Queue / mobile** — collapsed navigation and stacked/compact queue rows.

Use reusable components for `Lead row`, `Urgency badge`, `Summary card`, `Lead details`, `Button`, `Search field`, and `Add lead modal`. Keep the existing product identity only after checking the actual product UI; otherwise label this as a concept direction.

## What I would validate before shipping

1. Observe 3–5 sales users handling an overdue follow-up in the current app.
2. Measure time to find a lead, identify the next action, and complete the task.
3. Compare the current and proposed flows with identical test scenarios.
4. Check if urgency labels and counts match the team's actual follow-up rules.
5. Validate keyboard navigation, focus visibility, mobile overflow and form errors.
6. Review queue completion and task history with product/engineering before connecting a backend.

## Trade-offs

- Chose one high-frequency workflow instead of recreating the CRM.
- Used local mock data so the prototype runs without credentials or customer data.
- Kept calling, WhatsApp and other navigation actions as explicit placeholders rather than implying integrations exist.
- Used a side panel to retain queue context while inspecting one lead; validate whether this fits the real product's interaction patterns.
- The UI is intentionally a concept until the live product is reviewed and screenshots are added.

## What I would do with two more hours

- Inspect the authenticated product using dummy data and capture annotated current-state screenshots.
- Revise the audit to distinguish observed evidence from assumptions.
- Align visual tokens and component patterns with the actual app.
- Add automated interaction checks for search, filtering, validation and completion.
- Finish the Figma frames and record the walkthrough.

## AI usage notes

- **Tool used:** ChatGPT for hypothesis generation, implementation scaffolding, copy and documentation review.
- **How it helped:** accelerated a focused queue concept and the first React/TypeScript implementation.
- **Suggestion changed:** rather than redesigning the entire CRM or adding a large analytics dashboard, the concept focuses on one follow-up workflow because the assignment asks for one high-impact improvement.
- **What must be personally verified:** current product screenshots, whether the hypothesized friction exists, visual fidelity, build output, interactions, and accessibility. Do not claim that AI or this README has verified those items.

## Source context

The public LeadZam website describes lead capture across Meta, Google, WhatsApp and web forms, a lead inbox and timeline, follow-up tasks, calls, reports and automation. See the public site at https://leadzam.com/ and CRM overview at https://leadzam.com/crm/ . The public product pages informed the scope; they do not prove that any authenticated-app usability issue exists.

## Reusable design-system direction

The prototype uses shared visual patterns for color, typography, spacing, borders, status badges and buttons. If integrated into LeadZam, map these concept tokens to the existing product design system rather than introducing a competing palette. Suggested token groups:
- **Color:** brand/action, text primary/secondary, surface, border, success, warning, danger.
- **Spacing:** 4, 8, 12, 16, 24, 32px scale.
- **Radius:** compact control, card, modal.
- **Type:** page heading, section heading, body, helper text, metadata.
- **Components:** button, status badge, summary card, searchable input, select, lead row, detail panel, modal, toast.

Before adopting tokens, compare the actual app's styles and consolidate duplicates instead of changing colors for decoration.

## Before/after and measurement

Use `AUDIT.md` for a conceptual before/after matrix and a small usability-test plan. Replace all “current state” entries with observed evidence from the real app. Suggested post-launch events and success metrics are also documented there. Analytics must not include raw search text, lead names, phone numbers or message contents.

## Integration into the wider product

The follow-up queue should reuse existing LeadZam navigation, typography, buttons, fields, status semantics, spacing and feedback patterns. Extract only genuinely reusable elements into shared components after checking for existing equivalents. Keep business rules (urgency calculation, due-date rules, completion behavior and permissions) out of presentational components so the UI can later consume real API data without a rewrite.

## Follow-up discussion prep

Be ready to explain which observations are confirmed versus hypotheses, why you chose this scope, how mocked local state would become API loading/error/retry states, how you would test keyboard/mobile accessibility, what AI generated and what you reviewed, and how you would avoid introducing a second design system.

## Included product evidence

Candidate-supplied screenshots from the LeadZam test workspace are in `evidence/current-product/`. They document the owner-required warning, the separate lead-assignment modal, and the follow-up scheduling popover. See `AUDIT.md` for the evidence-based finding and scope limitation. Do not describe the ownership rule itself as a confirmed defect; the redesign reduces workflow interruption while preserving the requirement unless product validation says otherwise.

## Local verification status

Run `npm install`, `npm run build`, and `npm run dev` locally before sharing the prototype. Dependency installation/build could not be verified in the preparation environment, so do not claim a successful build until you run those commands. Test the add-lead, search/filter, detail panel, assignment/scheduling states, keyboard behavior, and mobile layout before recording your walkthrough.
