+++
# This is the default frontmatter on all pages when you create using:
#  hugo new test.md

title = "{{ replace .TranslationBaseName "-" " " | title }}"
date = {{ .Date }}
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = []
categories = []

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = ""
caption = ""

+++
