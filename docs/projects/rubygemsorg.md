---
layout: default
title: Rubygems.org
parent: Projects
nav_order: 2
---

Setup the code:

```bash
git clone $REPO_URL
cd $REPO_DIR
```

Setup services (elasticsearch / postgres / memcache)

```bash
docker-compose up
```

Setup dependencies:

```bash
bundle install
./script/setup
bundle exec rake db:reset db:test:prepare --trace
bundle exec rake environment elasticsearch:import:all DIR=app/models FORCE=y
```

Get test data:

```bash
./script/load-pg-dump -d rubygems_development -h localhost -c /tmp/dump
```

Start web server:

```bash
bundle exec rails s
```