---
title: "Header"
date: "2024-10-13"
summary: "Header menu"
description: "Header menu"
---

The header contains the site's main menu.
This menu is configured through Hugo's [menu system](https://gohugo.io/configuration/menus/).

To include pages in the header menu, you must add the following elements to your `hugo.toml` file:

```toml
[[menus.main]]
name = "home"  # Name of the menu item
pageRef = "/"  # Reference to the page to link to
weight = 10    # Optional weight to control the order of menu items
```
