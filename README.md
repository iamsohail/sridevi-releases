# Sridevi Industries Releases

## Overview

Static APK download repository for Sridevi Industries Android users. Download: https://iamsohail.github.io/sridevi-releases/app-release.apk.

## Status

Active

## Current functionality

Hosts the approved Android release APK for direct download and the app’s updater.

## Recent changes

- 2026-11-07 (wave 2): Convention audit fixes: the `ci` gate reads job results through an env variable; `validate` sits behind a docs-only `changes` job (the `ci` check still always reports); Setup lists prerequisites and commands.
- 2026-11-07: Convention cross-review fixes: added a light `ci` check (JSON parses, HTML local links exist, nothing tracked over 100 MB; owner decision 2026-11-07), which also gives the monthly github-actions Dependabot entry a workflow to update; Pending says no issues are recorded.

- 2026-11-06: Applied repository convention audit fixes to documentation and repository configuration.

- 2026-11-06: Applied the BlackBuck repository convention to documentation and repository hygiene; application behavior is unchanged.

## Pending / known issues

No known issues recorded as of 2026-11-07.

## Setup

No local setup or build step: the only prerequisite is `git` (Python 3 if you want to rerun the CI integrity check locally).

```bash
git clone https://github.com/iamsohail/sridevi-releases.git
cd sridevi-releases
```

To publish an approved APK, follow `RELEASE_CHECKLIST.md` in the Android app repository (`blackbuck-solutions/sridevi-industries-app`); GitHub Pages serves `main` automatically.

## Credentials

No configuration or credentials are read by this repository, so there is no `.env.example`. GitHub account access stays outside Git.

## Deploy

GitHub Pages serves the Android APK at https://iamsohail.github.io/sridevi-releases/app-release.apk. The Android release procedure publishes the approved APK here; this repository is a static download site. CI (`.github/workflows/ci.yml`) only checks integrity and never deploys; Pages publishes `main` by itself. Published files are unchanged by repository hygiene updates.

## Owner

Foreman coordinator (Claude)
