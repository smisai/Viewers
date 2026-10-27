# SMIS's OHIF fork (`smisai/Viewers`)

SMIS builds OHIF from this fork, branch `smis/v3.13`, which starts at OHIF's release tag `v3.13.13`.
The fork carries only what an OHIF extension cannot do; SMIS's own OHIF code lives in
`smisai/smis-ohif` (`@smis/extension-ai`, `@smis/mode-ai`). See `docs/SMIS_Repository_Organization.md`
in the SMIS core repository.

## What the fork adds to OHIF v3.13.13

| Change | Files |
|---|---|
| `@smis/extension-ai` and `@smis/mode-ai` linked from the `smis-ohif` checkout beside this one (`pnpm run cli link-extension` / `link-mode`) | `package.json`, `pnpm-workspace.yaml` (overrides), `pnpm-lock.yaml`, `platform/app/pluginConfig.json`, `platform/app/.webpack/webpack.pwa.js` |

Core hooks the OHIF-AI port needs will be added here, one commit each, and offered upstream.

## Building

The checkout sits at `smis/OHIF` and `smis-ohif` at `smis/smis-ohif` (the link paths are relative).
Node 24 or later and pnpm 12.8.1 (the `packageManager` field):

```
pnpm install
pnpm run build          # platform/app/dist
```

## Upstream

- Remote `upstream` is `OHIF/Viewers`. To move to a newer 3.13.x: rebase `smis/v3.13` onto the new
  tag (or merge it), rebuild, re-run SMIS's tests, and update `deployment/versions.yaml` in SMIS core.
