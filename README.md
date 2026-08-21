# DEUSPROOF — prove you made it first

A Claude Code plugin for establishing provenance of work an AI agent produced.

Two questions, in this order:

1. **Has this been made before?** Search a public ledger of AI-generated work
   before you publish.
2. **Can I prove I had it first?** Timestamp it so priority is checkable by
   anyone, later.

Free, no account, no API key.

## Install

```
/plugin marketplace add Abracadabrastartup/deusproof-plugin
/plugin install deusproof@deusproof
```

It connects to the hosted MCP server at `https://deusproof.com/mcp`. Nothing runs
locally and there is nothing to configure — no API key, no account.

Verified on Claude Code: installs from this repo and resolves to three skills
and one MCP server, ~207 tokens always-on.

## What you get

| Command | What it does |
|---|---|
| `/prior-art` | Is anything close to this already on the ledger? |
| `/notarize` | Seal a SHA-256 so you can prove priority. Content stays on your machine. |

Plus a skill that teaches Claude when provenance is worth raising on its own —
before you publish, ship or announce generated work — and nine MCP tools for
searching, sealing, verifying and looking up an agent's public record.

## Content stays private unless you ask otherwise

`notarize_hash` is the default and sends only a SHA-256 fingerprint. Your content
never leaves your machine, and the record still carries a real RFC 3161
timestamp, a public ledger entry and a Bitcoin anchor.

`certify_creation` is the other one — it publishes the prompt and output on a
public, append-only ledger. **That cannot be undone by anyone, including us.**
The bundled skill instructs Claude to prefer the hash and never to publish
content on its own initiative.

## What a record proves — and what it does not

It proves **a fingerprint existed at a given time and has not changed since**,
through an RFC 3161 timestamp, an append-only hash chain and a Bitcoin anchor via
OpenTimestamps. All three are verifiable by anyone, without trusting us.

It does **not prove authorship**. The ledger records what was submitted; it
cannot know who wrote it. Records signed with an agent's own key are marked
`signed`; the rest are `witnessed`, meaning only that the submission was seen.
The authorship score is a heuristic, not evidence. This is not a patent and not
a copyright registration.

We would rather you knew that than found out during a dispute.

## Keep the exact bytes

A SHA-256 is of exact bytes. Re-saving a file with different line endings (CRLF
vs LF) or adding a byte-order mark changes the hash, and the proof stops
matching. Keep the file you hashed.

## Privacy policy

<https://deusproof.com/legal/privacy> — what is stored, what becomes public and
permanent, what cannot be deleted, and who else sees any of it.

Terms of use: <https://deusproof.com/legal/terms>

## About

DEUSPROOF is operated by REDGROUND BLOCKCHAIN LLC (Florida, USA).
Site: <https://deusproof.com> · Docs: <https://deusproof.com/skill.md>
Contact: mars@redground.org

The agent card at `https://deusproof.com/.well-known/agent-card.json` is signed
with the same `did:key` that signs every certificate, so you can check the
service is who it says it is before you trust it with anything.

MIT licensed.
