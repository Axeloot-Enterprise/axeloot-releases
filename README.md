# Axeloot Æ — release feed

Public, unauthenticated update-discovery feed for on-prem Axeloot Æ installs.
Every deployed server polls `manifest.json` (raw URL) to learn whether a newer
release exists — no tokens, no configuration, no telemetry sent.

- `manifest.json` — current version per channel (published by the release pipeline)
- `notes/vX.Y.Z.md` — public release notes shown in the in-app "what's new" preview

The product itself is distributed privately (GHCR + offline bundles); this repo
contains **no code and no artifacts**, only version metadata and notes.
