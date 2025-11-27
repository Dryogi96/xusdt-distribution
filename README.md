# xUSDT Tokenlist & Distribution Repo

This repository contains the xUSDT token list, TrustWallet asset files, hosting docs, and CI workflows to publish the token list to GitHub Pages and optionally pin to IPFS.

## Included
- `docs/tokenlist.json` - tokenlist for MetaMask / tokenlist consumers
- `docs/index.html` - simple web UI to view/download tokenlist
- `assets/blockchains/smartchain/assets/<contract>/logo.png` - TrustWallet logo (256x256)
- `assets/blockchains/smartchain/assets/<contract>/info.json` - TrustWallet info.json
- `xUSDT_Whitepaper_UPDATED.pdf` - Whitepaper PDF
- `WHITEPAPER_UPDATED.md` - Whitepaper markdown

## How to publish (GitHub Pages)
1. Create a GitHub repository (or fork).
2. Push these files to the repo root.
3. In repository settings, enable GitHub Pages to serve from `gh-pages` branch or `/docs` folder (we include a workflow to deploy to Pages).
4. Configure repository secrets:
   - `WEB3_STORAGE_TOKEN` (optional) for IPFS pinning
   - `GH_PAT` (optional) if using actions requiring personal token

## Automation (GitHub Actions)
We include `.github/workflows/deploy.yml` which:
- Copies `docs/` to Pages and deploys
- Pins `docs/tokenlist.json` to IPFS using Web3.Storage (if `WEB3_STORAGE_TOKEN` secret provided)

Customize the `deploy.yml` secrets before enabling.

