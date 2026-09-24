---
name: house-briefing
description: Produces a household briefing from the record page — what needs to happen now, this week, this month and beyond, plus a cleaning priorities list with rotating deep-clean tasks. Use when the user says "what needs to happen", "house briefing", "what's due this week", "what maintenance is coming up", "cleaning priorities", "what should the cleaning person focus on", or asks what has been neglected.
---

# House briefing

Answer from the record page's data, never from memory of the conversation. Read `records`, `questions` and `property/profile` with the `ArtifactData` tool before answering.

## What needs to happen

Bucket every dated thing and lead with the first bucket that has something in it:

**NOW** — overdue tasks, overdue service, warranties already expired or expiring within 30 days.
**THIS WEEK** — due within 7 days.
**THIS MONTH** — due within 31 days.
**UPCOMING** — beyond that, but dated.
**ONGOING** — recurring work with no next date set, and open items with no deadline.

Then, briefly: warranties ending within 120 days, upcoming payments, and records missing something that would matter in a failure ("no HVAC serial on file"). Use the seasonal check in `references/seasonal.md` against the current month and the systems on record — and say plainly when a date is a general recommendation rather than this house's own schedule.

Each line: the thing, its date, how overdue or how soon, and who to call if the record knows. Name the provider and their phone number when the user would have to look it up otherwise.

## Cleaning priorities

Produce a list the cleaning person can work from, in this order:

1. **Every visit** — the recurring work, in room order.
2. **This visit's deep clean** — two or three areas, chosen by how long since each was last done. `references/cleaning-rotation.md` holds the rotation and the intervals.
3. **Before guests or an event** — only when the user has mentioned one.
4. **Supplies to replenish** — only what the record says is low.

Do not repeat a deep-clean area done in the last two cycles unless the user asks. After the list, offer to record the visit so next time's rotation is right; on confirmation write a `maintenance` record with `system: "Cleaning"`, the areas deep-cleaned in `work`, the date, and `nextDue` from the cadence.

## Keep it short

A briefing is read standing up. No preamble, no restating the house's history, no praise. If nothing needs attention, say so in one line and name the one thing worth doing while there is time.
