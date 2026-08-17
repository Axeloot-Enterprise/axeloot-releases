# Axeloot Æ — release feed

Public, unauthenticated update-discovery feed for on-prem Axeloot Æ installs.
Every deployed server polls `manifest.json` (raw URL) to learn whether a newer
release exists — no tokens, no configuration, no telemetry sent.

- `manifest.json` — current version per channel (published with each release)
- `notes/vX.Y.Z.md` — public release notes shown in the in-app "what's new" preview

The product itself is distributed privately (GHCR + offline bundles); this repo
contains **no code and no artifacts**, only version metadata and notes.

## Install Axeloot Æ (server)

Installation is from the **signed offline bundle** your vendor contact provides.
It needs no registry credentials and works on an air-gapped host:

```bash
tar xzf axeloot-bundle-<version>.tar.gz && cd axeloot-bundle-<version>
sudo ./deploy/linux/bootstrap-host.sh --source . --ssh-allow <your.ip>/32
sudo /opt/axeloot/deploy/linux/init-secrets.sh
sudo /opt/axeloot/deploy/linux/install.sh --image-archive "$PWD/images.tar.gz"
```

### The old one-command installer is retired

`curl … /ae | sudo bash` was written for the pre-5.8.0 deployment contract and
cannot bring up the current stack — it produced a directory that looked
installed and a stack that could not start. The `ae` file here is kept only so
an operator who still has that command is told where to go: it now refuses to
run and prints the sequence above.
