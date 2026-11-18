# Sridevi Industries Releases

## Overview

Static APK download repository for Sridevi Industries Android users. Download: https://iamsohail.github.io/sridevi-releases/app-release.apk.

## Status

Active

## Current functionality

Hosts the approved Android release APK for direct download and the app’s updater.

### Current release

| | |
|---|---|
| Version | 2.11.3 (versionCode 41), committed 2026-10-09 (`78e17b0`) |
| File | `app-release.apk` (about 38 MB), the only file the app and users download |
| SHA-256 | `5f580fd05d518a6d274be6125e537b5e791624ab21ed07d7814924e512ff304f` |
| Served | https://iamsohail.github.io/sridevi-releases/app-release.apk (verified 2026-11-18: served bytes match `main`) |
| Updater | The app reads `latest_version_code`, `update_url`, `apk_sha256` and `force_update` from Firebase Remote Config (managed in `blackbuck-solutions/sridevi-industries-app`), not from this repo. |

## Recent changes

- 2026-11-18: Repository audit ([docs/AUDIT-2026-11-18.md](docs/AUDIT-2026-11-18.md)): README gains the current release and the public-repo rules; every historical APK scanned for embedded keys. No change to the published file.
- 2026-11-07 (wave 2): Convention audit fixes: the `ci` gate reads job results through an env variable; `validate` sits behind a docs-only `changes` job (the `ci` check still always reports); Setup lists prerequisites and commands.
- 2026-11-07: Convention cross-review fixes: added a light `ci` check (JSON parses, HTML local links exist, nothing tracked over 100 MB; owner decision 2026-11-07), which also gives the monthly github-actions Dependabot entry a workflow to update; Pending says no issues are recorded.

- 2026-11-06: Applied repository convention audit fixes to documentation and repository configuration.

- 2026-11-06: Applied the BlackBuck repository convention to documentation and repository hygiene; application behavior is unchanged.

## Pending / known issues

- The repository's GitHub *Release* `v1.9.1` (Releases tab, marked "Latest") still carries a v1.9.1 APK. It is not the update path, but a person browsing the repo could install it. Owner decision: delete that release or mark it outdated.
- Historical commits keep every earlier APK (v1.9.1 to v2.11.2); see the audit for what they contain.

## Setup

No local setup or build step: the only prerequisite is `git` (Python 3 if you want to rerun the CI integrity check locally).

```bash
git clone https://github.com/iamsohail/sridevi-releases.git
cd sridevi-releases
```

To publish an approved APK, follow `RELEASE_CHECKLIST.md` in the Android app repository (`blackbuck-solutions/sridevi-industries-app`); GitHub Pages serves `main` automatically.

## Credentials

No configuration or credentials are read by this repository, so there is no `.env.example`. GitHub account access stays outside Git.

**This repository is public.** Commit only the signed release APK and documentation. Never commit keystores, `google-services.json`, `.env` files, build logs or release notes that name internal systems; `.gitignore` blocks the common ones. Before every push, run `scripts/verify-release-apk.sh` (in the app repo) on the APK: it checks the signing certificate, Firebase project and that no AI key is compiled in.

## Deploy

GitHub Pages serves the Android APK at https://iamsohail.github.io/sridevi-releases/app-release.apk. The Android release procedure publishes the approved APK here; this repository is a static download site. CI (`.github/workflows/ci.yml`) only checks integrity and never deploys; Pages publishes `main` by itself. Published files are unchanged by repository hygiene updates.

## Owner

Foreman coordinator (Claude)
