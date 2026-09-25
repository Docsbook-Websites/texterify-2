---
status: generated
version: "0.1"
---

# REST API reference

All endpoints live under `/api/v1` (for the cloud: `https://app.texterify.com/api/v1`) and return JSON.

## Authentication

Send two headers on every request:

```
Auth-Email: you@example.com
Auth-Secret: <access token>
```

Create access tokens under **Settings → Access tokens**.

## Projects

| Method | Path | Description |
| --- | --- | --- |
| GET | `/projects` | List projects |
| POST | `/projects` | Create a project |
| GET | `/projects/:id` | Show a project |
| PUT | `/projects/:id` | Update a project |
| DELETE | `/projects/:id` | Delete a project |
| POST | `/projects/:project_id/import` | Import a translation file |
| GET | `/projects/:project_id/exports/:export_config_id` | Download an export (zip) |
| GET | `/projects/:project_id/activity` | Project activity |
| POST | `/projects/:project_id/transfer` | Transfer a project |

The export endpoint returns `NO_LANGUAGES_FOUND_TO_EXPORT` if the project has no languages.

## Keys

| Method | Path |
| --- | --- |
| GET, POST | `/projects/:project_id/keys` |
| GET, PUT, DELETE | `/projects/:project_id/keys/:id` |
| DELETE | `/projects/:project_id/keys` (multiple) |
| GET | `/projects/:project_id/keys/:key_id/activity` |
| GET, POST, DELETE | `/projects/:project_id/keys/:key_id/placeholders` |
| POST, DELETE | `/projects/:project_id/keys/:key_id/tags` |

## Languages and translations

| Method | Path |
| --- | --- |
| GET, POST | `/projects/:project_id/languages` |
| GET, PUT, DELETE | `/projects/:project_id/languages/:id` |
| POST | `/projects/:project_id/languages/:language_id/machine_translate` |
| POST | `/projects/:project_id/translations` |
| POST | `/projects/:project_id/translations/:translation_id/machine_translation_suggestion` |

## Export configurations and releases

| Method | Path |
| --- | --- |
| GET, POST | `/projects/:project_id/export_configs` |
| PUT, DELETE | `/projects/:project_id/export_configs/:id` |
| GET, POST, PUT, DELETE | `/projects/:project_id/export_configs/:export_config_id/language_configs` |
| POST | `/projects/:project_id/export_configs/:export_config_id/releases` |
| GET | `/projects/:project_id/releases` |

## Quality

| Method | Path |
| --- | --- |
| GET, POST, PUT, DELETE | `/projects/:project_id/validations` |
| POST | `/projects/:project_id/validations_check` |
| GET, PUT, DELETE | `/projects/:project_id/validation_violations` |
| GET, POST, PUT, DELETE | `/projects/:project_id/post_processing_rules` |
| GET, POST, PUT, DELETE | `/projects/:project_id/flavors` |
| GET, POST, PUT, DELETE | `/projects/:project_id/members` |
