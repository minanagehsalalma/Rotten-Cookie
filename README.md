# extpatcher

ReVanced-style patch generator and patcher for unpacked Chrome extensions. It creates a portable zip bundle describing file operations (add, delete, replace) and the payload bytes needed to reproduce a modified extension from an original.

## Features

- Deterministic patch generation with payload files named by SHA-256.
- Safe patch application with fingerprint checks and manifest validation.
- Supports input/output as directories or zip archives.
- Optional verification mode.

## Usage

```bash
npm run build

# Create a patch bundle
npm start -- make --original ./Original --modified ./Modified --out ./patch-bundle.zip

# Apply a patch bundle to a directory
npm start -- apply --patch ./patch-bundle.zip --in ./Original --out ./Patched

# Apply a patch bundle to a zip
npm start -- apply --patch ./patch-bundle.zip --in ./Original.zip --out ./Patched.zip

# Verify an input against a patch bundle
npm start -- verify --patch ./patch-bundle.zip --in ./Original
```

## Notes

Patched extensions cannot remain installed via the Chrome Web Store. Chrome will treat them as unpacked extensions; you must load them in Developer Mode.
