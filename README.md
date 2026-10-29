# Agentsteam Skills

Source of truth for Agentsteam skill packages and the bilingual website catalogue.

## Use a skill without installing anything

Choose a package under skills/en or skills/pl. Download this repository's archive into a temporary directory, then read the complete SKILL.md and the supporting files relevant to your task. Resolve relative paths from that skill's directory.

- Windows: PowerShell Invoke-WebRequest and Expand-Archive with https://github.com/agentsteam/skills/archive/refs/heads/main.zip
- Linux: curl or wget, then tar with https://github.com/agentsteam/skills/archive/refs/heads/main.tar.gz
- Python: urllib.request, zipfile, tempfile and pathlib from the standard library.

When the assistant cannot download files, attach the skill ZIP downloaded from the website. Python can extract an attached ZIP without network access. Optional persistent installation remains available through npx skills add and the exact language folder URL.

## Packages and publication

Each package contains SKILL.md, skill-manifest.json, LICENSE.txt and its supporting files. Distribution version: 1.0.0. Initial release: 2026-10-01. Original provenance and copyright notices remain unchanged.

The ordered website catalogue and page copy live in catalogue/en.json and catalogue/pl.json. The English product-video package remains available here but is intentionally absent from the website catalogue. catalogue/source-inventory.json records the upstream runtime file inventory for the ten bilingual skills.

The website imports the latest packages from main through vp run skills:sync in agentsteam/hyperapp-build. Update packages here first, then run the sync command. Builds and web requests use the validated local snapshot without contacting GitHub. Usage prompts and optional installation commands always fetch the latest packages from main.
