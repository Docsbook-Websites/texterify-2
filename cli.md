---
status: generated
version: "0.1"
---

# CLI reference

The official CLI is published on npm as `texterify`.

```sh
npm install -g texterify
texterify -h
```

## Configuration files

- `~/.texterify.json` (global, private): `auth_email`, `auth_secret`.
- `texterify.json` (project root, safe to commit): `api_base_url`, `api_version`, `project_id`, `export_configuration_id`, `export_directory`, `project_path`.

Credentials passed with `--auth-email` and `--auth-secret` take precedence over the global config.

## `texterify add`

Add a new key with an optional default-language translation or per-language translations.

```sh
texterify add "app.title" "MyApp" --description "The name of the app."
texterify add "app.title" en="MyApp" de="MeineApp"
```

| Flag | Description |
| --- | --- |
| `--description` | Description of the key. |
| `--project-path` | Directory that contains `texterify.json`. |
| `--auth-email`, `--auth-secret` | Credentials for this call. |

If you pass both a default translation and `lang=content` pairs, the default one targets the project's default language.

## `texterify download`

Download the translations of an export configuration and extract them into `export_directory`.

```sh
texterify download
texterify download --export-config-id <id>
```

| Flag | Description |
| --- | --- |
| `--export-config-id` | Overrides `export_configuration_id`. |
| `--project-path` | Directory that contains `texterify.json`. |
| `--emojify` | Passed to the export endpoint. |
| `--auth-email`, `--auth-secret` | Credentials for this call. |

## `texterify open`

Open the current project in the browser, using `api_base_url` and `project_id` from `texterify.json`.

## `texterify use <name>`

Switch between servers. Store several global configs as `~/.texterify.json.<name>` and run `texterify use <name>` to copy one to `~/.texterify.json`.

```sh
texterify use serverA
```

## Upgrade

```sh
npm install -g texterify@latest
```
