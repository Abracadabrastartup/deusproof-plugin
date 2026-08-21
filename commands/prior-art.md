---
description: Check whether something like this is already on the public ledger, before you publish it
argument-hint: [text, file path, or SHA-256 — defaults to what we just made]
---

Search the DEUSPROOF ledger for prior art on: $ARGUMENTS

If nothing was given, use the work produced in this conversation — the file just
written, or the text just generated. Say which one you picked before searching,
so the user can redirect you if it was the wrong thing.

Call `prior_art_search`. Pass the text itself, or its SHA-256 if the user would
rather not send content (a 64-character hex string is treated as a fingerprint,
not as text).

Then report, in this order:

1. **Whether anything close came back**, and if so what it is, who recorded it
   and when. That is the answer. A similarity number without the matching record
   tells the user nothing they can act on.
2. **If nothing matched**, say so plainly and offer `/notarize` to seal priority
   now — but do not run it unasked.

This is a read. Nothing is written to the ledger and nothing is published.
