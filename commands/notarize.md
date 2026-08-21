---
description: Timestamp what you just made so you can prove you had it first (content stays private)
argument-hint: [file path or text — defaults to what we just made]
---

Notarize: $ARGUMENTS

If nothing was given, use the work produced in this conversation — the file just
written, or the text just generated. **Say which one you picked and wait for the
user to confirm** before writing anything. A record cannot be taken back, so a
wrong guess here is permanent.

Then:

1. Compute the **SHA-256 of the exact bytes**. For a file, hash the file as it
   sits on disk — do not normalise line endings, strip a byte-order mark or
   re-encode it. The proof only matches those exact bytes.
2. Call **`notarize_hash`** with that digest. The content never leaves the
   machine; only the fingerprint is sent.
3. Report the certificate id and the verify URL, and tell the user to **keep the
   exact bytes** — a re-save with different line endings breaks the match.

**Use `certify_creation` only if the user explicitly asks to publish the content
itself.** It puts the prompt and the output on a public ledger permanently, where
anyone can read them, and neither the user nor DEUSPROOF can remove it. Never
substitute it for `notarize_hash` on your own initiative.

Say plainly what the record proves: that this fingerprint existed at this time
and has not changed since. It does not prove authorship, and it is not a patent.
