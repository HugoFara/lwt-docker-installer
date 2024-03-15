# Learning with Texts

[![Latest Stable Version](https://poser.pugx.org/hugofara/lwt/v)](https://packagist.org/packages/hugofara/lwt)
[![Docker Image](https://github.com/HugoFara/lwt/actions/workflows/docker-image.yml/badge.svg)](https://github.com/HugoFara/lwt/actions/workflows/docker-image.yml)
[![Discord Server](https://badgen.net/discord/members/zAE8GXMKFa?icon=discord)](https://discord.gg/zAE8GXMKFa)

**Learning with Texts** (LWT) is a tool for language learning by reading.
This repository is a Docker installer, the main repository can be found at
<https://github.com/HugoFara/lwt>.

[![LWT logo](https://github.com/HugoFara/lwt/raw/master/img/lwt_icon_big.jpg)](https://github.com/HugoFara/lwt)

## Prerequisites

This is a Docker installer, we recommend using
[Docker Desktop](https://docs.docker.com/desktop/) for unexperienced user.

For people familiar with Docker, you only need:

* [Docker](https://www.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/install/) plugin

## Installation

For copy/pasters:

```bash
git clone https://github.com/hugofara/lwt-docker-installer # download this repository
cd lwt-docker-installer
cp .env.sample .env                                        # don't hesitate to edit .env!
docker compose up -d
```

Manual instructions:

1. Copy the repository [hugofara/lwt-docker-installer](https://github.com/hugofara/lwt-docker-installer)
2. Create the ``.env`` file and customize it to your convenience
3. Run ``docker compose up -d``

By default the server can be accessed on port 8010 (<http://localhost:8010/lwt>). 
If you are using LWT 2.9.1 or older, you may access it on <http://localhost:8010> instead,
as LWT was moved from the main folder to `lwt/`.

## Update

As for any Docker container, do to the Docker folder and run:

```bash
docker compose down
docker composer pull
docker compose up -d
```

## Remove

To remove the created containers go the the created folder and run:

```bash
docker compose down
```

## Data storage

All user data will be stored in local folder `./lwt_db_data`.

**Let's learn new languages!**
