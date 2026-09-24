# Filing judgment

## Which kind is it?

| The user said | kind |
| --- | --- |
| "we have a Trane furnace" | `system` |
| "the dishwasher is a Bosch from 2023" | `appliance` |
| "we redid the kitchen in 2024" | `improvement` |
| "the plumber came out and replaced the valve" | `maintenance`, plus `contractor` if new |
| "we use Anderson Heating" | `contractor` |
| "the windows have a 20-year warranty" | `warranty` |
| "the shutoff is behind the furnace" | `knowledge` |
| "I need to get the gutters cleaned" | `task` |

A purchase that gets installed is an `appliance` or `improvement`, not a task. A quote is not an improvement — track it as a `task` until work is scheduled.

## Dates

Use `YYYY-MM-DD` only when the actual date is known. "Last spring" is not a date: put the phrase in `notes` and leave the date field empty. "About five years old" goes in `notes`, not into `installed` as a computed year.

Set `nextDue` only from a stated interval or a provider's stated plan. Common intervals exist, but a general interval is not this house's schedule — if the user has not said, ask.

## Money

Record a cost exactly as stated or as an invoice shows it. Never total, estimate or annualize a figure the user did not give. Recurring service cost goes in `cost` with the cadence in `payment` ("$185 per visit, monthly April–October").

## People

A provider gets one `contractor` record with the company as the title and the person in `contact`. Two people at one company: `contact` names the one to call, the other goes in `notes`. Keep phone and email exactly as given.

## Documents

Link every document to a record by name in `linkedTo` — "Windows warranty", "Improvement: Kitchen 2024". A document supporting several records names the main one and says so in `summary`.

An invoice states: a date, a provider, work performed, and a cost. It does not state a warranty term unless it says so, and it does not state a next service date unless it says so. File what is there.

## When it conflicts

A document that contradicts an earlier answer: keep both. Put the document's value in the field, and in `notes` say what was previously recorded and that the document supersedes it. Then tell the user.

## What not to file

Speculation ("it's probably original to the house"), your own recommendations, and anything the user asked you not to record. The record is the household's account of itself, not your analysis of it.
