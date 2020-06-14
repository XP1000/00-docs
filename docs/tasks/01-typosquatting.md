---
layout: default
title: 01-typosquatting
parent: Tasks
nav_order: 1
---

Git repo: [https://github.com/XP1000/01-typosquatting](https://github.com/XP1000/01-typosquatting)

See [Rubygems]({% link docs/projects/rubygems.md %}) for setup

For security reason we need to prevent typosquatting (on rubygems.org) when adding a new source for gems. The way this will be handled is similar to what is already done when using non https url:

```bash
gem source -a "http://rubygems.org"

https://rubygems.org is recommended for security over http://rubygems.org

Do you want to add this insecure source? [yn]  

```

{% details Hint 1 %}
  Read the definition of typosquatting: [https://en.wikipedia.org/wiki/Typosquatting](https://en.wikipedia.org/wiki/Typosquatting)
{% enddetails %}

{% details Hint 2 %}
  Learn about the Levenshtein distance: [https://en.wikipedia.org/wiki/Levenshtein_distance](https://en.wikipedia.org/wiki/Levenshtein_distance)
{% enddetails %}

{% details Hint 3 %}
  Search for the current implementation of the https check with

  ```bash
ack --ruby "check.*https"
  ```

  ```ruby
def check_rubygems_https(source) # :nodoc:
  uri = source.uri

  if uri.scheme and uri.scheme.downcase == 'http' and
     uri.host.downcase == 'rubygems.org'
    question = <<-QUESTION.chomp
https://rubygems.org is recommended for security over #{uri}

Do you want to add this insecure source?
    QUESTION

    terminate_interaction 1 unless ask_yes_no question
    end
end
  ```
{% enddetails %}

{% details Hint 4 %}
  Check for an already existing leveinshtein implementation

  ```bash
ack --ruby "levenshtein"
  ```
{% enddetails %}

{% details Hint 5 %}
  Add a new test in `test/rubygems/test_gem_commands_sources_command.rb`
{% enddetails %}
