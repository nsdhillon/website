+++
title = "Getting started"

date = 2018-02-20
lastmod = 2018-02-20
draft = false

math = true

aliases = ["post/getting-started/"]

[menu.docs]
    parent = "setup"
    weight = 20
+++

This quick tutorial will show you how to setup and use Hugo-nsd.

## Core parameters

The core parameters for the website can be edited in the `config.toml` configuration file:

- Set `baseurl` to your website URL (we recommend [GitHub Pages](https://ndhillon.com/create-your-website-with-hugo/) for free hosting)
- Set `title` to your desired website title such as your name
- The example Disqus commenting variable should be cleared (e.g. `disqusShortname = ""`) or set to your own [Disqus](https://disqus.com/) shortname to enable commenting
- Edit your details under `[params]`; these will be displayed mainly in the homepage *about* and *contact* widgets (if used). To disable a contact field, simply clear the value to `""`. 
- Place a square cropped portrait photo named `portrait.jpg` into the `static/img/` folder, overwriting any defaults. Note that you can edit the `avatar` filepath to point to a different image name or clear the value to disable the avatar feature. Alternatively, set `gravatar` to `true` to use the Gravatar/Wordpress avatar associated with your `email` address.
- To enable LaTeX math for your site, set `math = true`
- Social/Hugo-nsd networking links are defined as multiples of `[[params.social]]`. They can be created or deleted as necessary.

## Customize the homepage

Refer to our guide on using [widgets]({{< ref "widgets.md" >}}) to customize your homepage.

## Add your content

Refer to our guide on [managing content]({{< ref "docs/managing-content.md" >}}) to create your own publications, blog posts, talks, and projects.

## Remove unused widgets and pages

[How to remove unused widgets and content pages]({{< ref "docs/managing-content.md#removing-content" >}}).

## Themes

A different theme can be set using  the `color_theme` option in `config.toml`.

The following font styles are available and can be set by the `font` option in `config.toml`:

- default (modern)
- playfair (serif)

To **customize the color theme**, you can copy a theme such as `themes/Hugo-nsd/data/themes/default.toml` to `data/themes/default.toml` (at the root of your site, **not** in `themes/Hugo-nsd/`), creating the `data/themes/` folders if they do not already exist. Now you can adjust the colors within your theme file. Consider renaming and *sharing* your new color theme with the [community](http://discuss.gohugo.io/).

To **customize the font theme**, you can copy a theme such as `themes/Hugo-nsd/data/fonts/default.toml` to `data/fonts/default.toml` (at the root of your site, **not** in `themes/Hugo-nsd/`), creating the `data/fonts/` folders if they do not already exist. Now you can adjust the font size and family. Consider renaming and *sharing* your new font theme with the [community](http://discuss.gohugo.io/).

## View your site

If you installed on your computer with **Git** or **ZIP**, view your new website by running the `hugo server -v` command.

Now visit [localhost:1313](http://localhost:1313) and your new Hugo-nsd powered website will appear. Otherwise, if using **Netlify**, they will provide you with your URL.
