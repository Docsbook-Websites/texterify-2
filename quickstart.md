---
status: generated
version: "0.1"
---

# Quickstart

This guide takes you from an empty account to translation files in your repository.

## 1. Create an account and a project

1. Sign up at [app.texterify.com/signup](https://app.texterify.com/signup) (or on your self-hosted instance).
2. Create an **organization**, then create a **project** inside it.
3. Add the **languages** you want to translate into.

## 2. Create an access token

Open **Settings → Access tokens** (`/dashboard/settings/access-tokens`) and create a token. The CLI and the API authenticate with your login email plus this token.

## 3. Install the CLI

```sh
npm install -g texterify
```

or

```sh
yarn global add texterify
```

## 4. Configure authentication

Create `~/.texterify.json` in your home folder and keep it private:

```json
{
    "auth_email": "email@example.com",
    "auth_secret": "<your access token>"
}
```

## 5. Configure your project

Put `texterify.json` in the root of your repository. It contains no secrets, so you can commit it:

```json
{
    "api_base_url": "https://app.texterify.com/api",
    "api_version": "v1",
    "project_id": "<project id>",
    "export_configuration_id": "<export configuration id>",
    "export_directory": "translations",
    "project_path": ""
}
```

The project ID is shown on the project overview page and in the project URL. Create an export configuration in the project first to get its ID.

## 6. Add a key and download translations

```sh
texterify add "app.title" en="MyApp" de="MeineApp"
texterify download
```

`download` fetches a zip for your export configuration and extracts it into `export_directory`.

Next: learn the [core concepts](concepts.md) or set up [downloads in CI](guide-ci.md).
