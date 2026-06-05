# Hermes Desktop — Standalone Fork

A standalone fork of [Hermes Agent](https://github.com/NousResearch/hermes-agent) Desktop app.

**Same UI, same Electron shell — no monorepo workspace needed.**

## What's different

- Fully standalone — clone, `npm install`, `npm run dev` and go
- Includes `@hermes/shared` as a local workspace package (`packages/shared/`)
- No dependency on the Hermes Agent Python monorepo root

## Requirements

- Node.js `^20.19.0 || >=22.12.0`
- npm 10+
- Python 3.11+ (Hermes Agent backend, installed on first launch)

## Quick start

```bash
npm install
npm run dev
```

This starts the Vite dev server + Electron pointing at `http://127.0.0.1:5174`.

## Build

```bash
# Unpacked directory under release/
npm run pack

# Platform installers
npm run dist:mac      # DMG + zip
npm run dist:win      # NSIS + MSI
npm run dist:linux    # AppImage + deb + rpm
```

## How it works

The packaged app ships only the Electron shell. On first launch it installs the Hermes Agent runtime into `HERMES_HOME` (`~/.hermes`). The renderer (React) talks to a `hermes dashboard` backend over standard gateway WebSocket APIs.

## Upstream

This is a fork of `apps/desktop` from [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent). See upstream for the full agent backend, CLI, and other surfaces.

## License

MIT — see [LICENSE](./LICENSE).
