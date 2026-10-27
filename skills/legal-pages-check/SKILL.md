---
name: legal-pages-check
description: Use when preparing a launch or a store submission, or after adding data collection, to check a privacy policy, terms of service and cookie notice against a per-country checklist (Colombia's Law 1581 of 2012 as the worked example) and against what the app or site actually collects and declares. Flags gaps and marks what a lawyer must review. It is not legal advice.
disable-model-invocation: true
---

# Legal pages check

Legal pages fail in two ways: they miss what the law of the country requires, or they describe a product that does not exist (data that is not collected, or data collected and not mentioned). This check catches both and hands the hard questions to a lawyer.

**This is not legal advice.** Say so at the start of every report. The output is a list of gaps and questions for a qualified lawyer in each country, not an approval.

## Inputs

- The published or draft privacy policy, terms of service and cookie notice.
- The countries where the product has users or where the company is based.
- What the product actually does with data: forms, accounts, analytics, SDKs, cookies, payments, third parties that receive data, where data is stored and for how long. Get it from the code, the store data safety and privacy label answers, and the owner.
- A `legal/` knowledge base in the repo if one exists (approved clauses, past lawyer reviews).

## Step 1: what the product really does

Build a data inventory before reading the policy: each data type, its purpose, legal basis or consent, who receives it (processors and third parties), international transfer, retention and how a user can delete it. Mark each row "confirmed in code", "declared by owner" or "unknown".

## Step 2: compare against the pages

For each inventory row, check that the privacy policy mentions it accurately. Then the other way: each data practice the policy claims must exist in the inventory. Also check:

- Cookies and trackers listed in the notice match what the site sets; non-essential ones wait for consent where required.
- Terms describe the real product, pricing model, cancellation and refunds, and the governing law.
- Store declarations (Play data safety, App Store privacy labels) match the policy.
- Pages are reachable from the product, the store listing and the sign-up form, and have a visible last-updated date.

## Step 3: per-country checklist

Apply the checklist for each country. Worked example, **Colombia (Law 1581 of 2012 and its regulatory decrees)**; verify the current text of the law before relying on this list:

- Identity and contact details of the data controller.
- The processing and its purposes, stated specifically.
- Prior, express and informed authorization from the data subject, and how it is recorded and can be retrieved.
- Rights of the data subject (know, update, correct, revoke authorization, request deletion, be informed of use, complain to the SIC) and the channel and procedure to exercise them, with response times.
- Special treatment for sensitive data and data of children and adolescents.
- International transfers and the safeguards used.
- Registration of databases in the national registry (RNBD) when the controller is required to register.
- Effective date of the policy and how changes are communicated.
- Marketing communications only with authorization, with a way to unsubscribe.

For other countries, write the equivalent checklist from the official sources of that country's data protection authority, with the link to each source. Never fill a country's list from memory alone.

## Step 4: mark what needs a lawyer

Mark as **lawyer review** any of: interpretation of what a law requires, liability clauses and limitations, refunds and consumer law, international transfers, sensitive or children's data, regulated sectors (health, finance), contracts and anything the owner will sign.

## Rules

- Do not write "compliant", "approved" or "legal". Write "no gaps found against this checklist" at most.
- Do not draft final legal text as if it were approved. Suggested wording is marked as a draft for the lawyer.
- Do not invent laws, articles or deadlines. Cite the source for each requirement or mark it "to verify".
- Do not publish or change the pages.

## Output

```
NOT LEGAL ADVICE — gaps and questions for a qualified lawyer.
Data inventory: data type — purpose — basis/consent — recipients — retention — status
Gaps: - page — requirement or mismatch — source — severity — suggested fix (draft)
Lawyer review: - topic — why — question to ask
Unknowns for the owner: - ...
```

## Known failures

_Record real mistakes here with a date and the rule that prevents them._
