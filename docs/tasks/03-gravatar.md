---
layout: default
title: 03-gravatar
parent: Tasks
nav_order: 1
---

Git repo: [https://github.com/XP1000/03-gravatar](https://github.com/XP1000/03-gravatar)

See [Astuto]({% link docs/projects/astuto.md %}) for setup

We want to be able to see the gravatar of the comment authors in the posts comments:

![astuto-gravatar](/imgs/astuto-gravatar.png)

{% details Hint 1 %}
  Check the react-gravatar package: [https://www.npmjs.com/package/react-gravatar](https://www.npmjs.com/package/react-gravatar)
{% enddetails %}

{% details Hint 2 %}
  Return the author email from the SQL query: `app/controllers/comments_controller.rb:8`
  And render it in the json: `app/controllers/comments_controller.rb:25`
{% enddetails %}

{% details Hint 3 %}
  Edit the `Comment` component to take the author email into consideration and display the `Gravtar` component inside it
{% enddetails %}

{% details Hint 4 %}
  Add some CSS rules for a nice integration in `app/javascript/stylesheets/components/Comments.scss`
{% enddetails %}