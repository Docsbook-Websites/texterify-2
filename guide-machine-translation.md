---
status: generated
version: "0.1"
---

# Guide: machine translation with DeepL

Texterify uses DeepL to machine-translate content.

## Self-hosted

Set `DEEPL_API_TOKEN` in your environment. Without it, the machine translation endpoints are disabled.

## Translate a whole language

From the language list, run machine translation for a target language. Via the API:

```
POST /api/v1/projects/:project_id/languages/:language_id/machine_translate
```

## Get a suggestion for one translation

```
POST /api/v1/projects/:project_id/translations/:translation_id/machine_translation_suggestion
```

## Tips

- Keep key descriptions meaningful. They give translators context when reviewing machine output.
- Use [validations](concepts.md#validations-and-post-processing-rules) to catch problems before export.
