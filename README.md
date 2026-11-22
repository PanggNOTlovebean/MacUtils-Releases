# MacUtils Releases

Public installer downloads and manual update feeds for the MacUtil family. Application source repositories remain separate; no source code or user data is published here.

In each app, open General / Basic settings → Software Update → Check for Updates. The app fetches its public feed only on request, then opens the matching GitHub release page. Download the PKG for your Mac and install it manually. No automatic installation or background checking.

These are development candidates: the applications are ad-hoc signed and the PKGs are unsigned and not notarized. The first version with update checking must be installed manually.

## Products

| Product | Latest release | Feed | Architecture |
|---|---|---|---|
| MacUtilRight | [1.3.5](https://github.com/PanggNOTlovebean/MacUtils-Releases/releases/tag/MacUtilRight-v1.3.5) | `feeds/MacUtilRight.json` | Apple Silicon + Intel |
| MacUtil · Paste | [1.8.3](https://github.com/PanggNOTlovebean/MacUtils-Releases/releases/tag/MacUtilPaste-v1.8.3) | `feeds/MacUtilPaste.json` | Apple Silicon |
| MacUtil · Bar | [1.0.2](https://github.com/PanggNOTlovebean/MacUtils-Releases/releases/tag/MacUtilBar-v1.0.2) | `feeds/MacUtilBar.json` | Apple Silicon + Intel |
| MacUtils | [1.14.3](https://github.com/PanggNOTlovebean/MacUtils-Releases/releases/tag/MacUtils-v1.14.3) | `feeds/MacUtils.json` | Apple Silicon |

MacUtilMouse is currently a design-only project and has no installer or live feed.

## Publishing

Each release uses the tag `<Product>-v<semantic-version>` and contains a PKG plus SHA-256 checksums. Publish and verify the release assets before updating the corresponding feed. Never reuse a published version or lower its build number. Keep old release assets available.

Feed schema 1: `schemaVersion`, `product`, `bundleIdentifier`, `version` (three numeric components), `build` (positive increasing integer), `minimumSystemVersion` (three numeric components), and an HTTPS `releaseURL` pointing to this repository's exact product/version release tag.

The feeds contain no executable commands, installation scripts, credentials, user IDs, clipboard contents or configuration data.

See [verification results](VERIFICATION.md) for test coverage and native-interaction limits.
