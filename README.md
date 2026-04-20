# DevOps Exercise 1 — Containerize & CI

## Overview

This project containerizes a simple web app and sets up a CI pipeline to lint, test, and build the Docker image.

---

## Prerequisites

* Docker
* Docker Compose

---

## Setup

```bash
git clone <repo-url>
cd <repo-name>
cp .env.example .env
```

---

## Run App

```bash
make build
make run
```

App: http://localhost:8080
Health: http://localhost:8080/healthz

---

## Commands

```bash
make test    # run tests
make lint    # run linter
make clean   # stop & remove containers/images
```

---

## CI

GitHub Actions runs on push & PR:

* Lint
* Test
* Docker build

---

## Files

* Dockerfile
* docker-compose.yml
* Makefile
* ci.yml
* design_notes.md

---

## Submission

```
Submissions/DevOps/Exercise-1/Level/<YourName>/
```
