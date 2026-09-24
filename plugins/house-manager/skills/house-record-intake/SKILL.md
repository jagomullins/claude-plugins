---
name: house-record-intake
description: Reads a household's record page — answered questions, newly uploaded documents and quick notes — and files them into permanent House Memory, then asks the next round of questions. Use when the user says "process my house record", "file my answers", "I answered the questions", "I uploaded the invoice", "catch up my house record", or reports something that happened to the house and expects it recorded.
---

# Process a house record

File what the user has added, then ask what is still missing. `references/filing-rules.md` has the judgment calls; `../house-record-setup/references/data-model.md` has the collections and fields.

## 1. Read what's waiting

With the `ArtifactData` tool on the record page's URL:

- `questions` where `status` is `answered`
- `documents` where `status` is `new`
- `captures` where `status` is `new`
- the whole `records` collection, so existing records are updated rather than duplicated

No record page yet, or no URL on file: ask for the link, or offer `house-record-setup`.

## 2. Read each new document

For every new document, read the file itself — the Artifact read action with its `assetId` as `path` — before filing anything from it. Take only what the document states. A document that cannot be read gets a note saying so, not an inference from its filename.

## 3. File

Create or update records with as few `batch` calls as possible. Rules that are not negotiable:

- **Only what was said or what the document shows.** Unknown fields stay empty. Never a guess, never a placeholder, never a rounded-off date.
- **Update, don't duplicate.** Match on the thing itself: "the furnace" is the existing `system` record, not a second one.
- **Preserve history.** A new provider makes the old one `Former provider` and keeps their work. A replaced appliance keeps its record; the new one is added.
- **A service event is its own record.** File the `maintenance` entry, set the system's `lastService` and `nextDue`, and mark the related task Done.
- **Warranties get their own record** when terms are known, cross-referenced by name to the improvement or appliance.
- **A quick note can become several things** — a task, a service event, a payment fact, a knowledge entry. File each.

## 4. Mark things filed

Set each processed question to `status: "filed"`, each document to `status: "filed"` with a one-line `summary` and `linkedTo` naming the record, and each capture to `status: "filed"`. Nothing is marked filed unless it actually landed in a record.

## 5. Ask the next round

Add `questions` for the gaps this pass exposed, ordered after the existing ones: a missing serial number, an installer's contact, a warranty length, the next service date, whichever unknown would matter most if the system failed tomorrow. Keep it to five or six at a time — a long queue goes unanswered. Each gets a `why` line naming what would answer it fastest, and a photo of a data plate or a document is often the fastest answer.

## 6. Report

Short, plain, no table unless it earns its place: what was filed, what changed in the record, what is now known that was not, and what was left alone and why (an unreadable document, an answer that raised a question). Then name the next round and stop.
