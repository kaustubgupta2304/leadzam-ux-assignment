# LeadZam UX audit — evidence log

**Audit status:** preliminary. Public marketing pages were reviewed. The authenticated app was not accessible through the public page retrieval used for this draft. The app findings below are hypotheses to validate, not verified defects.

## Public-site observations

### 1. Trial vs. demo next step — Medium, validate with users
- **Where:** LeadZam homepage hero and calls to action.
- **Evidence:** the page presents “Start 14-Day Free Trial” and “Book a Demo” as actions in the hero area.
- **User goal:** decide how to evaluate the product.
- **Potential friction:** visitors who are unsure whether setup is self-serve or guided may hesitate between two different evaluation paths.
- **Recommendation:** clarify who each path is for, e.g. self-serve teams vs. teams wanting a guided walkthrough; measure click-through and trial activation before changing the CTA hierarchy.
- **Screenshot:** capture the homepage hero in a browser and insert it here before submission.

### 2. Broad feature discovery — Medium, validate with users
- **Where:** homepage navigation and feature overview.
- **Evidence:** public page presents multiple product areas, use cases and integrations, including CRM, Forms, Automations, Call Analytics and integrations.
- **User goal:** understand whether LeadZam solves their team's particular need.
- **Potential friction:** first-time visitors may have difficulty mapping a long feature list to their immediate goal.
- **Recommendation:** consider role- or goal-based entry points (sales follow-up, lead qualification, marketing attribution) and test whether visitors can find the right feature quickly.
- **Screenshot:** capture the navigation and feature overview in a browser before submission.

## In-app investigation targets — not yet confirmed

### 3. Follow-up triage — High if observed
- **Where:** authenticated Follow-ups/tasks area.
- **Question:** can a rep distinguish overdue, due-today and upcoming work without extra filtering or opening each task?
- **Why it matters:** missed or delayed follow-ups may affect lead response time and conversion.
- **Recommendation if evidence supports it:** prioritized queue with clear urgency, next action and lead context.
- **Evidence required:** current-state screenshot, task walkthrough and observed number of steps/time.

### 4. Lead context while acting — Medium if observed
- **Where:** lead detail/timeline and follow-up workflow.
- **Question:** can a rep see source, owner, stage, latest interaction and next task together?
- **Why it matters:** switching between screens can interrupt the contact workflow and increase mistakes.
- **Recommendation if evidence supports it:** keep the key context adjacent to the next action.
- **Evidence required:** current-state screenshot and user walkthrough.

### 5. First-time and recovery states — Medium if observed
- **Where:** onboarding, add/import lead forms, empty queues, errors and success feedback.
- **Question:** does the UI explain the next step when no data exists or an action fails?
- **Why it matters:** unclear empty or error states can stall initial setup and recovery.
- **Recommendation if evidence supports it:** contextual empty-state CTA, field-level validation, and clear success/error feedback.
- **Evidence required:** capture at least one relevant state using a test workspace.

## Selected problem

**Proposed selection: follow-up triage.** It is a core, repeated sales task and can be prototyped without recreating the whole CRM. Keep this selection only if live-product observation confirms meaningful friction. If not, choose the strongest verified problem instead.

## Screenshot checklist before submission

- [ ] Homepage hero showing trial/demo actions
- [ ] Homepage navigation or feature overview
- [ ] Authenticated current-state screen related to selected problem
- [ ] Current interaction showing the friction (annotated, with dummy data)
- [ ] Prototype default state
- [ ] Prototype success/empty/validation state
- [ ] Prototype mobile state

## Before / after comparison (conceptual until verified)

| Dimension | Current state | Proposed concept | How to validate |
|---|---|---|---|
| Prioritization | Record from actual app; do not assume. | Separate overdue, due-today and upcoming work with counts. | Time how long users take to identify their next task. |
| Lead context | Capture which fields are currently visible and where. | Show owner, stage, source, next follow-up and note beside the queue. | Ask users to state the next action without navigating away. |
| Search | Record whether search/filter currently exists and how it behaves. | Search by lead/company/owner/source; filter by source. | Measure task completion and number of filter changes. |
| Completion feedback | Capture actual current feedback. | Remove completed item from active queue and show confirmation toast. | Verify completion success and user confidence. |
| Small screens | Record observed responsive behavior. | Compact queue rows and collapsible navigation. | Test at 320px, 375px, 768px and desktop widths. |

## Screenshot annotation template

For each screenshot, include:
- **Observed:** only what is visibly present in the screenshot.
- **Task:** what the user is trying to do.
- **Friction:** a specific extra decision, step, ambiguity, or recovery problem.
- **Impact:** likely effect on time, error rate, completion, or confidence.
- **Recommendation:** the smallest change that addresses the friction.
- **Priority rationale:** frequency × impact × confidence in the evidence.

Do not use the prototype screenshot as proof of a current-state problem. Label current and proposed screenshots clearly.

## Small usability-test plan

**Participants:** 3–5 sales/telecalling users, ideally with a mix of new and experienced users. **Safety:** use a test workspace and dummy contacts only.

Tasks:
1. Find the most urgent follow-up.
2. Explain why it is urgent and identify the next action.
3. Find a lead from a specified source.
4. Review its latest note and mark the follow-up complete.
5. Add a lead with a missing required name, recover from validation, then create it.

Observe completion rate, time-on-task, wrong turns, filter usage, errors, and post-task confidence (1–5). Avoid leading participants to the intended solution. A small sample is directional, not statistically conclusive.

## Analytics to consider after shipping

Track only events needed to evaluate the workflow, using a stable pseudonymous lead/task ID and avoiding names, phone numbers, message contents, or other personal data:
- `follow_up_queue_viewed`
- `follow_up_filter_changed` (filter type/value category)
- `follow_up_search_used` (never log raw search text)
- `lead_detail_opened`
- `follow_up_completed`
- `follow_up_rescheduled`
- `lead_create_started`
- `lead_create_validation_error` (field name only)
- `lead_created`

**Success metrics:** median time to identify next follow-up, completion rate for due tasks, overdue task rate, task reschedule rate, validation recovery rate, and task-related error reports. Establish a baseline and guard against optimizing completion speed at the expense of quality.

## Accessibility review notes

- All interactive controls should be keyboard reachable with visible focus.
- Use real buttons/labels and accessible names for icon-only controls.
- Keep text/background contrast sufficient; do not communicate urgency by color alone.
- Announce completion feedback through a polite live region.
- Ensure the add-lead dialog has focus management, Escape handling and focus return before production.
- Check zoom/reflow and narrow screens; avoid horizontal page scrolling.
- Verify errors are associated with fields and explain how to fix them.

These are recommendations to verify, not claims of a completed formal accessibility audit.

## Screenshot evidence supplied on 18 October 2026

The `evidence/current-product/` folder contains three screenshots captured by the candidate from their LeadZam test workspace:

1. `lead-owner-required-warning.png` — the follow-up action is blocked by a warning that the lead needs an owner.
2. `assign-lead-modal.png` — the user is asked to choose a team member in a separate assignment modal.
3. `schedule-follow-up-popover.png` — the scheduling popover exposes quick options and a custom date/time option, plus an optional note.

### Evidence-based observation

In the shown sample-lead flow, scheduling and ownership are separate steps: the follow-up UI warns that an owner is required, then routes the user to a separate “Manage lead” assignment modal. This creates a context switch before the user can complete the reminder. The scheduling popover already offers quick scheduling and a note field, so the redesign should preserve those useful elements while making the owner requirement clearer and reducing rework.

### Proposed design response

- Keep quick scheduling options and custom date/time selection.
- Show owner status before final scheduling.
- If no owner exists, offer an inline owner selector or a clear “Assign owner” step without discarding the selected time or note.
- Disable final submission only when a required field is missing, and explain why next to the field.
- Confirm the scheduled date/time and owner after submission.

**Scope note:** these screenshots document the specific sample-lead flow shown, not every lead type or every workspace configuration. The assignment should present the finding as observed in this flow and validate whether ownership is a required product rule before proposing to remove that requirement.
