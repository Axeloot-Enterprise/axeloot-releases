# Axeloot Æ — release feed

Public, unauthenticated update-discovery feed for on-prem Axeloot Æ installs.
Every deployed server polls `manifest.json` (raw URL) to learn whether a newer
release exists — no tokens, no configuration, no telemetry sent.

- `manifest.json` — current version per channel (published by the release pipeline)
- `notes/vX.Y.Z.md` — public release notes shown in the in-app "what's new" preview

The product itself is distributed privately (GHCR + offline bundles); this repo
contains **no code and no artifacts**, only version metadata and notes.

## Install Axeloot Æ (server)

```bash
curl -fsSL https://get.axeloot.com/ae | sudo bash
```

`/ae` is the one-command Docker installer (`deploy/bootstrap.sh` from the
product repo, synced on every release). Until DNS is live, the same file is at
`https://raw.githubusercontent.com/Axeloot-Enterprise/axeloot-releases/main/ae`.
