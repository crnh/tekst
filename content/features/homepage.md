---
title: "Homepage"
date: "2024-10-14"
summary: "Homepage parameters"
description: "Homepage parameters"
toc: false
readTime: false
autonumber: true
math: false
showTags: false
---

The homepage is located in `content/_index.md` and can be customized using this file's frontmatter parameters.

## Intro section

The page content in `content/_index.md` is displayed as a text section after the header on the homepage.
The title of the intro is set through the `title` frontmatter parameter.

## Social icons

You can include social icons after the intro:

```yaml
social:
  - name: linkedin
    url: https://linkedin.com/in/your-profile
  - name: github
    url: https://github.com/your-profile
  - name: mail
    url: mailto:you@example.com
```

## Display a collection

A content collection can be displayed below the social icons.
This is also configured through the frontmatter parameters:

```yaml
collection:
  name: posts
  title: Posts
  entry: post  # Optional list item type, defaults to "post"
```

The above example includes the `/posts` collection. Note that you can omit the title if you prefer.
The `entry` parameter is optional and allows you to specify an entry partial template to use for the list items. 
These partials are located in `layouts/_partials/entries` and can be added or customized to your liking.

## Example home page

```markdown
---
title: 'Hi!'

social:
  - name: linkedin
    url: https://linkedin.com/in/your-profile
  - name: github
    url: https://github.com/your-profile

collection:
  name: features
  title: Features
---

Tekst is a minimal, text-centered theme for Hugo.
```