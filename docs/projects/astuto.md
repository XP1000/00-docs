---
layout: default
title: Astuto
parent: Projects
nav_order: 4
---

Setup the code:

```bash
git clone $REPO_URL
cd $REPO_DIR
cp .env-example .env
```

Setup dependencies and start web server:

```bash
script/docker-update-and-run.sh
```