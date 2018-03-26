+++
# This is the frontmatter on all post when you create using:
#  hugo new post/test.md
date = 2018-03-15T15:42:07-04:00
draft = false

# Post title.
title = "Unit Testing with C"

# Project summary to display on homepage.
summary = "Using the Check unit testing framework for C"

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Does the project detail page use source code highlighting?
highlight = true

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = []
categories = ["testing"]

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

## What is Unit Testing?
Unit Testing of software applications is done during the development (coding) of an application.

The objective of Unit Testing is to isolate a section of code and verify its correctness. In procedural programming a unit may be an individual function or procedure

The goal of Unit Testing is to isolate each part of the program and show that the individual parts are correct. Unit Testing is usually performed by the developer.

## [Check framework](https://libcheck.github.io/check/)
Check is a unit testing framework for C. It features a simple interface for defining unit tests, putting little in the way of the developer. Tests are run in a separate address space, so both assertion failures and code errors that cause segmentation faults or other signals can be caught.

### How to Write a Test
Test writing using *Check* is very simple. The file in which the checks are defined must include ‘check.h’ as so:
```c
#include <check.h>

// The basic unit test looks as follows:

START_TEST (test_name)
{
 // unit test code
}
END_TEST
```

The START_TEST/END_TEST pair are macros that setup basic structures to permit testing. To run unit tests with Check, we must create some test cases, aggregate them into a suite, and run them with a suite runner.

```c
// define test suite and cases
Suite *test_suite(void) {

	Suite *s = suite_create("example-sha2");
	TCase *tc;

  tc = tcase_create("sha2");
  tcase_add_test(tc, test_sha1);
  tcase_add_test(tc, test_sha256);
  tcase_add_test(tc, test_sha512);
  suite_add_tcase(s, tc);

```
