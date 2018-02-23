+++
title = "Customization"

date = 2018-02-20
lastmod = 2018-02-20
draft = false

math = true

aliases = ["post/getting-started/"]


# the following creates a sub-menu link toc
[menu.docs]
    parent = "setup"
    weight = 30
+++

It is possible to carry out many customizations *without* editing any code in the `themes/hugo-nsd/` folder, making it easier to update the framework in the future.

## Menu

The `[[menu.main]]` entries towards the bottom of `config.toml` define the navigation links at the top of the website. They can be added or removed as desired.

To create a dropdown sub-menu, add `identifier = "something"` to the parent item and `parent = "something"` to the child item.

## Website icon

Save your main icon and mobile icon as square PNG images named `icon.png` (32x32 pixels) and `icon-192.png` (192x192 pixels), respectively. Place them in your root `static/img/` folder.

## Analytics

To enable [Google Analytics](http://www.google.com/analytics), add your tracking code in `config.toml` similarly to `googleAnalytics = "UA-12345678-9"`.

## Add scripts (JS)

To add a **third party script**, create a file named `head_custom.html` in a `layouts/partials/` folder at the root of your website (not in the `themes` folder). Any HTML code added to this file will be included within your website's `<head>`. Therefore, it's suitable for adding custom metadata or third party scripts specified with the *async* attribute.

Whereas for your own **local scripts**, you can link your local JS assets (relative to your root `static/js`) from your `config.toml` using `custom_js  = ["custom.js"]`.

## Permalinks

*Permalinks*, or *permanent links*, are URLs to individual pages and posts on your website. They are permanent web addresses which can be used to link to your content. Using Hugo's *permalinks* option these can be easily customized. For example, the blog post URL can be changed to the form *yourURL/2018/02/20/my-post-slug* by adding the following near the top of your `config.toml` (before `[params]` settings):

    [permalinks]
        post = "/:year/:month/:day/:slug"

Where `:slug` defaults to the filename of the post, excluding the file extension. However, slug may be overridden on a per post basis if desired, simply by setting `slug = "my-short-post-title"` in your post preamble.

**Example 2:** let's consider changing the URL path of posts from `post/` to `blog/`. First, add the following parameters right above the `[params]` section of your `config.toml`:
```
[permalinks]
    post = "/blog/:slug"
```
Then add `aliases = ["/blog/"]` to your post archive page `post/_index.md` so that it can be accessed from the */blog/* URL.

## Customize style (CSS)

For advanced customization of the style, you can link custom CSS assets (relative to your root `static/css`) from your `config.toml` using `custom_css = ["custom.css"]`.

For example, let's override some of Hugo-nsd's default styles. First, define `custom_css = ["override.css"]` in `config.toml`. Then we can create the file `static/css/override.css`, relative to your website root (i.e. **not** in the `themes` directory). Add your custom CSS to this file.

## Override a template

Hugo uses a [template lookup](https://gohugo.io/templates/lookup-order/) which enables you to override any of Hugo-nsd's files without directly changing them. This can make it easier to update Hugo-nsd in the future since you do not modify any of Hugo-nsd's files directly.

To override a template in the theme, you simply copy the file you are interested in from `themes/Hugo-nsd/` and paste it in your site folder using a similar path. To understand how this works, you should familiarize yourself with template lookup. Finally, when you update Hugo-nsd, remember to compare your version of the file against Hugo-nsd's one, in case you need to propagate any changes across.

For example, say we wish to add some HTML code to the navigation bar. Let's copy the relevant file `themes/Hugo-nsd/layout/partials/navbar.html` to `layout/partials/navbar.html` (at the root of your site, **not** in `themes/Hugo-nsd/`), creating the `layout/partials/` folders if they do not already exist. Now you can add the HTML code you want to your copy of the file, which will override Hugo-nsd's version.
