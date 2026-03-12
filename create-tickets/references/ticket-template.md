# Ticket Template

Use this structure for every generated ticket. Fill every section; write "N/A" only if a section is genuinely not applicable (rare). Do not leave placeholders.

---

```markdown
# [TICKET-ID] <Title>

> **Status:** Draft | Ready | In Progress | Done
> **Priority:** P0 Critical | P1 High | P2 Medium | P3 Low
> **Estimate:** <story points or t-shirt size>
> **Assignee:** Unassigned
> **Labels:** <feature | bug | chore | spike | infra>

---

## Summary

One or two sentences: what this ticket delivers and why it matters.

---

## Background / Problem

Describe the current state and the pain or gap that motivates this work.
Include relevant context: user feedback, error rates, product goals, prior decisions.

---

## Goals

What this ticket **will** accomplish (bullet list, each item measurable or verifiable).

## Non-Goals

What this ticket explicitly **will not** do. Prevents scope creep.

---

## Scope

Enumerate the surfaces, systems, or components touched:
- **In scope:** ...
- **Out of scope:** ...

---

## Technical Considerations

- Architecture decisions, design patterns, or constraints
- Dependencies on other services, libraries, or tickets
- Data model changes (schema migrations, API contracts)
- Performance, security, or accessibility implications
- Open questions / decisions still to be made

---

## Acceptance Criteria

Each criterion must be independently verifiable.

- [ ] Given <context>, when <action>, then <observable outcome>
- [ ] ...

---

## Tasks / Implementation Steps

Ordered sub-tasks an engineer can check off. Break large tasks into ≤1-day chunks.

- [ ] 1. ...
- [ ] 2. ...
- [ ] 3. ...

---

## Risks / Edge Cases

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| ... | Low/Med/High | Low/Med/High | ... |

---

## Definition of Done

The ticket is complete when:
- [ ] All acceptance criteria are met and verified
- [ ] Unit / integration tests written and passing
- [ ] Code reviewed and approved
- [ ] Documentation updated (if applicable)
- [ ] Deployed to staging / production (as applicable)
```
