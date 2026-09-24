---
name: house-record-setup
description: Builds the user their own private house record page — a living artifact with a question queue, document uploads, House Memory and a Today view — and seeds the first round of questions. Use when the user says "set up my house record", "start my house manager", "build my home record", "I want to track my house", "set up house memory", or asks where their house records should live and has no record page yet.
---

# Set up a house record

Publish the user a private record page and seed its question queue. Run once per household.

## 1. Ask two things

Use AskUserQuestion:

- **What should the record be called?** Offer their surname ("the Miller House Record"), their street ("the Oak Lane House Record"), or plain "House Record".
- **Which of these does the house have?** Multi-select: pool · irrigation/sprinklers · septic system or well · none of these. This decides which questions to seed.

Do not ask for the address yet — the page asks for it.

## 2. Publish the page

The page is `references/record-page.html` in this skill. Read it, replace every `{{HOUSEHOLD}}` with the chosen name, write it to a working file, and publish it with the Artifact tool:

- `icon`: "house"
- `description`: one sentence naming the household.
- `capabilities`: `{"db": {}, "assets": {}}` — both are required. `db` holds the records; `assets` holds uploaded documents.

Do not restyle the page. It carries a complete design system (warm oat ground, clay accent, Petrona + Karla, phone-first); `references/design-notes.md` documents it if the user later asks for changes.

## 3. Seed the questions

Load `references/question-bank.json`. It holds question documents keyed by id, each with `order`, `section`, `q`, `why`, plus a `when` field naming a feature ("pool", "irrigation", "septic") — skip any question whose `when` the house does not have, and drop the `when` field before writing.

Write them to the `questions` collection with **one** `ArtifactData` `batch` call (up to 50 writes). Each document: `{order, section, q, why, status: "open", answer: "", docs: []}`.

Seed no records. House Memory fills from answers, so nothing is invented up front.

## 4. Hand it over

Tell the user, in plain language:

- The page is live and private to them; sharing is from its own Share menu, and only people signed in to their Claude organization can open it.
- Start on **Questions**; rough answers are fine and "don't know" is useful.
- The fastest win is attaching their **home inspection report or closing packet**, which usually answers many questions at once.
- Word and Excel files go in the chat rather than on the page.
- When they've answered some, say **"process my house record."**

Record the page's URL and the household name in the project or memory so later sessions find it without asking.

## If a record page already exists

Do not publish a second one. Ask whether they want to continue with the existing page (the usual case) or start a separate record for a different property, and if a second property, publish it as its own artifact with its own name.
