# Cookie-Editor Auto-Export Patch

This repo contains a patch bundle for Cookie-Editor (v1.13.0, MV3). It is not the extension itself. You apply the patch to an original, unmodified Cookie-Editor folder using the `extpatcher` CLI.

## What this patch changes

Quality-of-life additions:
- Auto-export cookies to a Discord webhook when a matching domain finishes loading.
- New Automation Settings section in the options page (target domain, webhook URL, countdown toggle).
- Optional 5-second confirmation banner with Send/Cancel before auto-export.
- Domain normalization so you can enter `example.com` or a full URL; subdomains are included.

Other changes:
- Adds permissions needed for automation (`activeTab`, `scripting`) and host permissions for Discord webhooks.
- Removes `_metadata/verified_contents.json` (Chrome Web Store verification file).
- Adds `AGENTS.md` (developer notes; no runtime impact).

## Requirements

- Node.js 20+
- The `extpatcher` CLI (see the patcher repo)

## How to apply

1) Get the original Cookie-Editor source folder  
   - Must be version `1.13.0` (Manifest V3).  
   - You can use the unpacked extension folder from the official source.

2) Download the patch bundle from this repo  
   - Example: `cookie-editor.patch.zip`

3) Apply the patch with extpatcher  
```bash
extpatcher apply --patch ./cookie-editor.patch.zip --in ./Cookie-Editor-Original --out ./Cookie-Editor-Patched
```

4) Load the patched extension  
   - Open `chrome://extensions`
   - Enable Developer Mode
   - Click “Load unpacked” and select `Cookie-Editor-Patched`

## Important notes

- This patch sends cookies to a Discord webhook URL. Only use it with webhooks you control.
- The patcher verifies fingerprints and will refuse to apply to the wrong version.
- Patched extensions cannot remain Web Store–installed; they must be loaded as unpacked extensions.

## Patcher

Use the `extpatcher` CLI to apply this patch:
- https://github.com/<your-org-or-user>/extpatcher
