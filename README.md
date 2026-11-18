# MacUtils Releases

Public installer downloads and manual update feeds for the MacUtil family. Application source repositories remain separate; no source code or user data is published here.

In each app, open General / Basic settings → Software Update → Check for Updates. The app fetches its public feed only on request, then opens the matching GitHub release page. Download the PKG for your Mac and install it manually. No automatic installation or background checking.

These are development candidates: the applications are ad-hoc signed and the PKGs are unsigned and not notarized. The first version with update checking must be installed manually.

## Products

| Product | Feed | Architecture |
|---|---|---|
| MacUtilRight | `feeds/MacUtilRight.json` | Apple Silicon + Intel |
| MacUtil · Paste | `feeds/MacUtilPaste.json` | Apple Silicon |
| MacUtil · Bar | `feeds/MacUtilBar.json` | Apple Silicon + Intel |
| MacUtils | `feeds/MacUtils.json` | Apple Silicon |

MacUtilMouse is currently a design-only project and has no installer or live feed.

## Publishing

Each release uses the tag `<Product>-v<semantic-version>` and contains a PKG plus SHA-256 checksums. Publish and verify the release assets before updating the corresponding feed. Never reuse a published version or lower its build number. Keep old release assets available.

Feed schema 1: `schemaVersion`, `product`, `bundleIdentifier`, `version` (three numeric components), `build` (positive increasing integer), `minimumSystemVersion` (three numeric components), and an HTTPS `releaseURL` pointing to this repository's exact product/version release tag.

The feeds contain no executable commands, installation scripts, credentials, user IDs, clipboard contents or configuration data.
