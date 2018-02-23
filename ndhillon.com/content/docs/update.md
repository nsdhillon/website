+++
title = "Update"

date = 2018-02-20
lastmod = 2018-02-20
draft = false

[menu.docs]
    parent = "setup"
    weight = 50
+++

## If you installed by Git cloning `hugo-nsd`

Before updating for the first time, the remote *origin* repository should be renamed to *upstream*:

    $ cd themes/hugo-nsd
    $ git remote rename origin upstream

To list available updates:

    $ cd themes/hugo-sd
    $ git fetch upstream
    $ git log --pretty=oneline --abbrev-commit --decorate HEAD..upstream/master

Then, update by running:

    $ git pull upstream

## Troubleshooting

Check out the [release notes](../../updates) for the version that you are updating to, paying attention to the breaking changes.
