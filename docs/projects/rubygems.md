---
layout: default
title: Rubygems
parent: Projects
nav_order: 1
---

Setup the code:

```bash
git clone $REPO_URL
cd $REPO_DIR
git submodule update --init
```

Change your system version with the one from the repo:

```bash
gem --version # know your current version
ruby setup.rb
gem --version # ensure you are using the latest version from the code
```