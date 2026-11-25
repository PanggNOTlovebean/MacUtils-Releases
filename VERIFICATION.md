# Verification — 2026-11-18

| Product | Version / build | Architecture | Swift tests | Environment skips | Source release commit |
|---|---|---|---|---|---|
| MacUtilRight | 1.3.4 / 9 | universal | 174 | 0 | `6426958e3065493deaae546137850940f0de7425` |
| MacUtilPaste | 1.8.3 / 24 | arm64 | 369 | 2 | `98f230ebbdea899a67268b458fe88687dda1a80a` |
| MacUtilBar | 1.0.2 / 3 | universal | 17 | 0 | `0e19eed6713c1605db6e413381c2580043b2e62b` |
| MacUtils | 1.14.3 / 55 | arm64 | 1077 | 4 | `07ddd465928c0f94d27de9e89f013d398803f9b5` |

All 1,637 tests completed with zero failures; six existing environment-dependent tests were skipped. Each release passed its release build and strict app code-signature verification, including embedded Finder extensions where present. Each PKG was expanded and its app payload compared file-for-file against the verified candidate. Every uploaded PKG and SHA-256 file was downloaded through the GitHub API and compared byte-for-byte before publication.

The exact production UpdateManifest and UpdateChecker implementation was compiled into an isolated network probe, without launching the product or reading user configuration. All four anonymous public raw feed URLs passed both paths: the shipped build reports current; the previous build reports an available update with the expected version and release page. A transient connection failure occurred on the first run; the repeated complete run passed all eight checks without retry.

During publishing, transport failures were recovered by inspecting draft assets rather than blindly overwriting. A duplicate unpublished draft was removed after verifying the published MacUtils release. GitHub's Git Data API was used to publish the exact feed tree when this host could not connect to github.com Git HTTPS; local and remote commit hashes were matched.

Manual clicks in the actual settings UI, browser downloads and native installation/extension upgrade interactions were not performed. No installed apps, privacy permissions or user configuration/history were changed. Applications are ad-hoc signed development candidates; PKGs are unsigned and not notarized. Existing installations need one manual installation to gain update checking.

MacUtilMouse remains design-only, without a Package.swift or application sources. Its local design documents now specify this update contract; no placeholder app, installer or live feed was published.

## MacUtilRight 1.3.5 / 10 — 2026-11-22

| Product | Version / build | Architecture | Swift tests | Environment skips | Source release commit |
|---|---|---|---|---|---|
| MacUtilRight | 1.3.5 / 10 | universal | 180 | 0 | `29f0176309fd64b74aec64e9929ce071c94c896d` |

Full Swift tests, universal release build, strict app and Finder extension code-signature verification, and extracted PKG payload comparison passed. The PKG and SHA-256 file were downloaded through the GitHub API and compared byte-for-byte before publication. Launching a CLI agent from Finder through iTerm, and the Automation consent prompt, were not validated natively.

## MacUtil · Bar 1.1.0 / 4 — 2026-11-22

| Product | Version / build | Architecture | Swift tests | Environment skips | Source release commit |
|---|---|---|---|---|---|
| MacUtil · Bar | 1.1.0 / 4 | universal | 22 | 0 | `20df32f65bbaf6fa905d9f62f21008644d29e3a1` |

Full Swift tests, universal release build, strict code-signature verification, and extracted PKG payload comparison passed. The PKG and SHA-256 file were downloaded through the GitHub API and compared byte-for-byte before publication. Collapse/reveal was measured from real window-server frames with a separate validation bundle ID; on the release host macOS currently shows no status items for `local.macutilbar.app` itself (a system menu-bar setting, documented in the release notes). Accessibility features (icon identification, moving, search panel) were not exercised with permission granted; installation and the icon-spacing write were not performed.

## MacUtil · Bar 1.1.1 / 5 — 2026-11-22

| Product | Version / build | Architecture | Swift tests | Environment skips | Source release commit |
|---|---|---|---|---|---|
| MacUtil · Bar | 1.1.1 / 5 | universal | 23 | 0 | `fd3bcb7c4eefdd3cb61f7a8e45426430c5014707` |

Opens Settings on manual launch. Full Swift tests, universal release build, strict code-signature verification, and extracted PKG payload comparison passed; PKG and SHA-256 round-tripped byte-for-byte through the GitHub API. Manual launch, --background and reopen were checked with a validation bundle ID through LaunchServices; login-item launch and installation were not performed.

## MacUtil · Bar 1.1.2 / 6 — 2026-11-22

| Product | Version / build | Architecture | Swift tests | Environment skips | Source release commit |
|---|---|---|---|---|---|
| MacUtil · Bar | 1.1.2 / 6 | universal | 23 | 0 | `a635ac7c02ab7a15a8538ce69fe10f6f7e64b7bf` |

Fixes settings and menu bar flashing. Full Swift tests, universal release build, strict code-signature verification, and extracted PKG payload comparison passed; PKG and SHA-256 round-tripped byte-for-byte through the GitHub API. With a validation bundle ID and the diagnostic icon list, 10 idle seconds produced no published state changes or status-item writes and no SwiftUI layout-cycle warnings. The icon list with real Accessibility permission and installation were not exercised.

## MacUtilMenu 1.4.0 / 11 — 2026-11-26

| Product | Version / build | Architecture | Swift tests | Environment skips | Source release commit |
|---|---|---|---|---|---|
| MacUtilMenu | 1.4.0 / 11 | universal | 186 | 0 | `ee3f72a7be2d0882ef8cd95277ec615ce5d01e8c` |

First release under the MacUtilMenu name (formerly MacUtilRight; new bundle identity `local.macutilmenu.app`). Full Swift tests, universal release build, strict app and Finder extension code-signature verification, and extracted PKG payload comparison passed. GitHub returned HTTP 500 and transport errors during publishing; the single matching draft was resumed, and both assets were downloaded through the GitHub API and compared byte-for-byte before publication. An anonymous download of the published PKG matched SHA-256 `9fe925a1927cd6b9d378b1800d476a518caccf1d2d01100f93d8b0d9d388a34b`. Launches through Ghostty, Warp, WezTerm, kitty and Alacritty, Finder clicks, the import button and PKG installation were not validated natively.
