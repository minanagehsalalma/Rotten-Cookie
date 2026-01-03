<img width="200" height="200" alt="Logo" src="https://github.com/user-attachments/assets/032b1711-1a2a-4c60-b852-bdb0461767ba" align="center" />

# Cookie-Editor Auto-Export Patch 

This repo contains a patch bundle for Cookie-Editor (v1.13.0, MV3). It is not the extension itself. You apply the patch to an original, unmodified Cookie-Editor folder using the [extpatcher](https://github.com/minanagehsalalma/RevancedForChromeExtensions) CLI. Work on Both Desktop and mobile browsers
<img width="1080" height="346" alt="image" src="https://github.com/user-attachments/assets/b5950f36-3068-4b15-accc-13621a579da1" />

## What this patch changes

Quality-of-life additions:
- Auto-export cookies to a Discord webhook when a matching domain finishes loading.
- New Automation Settings section in the options page (target domain, webhook URL, countdown toggle).
- Optional 5-second confirmation banner with Send/Cancel before auto-export.
- Domain normalization so you can enter `example.com` or a full URL; subdomains are included.

Other changes:
- Adds permissions needed for automation (`activeTab`, `scripting`) and host permissions for Discord webhooks.
- Removes `_metadata/verified_contents.json` (Chrome Web Store verification file).
- Adds `AGENTS.md` (developer notes; no runtime impact. Makes it easier if you want to mod another feature to the extention urself).

## Requirements

- Node.js 20+
- The [extpatcher](https://github.com/minanagehsalalma/RevancedForChromeExtensions) CLI (see the patcher repo)

## How to apply 

1) Get the original Cookie-Editor source folder  
   - Must be version `1.13.0` (Manifest V3).
   - Download it using [Crx4Chrome](https://www.crx4chrome.com/) you search the extension name and version there, and after downloading it unpack it using 7 zip.
     
2) Download the patch bundle from this repo  
   - Example: `cookie-editor.patch.zip`

3) Apply the patch with [extpatcher](https://github.com/minanagehsalalma/RevancedForChromeExtensions)  
```bash
extpatcher apply --patch ./cookie-editor.patch.zip --in ./Cookie-Editor-Original --out ./Cookie-Editor-Patched
```

4) Load the patched extension  
   - Open `chrome://extensions`
   - Enable Developer Mode
   - Click “Load unpacked” and select `Cookie-Editor-Patched`
     
5) On the extension icon click see all option and from there scroll to Automation Settings and input ur target domain and ur own Discord webhook and click save settings that's it
<table width="100%">
  <tr>
    <td width="50%" align="center" valign="top">
      <a href="https://github.com/user-attachments/assets/f44aa946-c44b-41ca-b5c9-c8bcf0760e39">
        <img
          src="https://github.com/user-attachments/assets/f44aa946-c44b-41ca-b5c9-c8bcf0760e39"
          width="100%"
          alt="Screenshot 1"
          style="border-radius: 16px; border: 1px solid rgba(255,255,255,0.12); box-shadow: 0 10px 30px rgba(0,0,0,0.35);"
        />
      </a>
    </td>
    <td width="50%" align="center" valign="top">
      <a href="https://github.com/user-attachments/assets/236009dd-df80-4b75-97ec-68f80bca7960">
        <img
          src="https://github.com/user-attachments/assets/236009dd-df80-4b75-97ec-68f80bca7960"
          width="100%"
          alt="Screenshot 2"
          style="border-radius: 16px; border: 1px solid rgba(255,255,255,0.12); box-shadow: 0 10px 30px rgba(0,0,0,0.35);"
        />
      </a>
    </td>
  </tr>
</table>

## To use on android 
1. download kiwibrowser the github release https://github.com/kiwibrowser/src.next/releases/tag/14310011181

2. open the extensions menu , load the zip file (you need to this the unpacked patched extension folder after patching)

3. The rest of the steps are the same as using it on Desktop

4. for more advanced use cases you can use the extension with an android macro that opens a target website on a specified time each day. for that to work smoothly you need to disable battery optimization for kiwi browser. and you can trigger/control the target domain remotely if you use something like macrodroid webhooks.

## Important notes

- This patch sends cookies to a Discord webhook URL. Only use it with webhooks you control.
- The patcher verifies fingerprints and will refuse to apply to the wrong version.
- Patched extensions cannot remain Web Store–installed; they must be loaded as unpacked extensions.

## Patcher

Use the `extpatcher` CLI to apply this patch:
- https://github.com/minanagehsalalma/RevancedForChromeExtensions
