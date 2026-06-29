---
title: catchUp CLI
publishDate: 2026-06-26 00:00:00
img: /assets/catchup.png
img_alt: Terminal screen showing a git summary output
description: |
  An AI-powered CLI tool that summarizes everything that changed in your codebase while you were away no more scrolling through hundreds of commits.
tags:
  - CLI
  - AI
  - Open Source
---

Every developer knows the feeling: you come back from a few days off, open the repo, and face a wall of commits. You start scrolling reading messages, opening diffs, trying to piece together what changed, what broke, what shipped. It's context loading before you can do any real work. catchUp was built to eliminate that entirely.

## What It Is

catchUp is an open source CLI tool that reads your git history and uses AI to produce a clean, human-readable summary of everything that changed in your codebase over a given window of time. Instead of spelunking through hundreds of commits, you run one command and get back a clear narrative of what happened which features landed, what was refactored, what got fixed, and what's still in progress.

The time range is flexible: an hour, a day, a week, two weeks   whatever matches how long you were away. You can read the summary right in your terminal, open it in a browser for a richer view, or save it as a Markdown file to share with your team.

## Why It Works

The key design decision was keeping the tool AI-provider agnostic. Developers already have API keys and preferences   some use Claude, some use OpenAI, some run local models with Ollama. catchUp supports all three out of the box and lets you swap providers at any time through a simple config command. The setup is a single `catchup init` that walks you through your choice, and from there every run is one command.

This also made the tool genuinely useful in team settings. A tech lead can run `catchup since 3d` before a standup and get a fast, accurate picture of what the team shipped without reading every PR individually.

## Impact

catchUp is published to npm as `@palr-dev/catchup` and available for any team using git, with full source available at [github.com/PALR-DEV/catchUp](https://github.com/PALR-DEV/catchUp).
