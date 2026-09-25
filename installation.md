---
status: generated
version: "0.2"
---

# Self-hosting Texterify

Texterify can run on-premise so your translation data stays in your own infrastructure. The easiest way is the official Docker image with the `docker-compose` setup repository.

## Requirements

- `docker`
- `docker-compose`

## Install

```sh
# Clone the docker-compose configuration.
git clone https://github.com/texterify/texterify-docker-compose-setup.git
cd texterify-docker-compose-setup

# Generate a secret key for the app. Keep it private.
echo SECRET_KEY_BASE=`openssl rand -hex 64` > secrets.env

# Start the service.
docker volume create --name=texterify-database
docker volume create --name=texterify-assets
docker-compose up
```

When everything has started, create the database from a second terminal in the same directory:

```sh
docker-compose exec app bin/rails db:create db:migrate db:seed
```

The service is now available at `http://localhost`.

## Services

The stack runs the Texterify app, PostgreSQL and Redis (used by background jobs).

## Point the CLI at your instance

In `texterify.json`, set `api_base_url` to your server, for example `https://translations.example.com/api`. If you work with several servers, see `texterify use` in the [CLI reference](cli.md).

## Next steps

- [Configuration](configuration.md): SMTP, DeepL, sign-in and storage settings.
