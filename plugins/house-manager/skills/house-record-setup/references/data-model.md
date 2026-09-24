# The record page's database

Read and write it with the `ArtifactData` tool, passing the page's URL. Collections:

## `questions`
`{order, section, q, why, status, answer, answeredAt, docs}`
`status`: `open` → `answered` (the user saved an answer) → `filed` (Claude filed it), or `skipped`.
`docs` holds asset ids of files attached to that question.

## `records`
`{kind, title, docs, source, createdAt, updatedAt, ...kind fields}`

`kind` and its fields:

| kind | fields |
| --- | --- |
| `system` | manufacturer, model, serial, installed, provider, lastService, frequency, nextDue, warrantyEnd, notes |
| `appliance` | manufacturer, model, serial, installed, vendor, cost, warrantyEnd, provider, notes |
| `improvement` | date, why, contractor, contact, cost, materials, warrantyEnd, upkeep, notes |
| `maintenance` | date, system, work, provider, contact, cost, findings, nextDue, notes |
| `contractor` | service, relationship, contact, phone, email, website, frequency, lastVisit, cost, payment, nextVisit, notes |
| `warranty` | product, manufacturer, installer, contact, phone, start, warrantyEnd, coverage, claims, notes |
| `knowledge` | topic, detail |
| `task` | due, status, priority, recurring, notes |

`relationship` is one of: Current provider, Former provider, One-time, Project-specific.
`task.status`: Open, Scheduled, Waiting, Done. `task.priority`: Normal, High, Low.

All dates are `YYYY-MM-DD` strings. `nextDue`, `nextVisit`, `due` and `warrantyEnd` drive the Today lanes; `warrantyEnd` within 120 days surfaces automatically.

Leave a field out or empty when it is unknown — the page renders that as *Unknown*. Never fill it with a guess or a placeholder.

## `documents`
`{name, assetId, contentType, sizeBytes, note, linkedTo, questionId, status, uploadedAt, summary}`
`status`: `new` → `filed`. Read the file itself with the Artifact tool's read action, passing the `assetId` as `path`.

## `captures`
Quick notes typed into the bar at the top: `{text, status, createdAt}`. `status`: `new` → `filed`.

## `property/profile`
A single document: `{address, yearBuilt, purchased, sqft, beds, baths, lot, notes}`.

## Capacity

5,000 documents per page. Aggregate rather than creating a document per trivial event; prune nothing without asking.
