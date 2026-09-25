---
status: generated
version: "0.1"
---

# Core concepts

## Organizations
The top-level container for a team. Users are invited to an organization and projects belong to it.

## Projects
A project holds everything for one product: keys, languages, translations, export configurations and members. Projects can be transferred and show an activity log.

## Keys
A key is a translatable string identifier such as `app.title`. Keys can have a description, **tags** and **placeholders**, and keep their own activity history.

## Languages
Each project defines the languages it translates into. One of them is the default language. Languages can be machine-translated in bulk.

## Translations
The content of a key in one language. Texterify supports pluralization.

## Export configurations
An export configuration describes how translations leave Texterify: the [file format](file-formats.md), file paths and per-language settings (**language configs**). The CLI `download` command and the export endpoint always use one export configuration.

## Flavors
A flavor is a named variant of a project's translations. Translations can be overridden per flavor, and an export configuration can be tied to a flavor, so the same keys can ship with different wording to different targets.

## Releases
A release publishes the current state of an export configuration so apps can fetch translations over the air.

## Validations and post processing rules
**Validations** check translations for problems and create **validation violations** you can fix or ignore. **Post processing rules** transform content during export. Forbidden-words lists help catch terms you never want to ship.

## Imports
Upload existing translation files to a language to bring legacy translations into a project.

## Access tokens
Personal secrets used, together with your email, to authenticate the CLI and the API.
