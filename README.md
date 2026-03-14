# Learning with Texts

[![Latest Stable Version](https://poser.pugx.org/hugofara/lwt/v)](https://packagist.org/packages/hugofara/lwt)
[![Docker Image](https://github.com/HugoFara/lwt/actions/workflows/docker-image.yml/badge.svg)](https://github.com/HugoFara/lwt/actions/workflows/docker-image.yml)
[![Discord Server](https://badgen.net/discord/members/zAE8GXMKFa?icon=discord)](https://discord.gg/zAE8GXMKFa)

**Learning with Texts** (LWT) is a tool for language learning by reading.
This repository is a Docker installer, the main repository can be found at
<https://github.com/HugoFara/lwt>.

[![LWT logo](https://github.com/HugoFara/lwt/raw/master/img/lwt_icon_big.jpg)](https://github.com/HugoFara/lwt)

## What's New in 3.0.0

LWT 3.0.0 is a complete rewrite of the application:

- **Modern frontend** with Alpine.js, TypeScript, and Bulma CSS (jQuery and iframes removed)
- **Multi-user support** with registration, login, OAuth, and per-user data isolation
- **InnoDB database** with foreign key constraints and full UTF8MB4 encoding
- **REST API** at `/api/v1` for all resources
- **Extensible parsers** for Japanese (MeCab), Chinese (Jieba), and standard languages
- **New features**: term notes, inline Markdown, RSS feeds, Gutenberg book import, EPUB support, local dictionaries, dark theme

See the [full changelog](https://github.com/HugoFara/lwt/blob/main/CHANGELOG.md) for details.

## Prerequisites

This is a Docker installer, we recommend using
[Docker Desktop](https://docs.docker.com/desktop/) for inexperienced users.

For people familiar with Docker, you only need:

* [Docker](https://www.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/install/) plugin

## Installation

For copy/pasters:

```bash
git clone https://github.com/hugofara/lwt-docker-installer
cd lwt-docker-installer
cp .env.sample .env    # edit .env to set your password and preferences
docker compose up -d
```

Then visit <http://localhost:8010>.

Manual instructions:

1. Clone this repository
2. Copy `.env.sample` to `.env` and customize it (at minimum, change `DB_PASSWORD`)
3. Run `docker compose up -d`
4. Visit <http://localhost:8010>

## Multi-user mode

To enable user registration and login, set `MULTI_USER_ENABLED=true` in your `.env` file. The first registered user automatically becomes the administrator.

## Update

```bash
docker compose down
docker compose pull
docker compose up -d
```

Database migrations run automatically on startup.

## Remove

To remove the created containers:

```bash
docker compose down
```

Your data is preserved in `./lwt_db_data`. To delete everything including data:

```bash
docker compose down -v
rm -rf lwt_db_data
```

## Data storage

- **Database**: stored in `./lwt_db_data` (configurable via `DB_DATA_PATH` in `.env`)
- **Media files**: stored in `./media` (configurable via `WEB_MEDIA_PATH` in `.env`)

**Let's learn new languages!**
