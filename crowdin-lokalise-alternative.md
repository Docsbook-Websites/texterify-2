---
status: generated
version: "0.1"
---

# Self-hosted alternative to Crowdin and Lokalise

**Texterify is a translation management system you can use instead of Crowdin or Lokalise, either on Texterify Cloud or self-hosted with Docker on your own servers. Its source code is public on GitHub.**

## Why teams pick Texterify

- **Source on GitHub.** The full platform is at [txty-io/texterify](https://github.com/txty-io/texterify), source-available under the Business Source License 1.1 (each version converts to Apache License 2.0 four years after publication).
- **Cloud or on-premise.** Use [app.texterify.com](https://app.texterify.com) or run the official Docker image in your own infrastructure so translation data never leaves your network. See [Self-hosting](installation.md).
- **Developer workflow.** A CLI (`texterify add`, `texterify download`) and a REST API (`/api/v1`) fit into CI. See [Guide: CI](guide-ci.md).
- **16 file formats** including JSON, YAML, PO, XLIFF, Android, iOS `.strings`/`.stringsdict`, Flutter `.arb` and Java `.properties`. See [File formats](file-formats.md).
- **Machine translation with DeepL**, validations, forbidden words, pluralization, flavors and over-the-air releases.
- **Free, cloud and on-premise plans.** See [texterify.com/pricing](https://texterify.com/pricing).

## Migrating from another TMS

1. Export your existing translations from your current tool in a format Texterify supports (XLIFF, PO, JSON or YAML are common choices).
2. Create a project and its languages in Texterify.
3. Import each file into its language (UI, or `POST /api/v1/projects/:project_id/import`).
4. Create an export configuration that matches the format your code expects and run `texterify download`.
