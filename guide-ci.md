---
status: generated
version: "0.1"
---

# Guide: download translations in CI

Keep translation files out of manual copy-paste by downloading them on every build.

## 1. Commit the project config

`texterify.json` holds no secrets, so commit it to your repository:

```json
{
    "api_base_url": "https://app.texterify.com/api",
    "api_version": "v1",
    "project_id": "<project id>",
    "export_configuration_id": "<export configuration id>",
    "export_directory": "translations"
}
```

## 2. Store credentials as CI secrets

Save your login email and an access token as secrets, for example `TEXTERIFY_EMAIL` and `TEXTERIFY_SECRET`. Do not commit `~/.texterify.json`.

## 3. Download in the pipeline

```sh
npm install -g texterify
texterify download --auth-email="$TEXTERIFY_EMAIL" --auth-secret="$TEXTERIFY_SECRET"
```

Command-line credentials take precedence over any global config, so no config file is needed on the CI runner.

## Several platforms from one project

Create one export configuration per platform (for example Android and iOS) and call `download` once per configuration:

```sh
texterify download --export-config-id <android-config-id> --auth-email="$TEXTERIFY_EMAIL" --auth-secret="$TEXTERIFY_SECRET"
texterify download --export-config-id <ios-config-id> --auth-email="$TEXTERIFY_EMAIL" --auth-secret="$TEXTERIFY_SECRET"
```

## Without the CLI

Call the export endpoint directly and unzip the result:

```sh
curl -H "Auth-Email: $TEXTERIFY_EMAIL" -H "Auth-Secret: $TEXTERIFY_SECRET" \
  -o translations.zip \
  "https://app.texterify.com/api/v1/projects/<project id>/exports/<export configuration id>"
unzip -o translations.zip -d translations
```
