---
layout: default
title: 02-dependency-update
parent: Tasks
nav_order: 1
---

Git repo: [https://github.com/XP1000/02-dependency-update](https://github.com/XP1000/02-dependency-update)

See [BitMidi]({% link docs/projects/bitmidi.md %}) for setup

We have received the following report to update the uuid dependency: [https://github.com/XP1000/02-dependency-update/pull/8](https://github.com/XP1000/02-dependency-update/pull/8)

Check if it is safe to merge

{% details Hint 1 %}
  Read the changelog of the uuid package: [https://github.com/uuidjs/uuid/blob/master/CHANGELOG.md](https://github.com/uuidjs/uuid/blob/master/CHANGELOG.md)
{% enddetails %}

{% details Hint 2 %}
  Rewrite the uuid import to comply with the new default export
{% enddetails %}

{% details Hint 3 %}
  Notice that the code using uuids isn't used anymore and carrefully remove the uuid dependency
{% enddetails %}