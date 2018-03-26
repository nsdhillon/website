+++

# This is the frontmatter on all post when you create using:

# hugo new post/test.md

date = 2018-03-20T22:17:15-04:00
draft = false

# Post title.

title = "Coding Style"

# Project summary to display on homepage.

summary = "Using clang-format"

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

# Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.

# Set `preview` to `false` to disable the thumbnail in listings.

[header]
image = ""
caption = ""
preview = true

+++

Many projects have a "programming style guide" that defines the layout, look and feel of code within the project. These style guides are often ignored as developers do not pay enough attention to the details that are described within or they do have enough time due to project deadlines to fully absorb the required layouts.

So this style process is better automated allowing programmers to focus only on the code. To achieve this we can use [clang-format](https://clang.llvm.org/docs/ClangFormat.html) tool that uses a list of style rules to run on build servers to ensure compliance automatically.

ClangFormat is an LLVM tool for formatting code that utilizes the clang tokenizer to parse C, C++, Objective C, Java, and JavaScript files. When properly integrated into a toolchain, ClangFormat can entirely do away with time wasted on discussion and enforcement of code formatting.

## Getting started

### Configuration

Using the following command you can create .clang-format file that acts as a starting baseline configuration file.

    clang-format --style=llvm -dump-config > .clang-format

The .clang_format file is where custom style definition are kept. When running clang-format command we will specify -style=file so that clang-format knows these custom rules.

## Running clang-format

Running clang-format is relatively simple. Let's discuss some important options before we get into the details.

### STYLE

The style argument is used to determine the style rules that clang-format will apply. You can use any of the styles described below, or -style=file to tell clang-format that it must use your .clang-format file.

```console
clang-format -i -style=Mozilla *.cpp
```
The available style's are:

* LLVM - A style complying with the [LLVM coding standards](http://llvm.org/docs/CodingStandards.html)
* Google - A style complying with [Google’s C++ style guide](http://google-styleguide.googlecode.com/svn/trunk/cppguide.xml)
* Chromium - A style complying with [Chromium’s style guide](http://www.chromium.org/developers/coding-style)
* Mozilla - A style complying with [Mozilla’s style guide](https://developer.mozilla.org/en-US/docs/Developer_Guide/Coding_Style)
* WebKit - A style complying with [WebKit’s style guide](http://www.webkit.org/coding/coding-style.html)


### IN-PLACE EDITING

By default, clang-format will display formatting discrepancies as shell output. I prefer to have clang-format update the files directly. This behavior is enabled using the -i option.

### FALLBACK STYLE

When getting started with clang-format, it's easy to get into situations where clang-format cannot find your style file. In this situation, it will fallback to the LLVM style. You can determine the exact style to use as a fallback using the "-fallback-style" switch.

```console
-fallback-style=none
```

Setting to none will cause clang-format to fail if your file can't be located:

#### RE-FORMATTING FILES

The following command will fill and find all C and C++ files in the current directory tree:

```console
find . -iname *.h -o -iname *.c -o -iname *.cpp -o -iname *.hpp \
    | xargs clang-format -style=file -i -fallback-style=none
```

Note the arguments used with **clang-format**

-   applied in-place editing
-   indicated that the style rules are in the .clang-format file
-   clang-format will fail if the style file is not found
