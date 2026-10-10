---
title: "Setup"
date: "2024-10-12"
summary: "How to setup a Hugo's website using Tekst as a theme."
description: "Getting started with Tekst theme"
toc: true
readTime: false
autonumber: true
showTags: false
hidePagination: true
---

## Requirements

Tekst requires Hugo Extended v0.160.0 or later.

## Installation

Below are the ways to get started with the Tekst theme.

### Getting Started

First, create a new Hugo project as follows:

```bash
hugo new site <your site name> --config toml
```

### Downloading the Theme

There are different ways to install Hugo themes.
The recommended way is to install the theme as a Hugo module.
Installing Tekst as a [Hugo module](https://gohugo.io/hugo-modules/use-modules/) requires Go to be installed in your development environment.

First, initialize your Hugo project as a module:

```bash
# Initialize your project as a Hugo module
hugo mod init <module_name>
```

Then add the following to `hugo.toml`:

```toml
theme = "github.com/crnh/tekst"
```

When building the site, Hugo will automatically download the theme.

Instead of using the theme as a Hugo module, you can also install it as a Git submodule, clone it directly, or download a release and unzip it into the `/themes` directory.
These methods are not documented here.

### Updating the theme

If the theme is installed as a Hugo module, you can update it by running the following command:

```bash
hugo mod get -u github.com/crnh/tekst
```

or simply run

```bash
hugo mod get -u
```

to update all modules.

## Sample Config

Use those to get started with the theme. You can find a complete overview of the available features [here]({{< relref "/features" >}}).

### Site Config

Here is a sample `hugo.toml` config to get started with the theme.

```toml
baseURL = 'https://example.org/'
languageCode = 'en-us'
title = 'My website'
theme = 'github.com/crnh/tekst'

[taxonomies]
tag = 'tags'

[params]
# Meta description
description = "A Tech Blog"

# Appearance settings
theme = 'auto'
colorPalette = 'default'
hideHeader = false

# Lists parameters
paginationSize = 100
listSummaries = true
listDateFormat = '2 Jan 2006'

# Breadcrumbs
[params.breadcrumbs]
enabled = true
showCurrentPage = true
home = "Home"

# Social icons
[[params.social]]
name = "linkedin"
url = "https://www.linkedin.com/in/user/"

[[params.social]]
name = "medium"
url = "https://medium.com/@user"

[[params.social]]
name = "github"
url = "https://github.com/user"

# Main menu pages
[[menus.main]]
name = "home"
pageRef = "/"
weight = 10

[[menus.main]]
name = "posts"
pageRef = "/posts"
weight = 20

[[menus.main]]
name = "about"
pageRef = "/about"
weight = 30

# Syntax highlight on code blocks
[markup]
_merge = 'deep'

[markup.highlight]
noClasses = false

# Giscus comments
[params.giscus]
enable = false
repo = "user/repo"
repoid = "repoId"
category = "General"
categoryid = "categoryId"
mapping = "pathname"
theme = "preferred_color_scheme"
```

You can also check this website's [source code](https://github.com/crnh/tekst) to see an example.