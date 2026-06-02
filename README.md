# scoop-nole

[Scoop](https://scoop.sh) bucket for **[Nólë](https://github.com/dorukardahan/nole)** (`nole`) — a free web-search router/gateway for AI agents and coding CLIs.

## Install (Windows)

```powershell
scoop bucket add nole https://github.com/dorukardahan/scoop-nole
scoop install nole
nole version
```

## How this bucket works

- **`nole.json`** (this repo's root) is the Scoop manifest. It points `64bit` and `arm64` at the matching `nole-windows-<arch>.exe` GitHub Release asset and pins each asset's `sha256` — Scoop's fail-closed integrity check.
- The manifest is **auto-updated on every stable Nólë release** by the `Update Scoop bucket` step in the main repo's [`release.yml`](https://github.com/dorukardahan/nole/blob/main/.github/workflows/release.yml). Its source of truth is [`packaging/scoop/nole.json.tmpl`](https://github.com/dorukardahan/nole/blob/main/packaging/scoop/nole.json.tmpl) — edit it **there**, not here.

## Verify the download (optional)

Each release carries a keyless build-provenance attestation:

```powershell
gh attestation verify (scoop which nole) --repo dorukardahan/nole
```
