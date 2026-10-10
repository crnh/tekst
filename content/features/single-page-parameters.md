---
title: "Single page parameters"
weight: 80
summary: "Single page parameters"
description: "Single page parameters"
icon: "fxemoji:pagefacingup"
---

The following parameters apply to single pages, they are meant to be inserted in the `.md` files introductions, apart from the date format.

## Author

You can specify an author name to display and avatar path to use. Here is an example
using an image from /static:

```md
author: "Francesco"
authorAvatarPath: "/avatar.jpeg"
```

## Page icon

An icon can be shown before the page title.
Icons are retrieved from [Iconify](https://iconify.design/) datasets.
This is the configuration used to show the `fxemoji:pagefacingup` icon before the title of this page:

```md
icon: "fxemoji:pagefacingup"
```

Refer to the [`icon`]({{< relref "shortcodes.md#icon" >}}) shortcode for more information on how to specify icons or include other icon sets.

## Summary

A short summary can be shown under the title.

```md
summary: "A short introduction to the page"
```

## Table of contents

Show a table of contents at the beginning of the post.

```md
toc: true
```

## Sections auto-numbering

Auto-number headings.

```md
autonumber: true
```

Note that headings should start from level two.

## Tags

Create tags associated with the post and decide to show them.

```md
tags: ["database", "java"]
showTags: false
```

## Display read time

Choose to display reading time.

```md
readTime: true
```

## Hide back to top

Choose to display back to top at the end of the page.

```md
hideBackToTop: true
```

## Hide pagination controls

Choose to display pagination controls at the end of the page.

```md
hidePagination: true
```

## Meta description

You can specify the post meta description as follows:

```md
description: "Your Description"
```

## Fediverse

You can include a [fediverse handle](https://blog.joinmastodon.org/2024/07/highlighting-journalism-on-mastodon/) in your posts.

```md
fediverse: "@username@instance.url"
```

## Extra scripts

Page-specific scripts can be added with the `extraScripts` parameter.
Each entry is a path to a script in the `assets` directory, and is bundled with Hugo Pipes before being included in the page footer.

```md
extraScripts: ["js/plot.ts"]
```

## Date format

You can decide the date format to apply to single posts by setting the following param in the toml file:

```toml
[params]
singleDateFormat = "2 January 2006"
```
