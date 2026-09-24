---
name: house-sale-handoff
description: Turns a household's House Memory into a buyer and homeowner handoff package, separating what is known from what is missing and which documents exist from which are still needed. Use when the user says "prepare the house for sale", "we're listing the house", "buyer handoff package", "what would a new owner need to know", "house sale mode", or asks what to gather before listing.
---

# House sale handoff

Switch from daily operations to making the house transferable: organise everything the record holds so a new owner can understand, maintain and operate the property without reconstructing its history.

## 1. Read the whole record

With the `ArtifactData` tool: `property/profile`, every `records` document, every `documents` document, and any `questions` still open. Read the actual data — a handoff package built from conversation memory will be wrong.

## 2. Build the package

In this order, using only what the record holds:

1. **Property** — address, year built, size, purchase date, lot.
2. **Major systems** — each with age, install or replacement date, manufacturer and model, who services it, service interval and last service.
3. **Appliances** — what conveys, with model, serial, age and warranty.
4. **Improvements** — chronological, with date, contractor, cost, materials and warranty.
5. **Maintenance history** — by system, most recent first.
6. **Contractors and service providers** — current first, then former, each with what they worked on. Say plainly which ones know the property well.
7. **Warranties** — what remains in force, what covers it, what expires when, and which are transferable if the record says.
8. **Documents** — invoices, contracts, warranties, manuals, permits, inspections, receipts.
9. **What a new owner should know** — paint colors, finishes, shutoff locations, equipment quirks, seasonal routines, access details, lessons from past repairs. This section is the one a seller cannot produce from a filing cabinet, and it is the most valuable.

## 3. Separate known from missing

Four headings, always, and never blur them:

**Known** · **Missing** · **Documents available** · **Documents still needed**

Invent nothing. "Roof age unknown" is the correct entry when the roof's age is unknown; a plausible estimate in a sale document is a liability.

## 4. Say what to fix before listing

A short prioritised list of the gaps worth closing, hardest-to-recover first: a system with no service history, a warranty with no paperwork, a major improvement with no permit or invoice, a provider whose contact is lost. For each, name where it would come from — the contractor's office, the manufacturer's registration, the county permit record, a card statement.

## 5. Deliver it

Offer the package as a document the user can hand to an agent, a buyer or the next owner, and ask which form they want before building it. Add the gap list to the record as `task` documents so closing them shows up in the ordinary briefing.
