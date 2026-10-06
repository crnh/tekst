---
title: "Advanced Customization"
date: "2024-10-07"
summary: "Advanced customization options"
description: "Advanced customization options"
toc: false
readTime: false
autonumber: true
math: false
showTags: false
hideBackToTop: true
---

## Custom CSS

Tekst has a modular CSS architecture and uses Hugo Pipes to compile the CSS files.
All CSS files are located in the `assets/css` directory.
Simple custom CSS can be added in `assets/css/custom.css`, which is included in the final CSS bundle.
For more advanced customization, you can override the default CSS files by creating a file with the same name in the `assets/css` directory.
This should generally not be necessary, but can be useful if you for instance want to change the default fonts.

## Typography

Tekst bundles the [Inter](https://rsms.me/inter/) font in `assets/fonts`.
Other fonts can be used by putting them in the `assets/fonts` directory and overriding the `assets/css/fonts.css` file.
Fonts in the `assets/fonts` directory are automatically preloaded by the theme.

## Hooks

Hooks allow to customize layouts by injecting custom code at specific points in the layout.
Hooks are defined in the `layouts/partials/hooks` directory.
The following hooks are currently available:

- `head_start` is inserted at the beginning of the `<head>` tag.
- `head_end` is inserted at the end of the `<head>` tag.
- `body_end` is inserted at the end of the `<body>` tag.
- `footer_start` is inserted at the beginning of the footer.

To create a hook, add a file named `<hook_name>.html` in the `layouts/partials/hooks` directory. The file should contain the code you want to inject at that point in the layout.
The full context is passed to the hook, so any variables available in the page context can be used in the hook.