+++

# this an example markdown - used to show what builtin there are - Narinder

# Date this page was created.
date = "2018-02-01"

# Resume title.
title = "Testing Markdown"

# Project summary to display on homepage.
summary = "A simple howto frame your markdown as based upon the Hugo BlackFriday markdown engine."

# Optional image to display on homepage (relative to `static/img/` folder).
image_preview = ""

# Tags: can be used for filtering projects.
tags = ["markdown", "tests"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Optional featured image (relative to `static/img/` folder).
[header]
image = ""
caption = "this is a caption for the optional featured image"

+++

# testing markdown

### tables
Tables can be created by drawing them in the input using the below syntax: Example:

   Name | Age
--------|------
    Bob | 27
  Alice | 23


### example fenced code
To insert code: you can use 3 or more backticks to mark the beginning of the block, and the same number to mark the end of the block. Output looks like:

```md
# Heading Level 1
Some test
## Heading Level 2
Some more test
```

### strikethrough
hen enabled, text wrapped with two tildes will be crossed out.  
Example: ~~crossed-out~~

### link text highlight
[`Narinder`: Test website](https://localhost:1313)

### code highlight shortcode
See config.toml for default syntax highlighter that is being used.  
Using emacs as the style sheet but here code highlighted is python.

{{< highlight python "linenos=inline,hl_lines=5 10-12,linenostart=6" >}}

#!/usr/bin/python3

from engine import RunForrestRun

"""Test code for syntax highlighting!"""

class Foo:

	def __init__(self, var):
	self.var = var
	self.run()

	def run(self):
	RunForrestRun()  # run along!

{{< / highlight >}}

### another markdown example highlighting 'C'

```c
/**
 * Dynamic shared object example.
 *
 * The function interfaces that are required for a dynamically registered shared
 * object have the ability to have transport connectivity from the IXMDD layer.
 *
 * This example consumes CME messages from the IXMDD service. Here we are mixing
 * both C and C++ to show flexibiliy in the callback interface.
 */


#include <iostream>
#include <fstream>
#include <string>
#include <cstring>
#include <sstream> // ostringstream
#include <iomanip> /* setw */

extern "C" {
#include <unistd.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>
#include <sys/time.h>

#include <ixmdd.h>
#include <cme_messages.h>
}

#define timeval_to_float(tv_p) \
    ((double)(tv_p)->tv_sec + ((double)(tv_p)->tv_usec) / 1000000L)

#define	timeval_sub(xtv, ytv, ztv) do { 	      \
    (ztv)->tv_sec = (xtv)->tv_sec - (ytv)->tv_sec;    \
    (ztv)->tv_usec = (xtv)->tv_usec - (ytv)->tv_usec; \
    if ((ztv)->tv_usec < 0) {			      \
      (ztv)->tv_sec--;				      \
      (ztv)->tv_usec += 1000000L;		      \
    }						      \
  } while (0)


std::string out_fs = ": ";
std::string out_us = "\n";
int padding = 20;

void cme_dump_packet_type (int packet_type) {

```



### footnotes
Pandoc-style footnotes will be supported. The footnote marker in the text that will become a superscript text; the footnote definition will be placed in a list of footnotes at the end of the document.

Example:
This is a footnote.[^1]

[^1]: the footnote text.



### including an image
Pencil sketch of `Narinder` - here the image link text not displayed
![Pencil sketch Narinder](/img/posts/tests/nsd.png.jpg)

### inserting an alert at note level
{{% alert note %}}
This is an alert note that sends you [home](https://www.ndhillon.com).
{{% /alert %}}

### inserting an alert at warning level
{{% alert warning %}}
This is an alert warning that sends you [home](https://www.ndhillon.com).
{{% /alert %}}

### some bullets
These are bullets.

1. hello 1
2. world 2
3. goodbye
   * hello again

### Adding links to pdf file
{{%/* staticref "files/cv.pdf" */%}}Download my CV{{%/* /staticref */%}}


### Adding images to a post

If you want to include an image the recommended method is to:

1. Add the image to your `/static/img/` folder, then
2. Reference the image using the relative file path as follows:

```
![my-image](/img/my-image.png)
```

### Changing look & feel - Custom CSS
The default theme settings like colors and fonts can be controlled via the `config.toml` file entry:

```
  # Link custom CSS and JS assets
  #   (relative to /static/css and /static/js respectively)
  custom_css = ["blue.css"]
```

### Forms -  Formspree

By default using [Formspree](https://formspree.io) to make a contact form, which is an online service (managed on [GitHub](https://github.com/formspree/formspree)) that allows you to add an HTML form to your static site. No registration, just use the form and confirm your email address once. Add the following code into [my contact widget](https://github.com/nsdhillon/hugo-nsd/layouts/partials/widgets/contact.html):

```
<form action="https://formspree.io/your@email.com" method="POST">
  <label for="name">Your name: </label>
  <input type="text" name="name" required="required" placeholder="here"><br>
  <label for="email">Your email: </label>
  <input type="email" name="_replyto" required="required" placeholder="here"><br>
  <label for="message">Your message:</label><br>
  <textarea rows="4" name="message" id="message" required="required" class="form-control" placeholder="I can't wait to read this!"></textarea>
  <input type="hidden" name="_next" value="/html/thanks.html" />
  <input type="submit" value="Send" name="submit" class="btn btn-primary btn-outline">
  <input type="hidden" name="_subject" value="Website message" />
  <input type="text" name="_gotcha" style="display:none" />
</form>
```


<!-- commented out using HTML comment
### You can insert gif's

<iframe src="https://media.giphy.com/media/Y5GeL3y4uAYjS/giphy.gif" width="480" height="400" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://media.giphy.com/media/Y5GeL3y4uAYjS/giphy.gif">via GIPHY</a></p>

-->
