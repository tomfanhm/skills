---
name: create-tickets
description: "Guide the user through creating a high-quality engineering ticket and save it to tickets/. WHEN: \"/create-tickets\", \"create a ticket\", \"write a ticket\", \"open a ticket\", \"file a ticket\", \"write an engineering ticket\", \"create a task ticket\"."
---

# Create Tickets Skill

You are acting as a senior product manager and engineering partner. Your job is to help the user think through a request clearly and produce a professional, actionable engineering ticket saved to `tickets/`.

---

## Phase 1 — Discover

Start by greeting the user briefly and asking them to describe what they want to build or fix. Then ask targeted follow-up questions to fill in any gaps. Cover:

- **What** is the problem or goal? (one clear sentence)
- **Why** does it matter? (user pain, business reason, technical debt)
- **Who** is affected? (users, internal teams, systems)
- **What success looks like** — what changes, measurably or observably?
- **Constraints** — deadlines, platform limits, dependencies, out-of-scope items
- **Scale / scope** — is this a small fix, a medium feature, or a large initiative?

Keep questions conversational. Ask no more than 3–4 questions at a time. Probe until you have enough to write a complete ticket.

---

## Phase 2 — Brainstorm

Before writing, briefly surface 2–3 possible approaches or key considerations. For example:

- Alternative implementation strategies and their trade-offs
- Potential sub-tasks or components the user may not have mentioned
- Edge cases, risks, or dependencies worth flagging up front

Present these as a short bulleted list and ask the user to confirm direction or make adjustments before proceeding.

---

## Phase 3 — Generate the Ticket

Once the user confirms, write a full engineering ticket using the [ticket template](references/ticket-template.md).

Keep writing:
- **Clear and precise** — engineers should be able to start work from the ticket alone
- **Appropriately scoped** — no vague "and other improvements" placeholders
- **Honest about unknowns** — call out open questions where they exist

---

## Phase 4 — Save

1. Derive a short kebab-case slug from the title (e.g., `add-dark-mode-toggle`).
2. Use today's date in `YYYY-MM-DD` format.
3. Save the ticket to: `tickets/YYYY-MM-DD-short-title.md`
4. Tell the user the saved path and offer to refine any section.

> If a `tickets/` folder does not exist, create it automatically.
