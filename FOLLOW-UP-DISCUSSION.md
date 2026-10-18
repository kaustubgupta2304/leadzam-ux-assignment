# Follow-up discussion prep

Adapt these answer prompts to the evidence you actually collect. Do not claim a current-app issue unless you observed it.

## Why did you choose this issue?
“I selected follow-up triage because it is closely tied to a repeated sales task and missed follow-ups can affect response time. I would only finalize the selection after observing the current app and checking that the friction is real. The scope is narrow enough to test and prototype without rebuilding the CRM.”

## How is the redesign better?
“The concept groups work by urgency and shows key lead context beside the queue. Search and source filtering help locate a lead, and completing a task immediately updates the list with feedback. These are intended benefits; I would measure task completion, time-on-task and errors before claiming improvement.”

## What did you not redesign?
“I kept the wider CRM, reporting, automation, telephony, WhatsApp integration and backend out of scope. Recreating those would dilute the assignment and make the core workflow harder to evaluate.”

## What are the limitations?
“The data is mocked and resets on refresh. Calling and WhatsApp actions are illustrative. The authenticated current-state audit and screenshot evidence must be completed in my own test workspace. The concept does not yet implement production permissions, API errors, loading retries or a full focus-managed modal.”

## How would you integrate it?
“I would first inspect existing components and design tokens, then reuse the current button, input, badge, table/list and toast patterns. I would separate urgency rules and API operations from the UI components, add tests for filtering/completion/validation, and roll out behind a feature flag if appropriate.”

## What would you test?
- Unit/component tests for queue filtering, counts, completion, and required-field validation.
- Keyboard navigation and focus return from the modal.
- Responsive behavior at mobile, tablet and desktop widths.
- A usability comparison using the same tasks in the existing app and prototype.
- Analytics for task completion and time-to-action, without recording personal lead data.

## How did AI help, and what did you change?
“ChatGPT helped draft a focused workflow, React scaffolding and audit questions. I rejected the idea of treating generic CRM best practices as proof of current LeadZam defects. I marked unverified app findings as hypotheses and would replace them with screenshots and observations from my own workspace before final submission.”
