---
title: devStack CLI
publishDate: 2026-03-16 00:00:00
img: /assets/devstack.png
img_alt: Terminal screen showing Docker services being spun up
description: |
  A CLI tool that eliminates Docker Compose boilerplate — spin up databases and local dev services in seconds with a single config file your whole team can share.
tags:
  - CLI
  - DevOps
  - Open Source
---

Every new project starts the same way. You need a database. Maybe a cache. Maybe a message broker. So before writing a single line of application code, you're already an hour deep — writing Docker Compose files from scratch, looking up the right environment variable names, figuring out which port conflicts with something else running on your machine, and copy pasting connection strings into `.env`. devStack was built to make that entire setup loop disappear.

## What It Is

devStack is an open source CLI tool that sits on top of Docker Compose and gives developers a single, consistent interface for spinning up, managing, and tearing down local development infrastructure. You describe your stack once in a `devstack.config.json` file, commit it to version control alongside your code, and from that point forward anyone on the team gets the exact same environment with one command.

It ships with first class support for the services developers reach for most: PostgreSQL, MySQL, MongoDB, Redis, RabbitMQ, Elasticsearch, MinIO for local object storage, and Mailpit for catching and inspecting email flows in development. Every service comes with sensible defaults — you don't need to know the right environment variable names, the correct volume mount paths, or the recommended memory flags. devStack knows them, and you only override what you actually need to change.

## Beyond Just Running Containers

Spinning up services is the baseline. devStack goes further with a set of commands designed around how developers actually work. A live info dashboard shows every service in your stack, whether it's running, and the exact connection string to paste into your app. An `env` command generates a ready-to-use `.env` file for every configured service. An `open` command launches the web UI for services that have one — RabbitMQ's management console, MinIO's dashboard, Mailpit's inbox — directly in your browser. And when you need a clean slate, a single `nuke` command tears everything down and resets your config.

## The Philosophy

The guiding principle behind devStack is convention over configuration. A developer starting a new project shouldn't have to be a Docker expert to get a reliable local environment running. The tool handles the infrastructure knowledge so you can stay focused on the application. And because the entire stack lives in a committed config file, "works on my machine" stops being a problem — every teammate starts from the same baseline.

devStack is published to npm as `@palr-dev/devstack-cli` with full documentation at [palr-dev.github.io/devStack](https://PALR-DEV.github.io/devStack/).
