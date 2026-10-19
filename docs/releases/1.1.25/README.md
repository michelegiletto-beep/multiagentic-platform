# Multiagentic Platform 1.1.25 release record

**Date:** 19 October 2026 · **Channel:** release · **Runtime:** `NATIVE_ONLY`

[Download Windows installer](https://github.com/michelegiletto-beep/multiagentic-platform/releases/download/v1.1.25/MultiagenticPlatform-Setup-1.1.25.exe) · [Installation guide](../../INSTALLATION.md) · [Release notes](RELEASE-NOTES.txt) · [Binary licence](LICENSE.txt)

This public distribution is based on rc.49 with revised packaging, personal-account onboarding and separate package verification. Historical rc.49 checks are not relabelled as tests of this installer. The package connects to accounts supplied by its users; no broker credentials, sample account or synthetic market feed are bundled. First launch has no configured agents, accounts or trading workers.

## Installer identity

| Property | Value |
| --- | --- |
| File | `MultiagenticPlatform-Setup-1.1.25.exe` |
| Bytes | 84,921,344 |
| SHA-256 | `0fbafa46452a4c9bac3a53c395d778ec50c4312f82119cada7078d25ec9e608b` |
| Authenticode | `NotSigned` |
| Installation | Per-user Windows x64; standalone package, no previous installation required |

The file size and SHA-256 match the authoritative final delivery manifest. The SHA-256 and unsigned status were also checked directly on the delivered EXE. A hash identifies that file; it is not a publisher certificate.

## Recorded verification and its limits

[TEST-RESULTS.json](TEST-RESULTS.json) reports 64 passing compiled tests with mock clients, exact production-payload verification of 494 files, isolated Windows installation, empty first launch, personal-account broker forms and uninstall checks. Installation QA used a disposable namespace with the same runtime; production-profile configuration was statically verified. The broker forms' 202 UI assets matched the final package.

The checks ran on the existing Windows host rather than a clean new-user or virtual-machine matrix. No personal installation was replaced, no credentials were entered and no live broker request or trade was executed during this campaign. Native graceful-shutdown confirmation was not tested. See the full [validation account](../../VALIDATION.md) and [known limitations](KNOWN-LIMITATIONS.txt).

The release does not declare fixes for the recorded stale-price, partial REST-fallback, timeout or `BROKER_DISPATCH_NOT_SENT` findings. IG CFD/OANDA live qualification, simultaneous multi-broker certification and financial performance remain outside this package-test result.

## Runtime and rights

The installer includes the compiled/minified runtime, one essential Windows intent-lock recovery helper and the SPINS inference weights needed by the application. Those original components remain proprietary and inspectable. Original TypeScript and the developer checkout, source maps, trainers, datasets and private operational records are excluded. Luna/OpenAI and Qwen are disabled; no Qwen model or GPU/LLM runtime is included or downloaded by installation.

Use is governed by [LICENSE.txt](LICENSE.txt); third-party components retain their own [notices and licences](THIRD-PARTY-NOTICES.txt). The historical SPINS training record describes local CPU fits on synthetic instruction policies, independently of the real account and market observations supplied by a connected broker.

## Public document provenance

The following files were copied without edits from the final **MultiagenticPlatform-1.1.25** delivery dated 19 October 2026. They were reviewed for private paths, credentials and account records; no redaction was required. Their byte hashes match that delivery's manifest. Document paths such as `%LOCALAPPDATA%` are installation instructions rather than the developer's private filesystem.

| File | SHA-256 |
| --- | --- |
| [START-HERE.txt](START-HERE.txt) | `08880f4382d7673e61679934a418f07e1659c0bc6fdbf7bcaad6e5b1b7675753` |
| [LICENSE.txt](LICENSE.txt) | `40f2d119ba1ed04655696d2550f5fb2f924041d16e72828e39f8fac8712f314f` |
| [RELEASE-NOTES.txt](RELEASE-NOTES.txt) | `d233163b6dcd9567e28c051f8910082daf8ccabe7b8b6afa55adbd70ea52931c` |
| [KNOWN-LIMITATIONS.txt](KNOWN-LIMITATIONS.txt) | `a8f6ed31344d7e5196d372902bb9d0d7ef7b9945b1539bd9b8b215673d040ee5` |
| [TEST-RESULTS.json](TEST-RESULTS.json) | `21d5c86b7b21556fd93a465edafe2087b304c028d5e9aeb967ae2d8c3ab6173c` |
| [REQUIREMENTS.txt](REQUIREMENTS.txt) | `13f99dbc711c838bb03bd82621048d1c9d2a5bfca10e8c6301bf0ccb65dda4c3` |
| [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt) | `9bb2206bf0fdecdbb479a9a7399f0c5e265807003bd18a3c47278e84a5f4060b` |
