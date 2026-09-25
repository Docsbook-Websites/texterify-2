---
status: generated
version: "0.1"
---

# Introduction

Texterify is a localization management platform (a translation management system, TMS) for translating apps, websites and other software. You manage keys, languages and translations in one place, then export them into the file format your code expects.

You can use it in two ways:

- **Texterify Cloud** at [app.texterify.com](https://app.texterify.com), managed by the team that builds Texterify.
- **On-premise**, self-hosted from the official Docker image `chrztoph/texterify` on your own infrastructure.

## What you can do

- Organize work in **organizations** and **projects**, and invite team members.
- Add **keys** with descriptions, tags and placeholders, and translate them per **language**.
- Import existing translation files and export them again through **export configurations** in 16 formats, including JSON, YAML, PO, XLIFF, Android, iOS `.strings`/`.stringsdict`, Flutter `.arb` and Java `.properties`.
- Machine-translate content with DeepL.
- Run **validations** and **post processing rules** on translations before they ship.
- Publish **releases** of an export configuration for over-the-air delivery.
- Automate everything from the terminal with the `texterify` CLI or the REST API (`/api/v1`).

## Where to go next

- [Quickstart](quickstart.md): from zero to downloaded translation files.
- [Self-hosting](installation.md): run Texterify on your own server.
- [CLI reference](cli.md) and [API reference](api.md).
- [Self-hosted alternative to Crowdin and Lokalise](crowdin-lokalise-alternative.md).

## License

Texterify is source-available under the Business Source License 1.1. Each version converts to the Apache License 2.0 four years after it is published. See the [LICENSE](https://github.com/txty-io/texterify/blob/master/LICENSE) file and [texterify.com/pricing](https://texterify.com/pricing).
