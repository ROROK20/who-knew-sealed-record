# who-knew-sealed-record

Public, hash-only timestamps for a sealed, prospective study. The study asks whether trading that is unusual for the address placing it appears on a public prediction-market ledger before an event's first public disclosure, more often than the same frozen rule fires in placebo windows.

**What this repository contains:** SHA-256 hashes only, committed in time order.
- `F0.txt` holds the stage-1 freeze: the protocol, the disclosure-time coding manual and the eligibility rule, frozen before any detector code existed.
- `F1.txt` will hold the stage-2 freeze: the detector code, thresholds and seeds, frozen before any evaluation or pre-disclosure window is opened.
- `issues/` will hold one file per weekly sealed alarm list. Each is a salted hash, committed when the list is issued.

**What it never contains:** the alarm lists themselves, any wallet address, any person's name, or any market question text.

**How to verify later.** When the study is scored, the hashed documents and salts are released. Anyone can then recompute the hashes (`shasum -a 256 <file>`) and compare them with the hashes here. The commit times on this public repository show that each hash existed no later than that time, which is before the outcomes it is scored against were known.

An alarm in this study means "statistically unusual", never wrongdoing. No address is ever labelled an insider.

**Independent timestamps.**
- Each `*.txt` hash file has a `*.txt.ots` OpenTimestamps proof beside it, anchoring its SHA-256 in the Bitcoin blockchain.
- A proof is "pending" until a Bitcoin block confirms it, usually within hours. It is then upgraded and re-committed. Verify with `ots verify <file>.ots`.
- The repository is also submitted to Software Heritage for independent archival.
- Neither check requires trusting GitHub or the author.
