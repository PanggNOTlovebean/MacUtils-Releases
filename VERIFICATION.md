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
