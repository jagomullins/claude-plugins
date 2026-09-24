# House Manager

A house manager, home operations coordinator and property historian for one household.

It keeps two layers of information, and keeps them apart:

- **Home Operations** — what needs to happen: maintenance due, contractor visits, payments, open issues, cleaning priorities.
- **House Memory** — what we know about this house: what it has, what was installed or replaced, who did the work, what it cost, what warranties exist, and everything a future owner would otherwise have to reconstruct.

The work happens on a **record page** the plugin builds for you: your own private page with a question queue, document uploads, a permanent record and a Today view. Claude reads that page, files what you add, and asks the next round of questions.

## What's in it

| Skill | Say | What it does |
| --- | --- | --- |
| Set up my house record | "set up my house record" | Publishes your own record page and seeds the first round of questions. Run this once. |
| Process my house record | "process my house record" | Reads your answers, uploads and notes; files them into House Memory; asks what's still missing. |
| Weekly house briefing | "what needs to happen this week" | Now / this week / this month / upcoming / ongoing, plus a cleaning priorities list with rotating deep-clean areas. |
| Prepare the house for sale | "prepare the house for sale" | Turns House Memory into a buyer handoff package, separating what's known from what's missing. |
| House memory | (loads on its own) | The operating principles: the two layers, the record categories, and the rule that nothing is ever invented. |

## Getting started

1. Say **"set up my house record."** Answer two short questions and you'll get a link to your page.
2. Answer whatever questions you can on the page. Attach an inspection report or closing packet if you have one — it answers a dozen questions at once.
3. Come back and say **"process my house record."**

Repeat step 2 and 3 whenever something happens to the house. The record gets more useful the longer you keep it.

## Notes

- Your record page is private to you until you share it from its own Share menu. Because it stores data and files, it can only be opened by people signed in to your own Claude organization — good for a spouse or a house sitter, not for a public link.
- Nothing is ever guessed. An unknown detail stays visibly unknown until someone fills it in.
- Word and Excel files can't be stored on the page; attach those in the chat instead, and Claude will file what they say.
