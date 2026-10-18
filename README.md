# LeadZam UX Audit and Frontend Redesign

A UI/UX audit and frontend concept redesign focused on improving the lead follow-up scheduling workflow.

## Problem

The supplied screenshots show that scheduling a follow-up for a lead without an assigned owner triggers an owner-required warning. Resolving this separately can interrupt the scheduling flow.

## Proposed Solution

The redesign brings owner selection into the scheduling workflow and provides:

- Owner selection when required.
- Quick scheduling options.
- Custom date and time selection.
- An optional follow-up note.
- A clear success state.

## Repository Contents

- `AUDIT.md` — UX audit and proposed improvements.
- `App.tsx` — frontend implementation.
- `AI-USAGE-NOTES.md` — AI assistance disclosure, when included.
- `ASSUMPTIONS-AND-LIMITATIONS.md` — assumptions and limitations, when included.
- `WALKTHROUGH-SCRIPT.md` — suggested screen-recording script, when included.
- `evidence/` — supporting screenshots, when included.

## Running the Frontend

This project requires Node.js and npm.

1. Clone the repository:

   ```bash
   git clone https://github.com/kaustubgupta2304/leadzam-ux-assignment.git
   cd leadzam-ux-assignment
   ```

2. Install dependencies if a `package.json` is present:

   ```bash
   npm install
   ```

3. Start the development server if the project scripts are configured:

   ```bash
   npm run dev
   ```

Follow any framework-specific instructions in the source files if these commands are not configured.

## Prototype Limitations

- The concept is not connected to a production backend.
- Scheduling and lead data may be simulated.
- Real reminders and notifications are not delivered.
- The proposed usability improvements have not been validated through user testing.

## Design Links

- Figma prototype: https://www.figma.com/proto/MsSXNFiZNfzaICTLu7cZk4/Untitled?node-id=4-1479&t=1oZgVMJWHIjVkhT7-0&scaling=min-zoom&content-scaling=fixed&page-id=0%3A1
- Editable Figma design: https://www.figma.com/design/MsSXNFiZNfzaICTLu7cZk4/Untitled

## Author

Kaustub Gupta
