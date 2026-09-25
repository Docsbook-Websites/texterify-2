---
status: generated
version: "0.1"
---

# Self-hosted translation management system

**You can self-host Texterify, a translation management system with public source code, with Docker in a few commands; your keys and translations stay on your own servers.**

## Setup in short

```sh
git clone https://github.com/texterify/texterify-docker-compose-setup.git
cd texterify-docker-compose-setup
echo SECRET_KEY_BASE=`openssl rand -hex 64` > secrets.env
docker volume create --name=texterify-database
docker volume create --name=texterify-assets
docker-compose up
docker-compose exec app bin/rails db:create db:migrate db:seed
```

Texterify then runs at `http://localhost`. Full steps: [Self-hosting](installation.md).

## What you control

- **Data location.** PostgreSQL and file storage run on your infrastructure.
- **Who can sign up.** Admins can disable sign-ups and restrict allowed email domains.
- **Email.** Use your own SMTP server.
- **Machine translation.** Bring your own DeepL API token.

See [Configuration](configuration.md) for every setting.

## Working with several servers

If some projects live on Texterify Cloud and others on your own instance, keep one global config per server and switch with `texterify use <name>`. See [CLI reference](cli.md#texterify-use-name).
