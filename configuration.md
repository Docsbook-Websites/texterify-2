---
status: generated
version: "0.1"
---

# Configuration

A self-hosted Texterify instance is configured with environment variables. The list below is taken from the Texterify source code.

## Core

| Variable | Purpose |
| --- | --- |
| `SECRET_KEY_BASE` | Rails secret used to sign sessions. Required. Generate with `openssl rand -hex 64`. |
| `DATABASE_URL` | PostgreSQL connection string. |
| `REDIS_URL` | Redis connection used by the app. |
| `SIDEKIQ_REDIS_SERVER_URL`, `SIDEKIQ_REDIS_CLIENT_URL` | Redis connections for background jobs. |
| `APP_HOST` | Public host of your instance. |
| `ASSET_HOST` | Optional host for static assets. |
| `PORT`, `WEB_CONCURRENCY`, `RAILS_MAX_THREADS`, `RAILS_MIN_THREADS` | Web server tuning. |
| `RAILS_SERVE_STATIC_FILES`, `RAILS_LOG_TO_STDOUT` | Standard Rails production switches. |

## Email (SMTP)

`SMTP_ADDRESS`, `SMTP_PORT`, `SMTP_DOMAIN`, `SMTP_USERNAME`, `SMTP_PASSWORD`, `SMTP_AUTHENTICATION`, `SMTP_ENABLE_STARTTLS_AUTO`, `SMTP_TLS`, `SMTP_OPENSSL_VERIFY_MODE`, `SMTP_FROM_EMAIL`.

`EMAIL_CONFIRMATION_REQUIRED` controls whether new users must confirm their email address.

## Machine translation

| Variable | Purpose |
| --- | --- |
| `DEEPL_API_TOKEN` | Enables DeepL machine translation. Without it, machine translation endpoints refuse requests. |

## Sign in with Google

`OMNIAUTH_GOOGLE_CLIENT_ID` and `OMNIAUTH_GOOGLE_CLIENT_SECRET`.

## Error reporting

`SENTRY_DSN_BACKEND` sends backend errors to Sentry.

## Instance administration

Instance admins can restrict sign-ups and filter allowed email domains from the instance settings (API: `PUT /api/v1/instance/sign-up-enabled` and `PUT /api/v1/instance/domain-filter`), and list or remove users (`GET /api/v1/instance/users`).
