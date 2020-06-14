---
layout: default
title: BitMidi
parent: Projects
nav_order: 3
---

Setup the code:

```bash
git clone $REPO_URL
cd $REPO_DIR
cp secret/index-sample.js secret/index.js
```

Edit `secret/index.js`

```diff
  export const db = {
    client: 'mysql',
    version: '5.7',
    connection: {
      host: isProd ? 'TODO' : 'localhost',
      port: 3306,
-      user: 'TODO',
+      user: 'bitmidi',
-      password: 'TODO',
+      password: 'bitmidi',
-      database: 'TODO'
+      database: 'bitmidi'
    },
    migrations: {
      directory: '../migrations'
    }
  }
```

Setup dependencies:

```bash
npm install
npm run build
```

Setup mysql

```bash
docker run --name bitmidi-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -e MYSQL_DATABASE=bitmidi -e MYSQL_USER=bitmidi -e MYSQL_PASSWORD=bitmidi -p 3306:3306 bitnami/mysql:5.7
```

Get test data:

```bash
npm run knex -- migrate:latest
curl http://www.jsbach.net/midi/sankey/802-805.zip --output /tmp/sample.zip
unzip /tmp/sample.zip -d /tmp/midi-samples
node -r @babel/register tools/import.js /tmp/midi-samples
```

Start web server:

```bash
npm start
```
