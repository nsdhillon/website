+++
title = "Front Matter"

date = 2018-02-20
lastmod = 2018-02-20


# lhs sub-menu item of content
[menu.docs]
  parent = "content"
  weight = 10
+++

Front matter allows page-specific variables to be included at the top of a Markdown file using [TOML format](https://github.com/toml-lang/toml/blob/master/README.md), set between triple-plus `+++` lines. The variables may include metadata such as page title, date published, author, categories, tags, and so on. Here is a simple example:

```toml
+++
date = 2018-02-20
title = "My first blog post"
+++
```

Archetypes automate in the creation of Front matter.
