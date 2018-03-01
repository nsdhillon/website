+++
# This is the frontmatter on all post when you create using:
#  hugo new post/test.md
date = 2018-02-28T23:39:13-05:00
draft = false

# Post title.
title = "Serialization of Configuration Files"

# Project summary to display on homepage.
summary = "Choosing the Serialization format for configuration files."

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Does the project detail page use source code highlighting?
highlight = true

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = []
categories = []

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = ""
caption = ""
preview = true

+++

Configuration (config) files are used to configure the parameters and initial settings for applications. A user of configuration files needs the ability to view or edit the config files by hand. The Serialization format of these configuration files is therefore very important and needs to be simple and quick. Here you would typically want to use one of the already established formats. There are quite a few of them and all have their pros and cons. So how do you pick the right one? I use the KISS principle to choose and thus will use TOML going forward where YAML was a close second.

## Serialization formats

* [INI](https://en.wikipedia.org/wiki/INI_file) - a common configuration file format composed of sections, properties, and values.
* [JSON](https://en.wikipedia.org/wiki/JSON) - a subset of javascript with support for complex data types and data structures
* [TOML](https://en.wikipedia.org/wiki/TOML) - TOML aims to be a minimal configuration file format that's easy to read due to obvious semantics. TOML is designed to map unambiguously to a hash table.
* [YAML](https://en.wikipedia.org/wiki/YAML) - a superset of json with support for complex data types and structures

## Configuration parser libraries

### Ini parsers
* [libconfini](https://github.com/madmurphy/libconfini) - using the reactor callback pattern to parse ini Files
* [qlibc](http://wolkykim.github.io/qlibc/) - great library (see [qconfig.c](http://wolkykim.github.io/qlibc/doc/html/qconfig_8c.html)) that also parses apache style configuration files

### JSON parsers
* [libU](https://github.com/koanlogic/libu) - multi-platform utility library written in C - rather dead
* [jansson](https://github.com/akheron/jansson) - C library for encoding, decoding and manipulating JSON data
* [parson](https://github.com/kgabis/parson) - Lightweight JSON library written in C.

### TOML parsers
* [libtoml](https://github.com/ajwans/libtoml) - Fast C parser using Ragel to generate the state machine.
* [cpptoml](https://github.com/skystrife/cpptoml) - A header-only C++ library for parsing TOML configuration files.
* [tinytoml](https://github.com/mayah/tinytoml) - A header only C++11 library for parsing TOML configuration files.
* [tomlc99](https://github.com/cktan/tomlc99) - Fast c parser in C99.

### YAML parsers
* [libyaml](https://github.com/yaml/libyaml) - the industry standard in decoding YAML configuration files.
* [yaml-cpp](https://github.com/jbeder/yaml-cpp) - parser and emitter in C++ matching the YAML 1.2 spec.
