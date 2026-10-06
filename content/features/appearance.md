---
title: "Appearance"
date: "2024-10-12"
summary: "Appearance parameters"
description: "Appearance parameters"
toc: false
readTime: false
autonumber: true
math: false
showTags: false
---

Tekst supports a dark and light mode.
By default, both are enabled and the mode is automatically chosen based on the user's system preferences.
A theme toggle in the header allows the user to switch between modes.

## Choosing a theme

By default the mode in use is `auto`, but the color scheme can be forced to either `light` or `dark`:

```toml
[params]
theme = 'auto | light | dark'
```

## Choosing a color palette

Tekst contains a set of color palettes that can be used to change the appearance of the theme.
By default, the color palette is black and white.
The color palette can be changed with the `colorPalette` parameter:

```toml
[params]
colorPalette = 'default'
```

These palettes are currently available:

- default
- catpuccin
- gruvebox
- eink
- base16-default
- base16-eighties
- base16-ocean
- base16-mocha
- base16-cupcake

## Adding a custom color palette

Palettes are defined using YAML files in `data/themes`.
New palettes can be added by creating a new file in that directory, and defining the required parameters.

## Hide the website title or header

The website title can be hidden by setting the `hideTitle` parameter to `true`:

```toml
[params]
hideTitle = true
```

Furthermore, the header can be hidden on all non-home pages by setting the `hideHeader` parameter to `true`:

```toml
[params]
hideHeader = true
```

It is recommended to enable breadcrumbs if you do so.

## Code Blocks

**Syntax Highlighting**

The theme supports syntax highlighting.
By default, it uses a slightly modified version of the `bw` theme, defined in `assets/css/syntax-highlighting.css`.
To enable syntax highlighting, add the following to your `hugo.toml`:

```toml
[markup]
[markup.highlight]
noClasses = false
```

The code block background can be changed with the `--code-background-light` and `--code-background-dark` variables in [`custom.css`]({{% relref "advanced-customization.md#custom-css" %}}) or in a [custom color file](#adding-a-custom-color-palette).
Other color schemes, e.g. Monokai, can be applied using [inline styles]: 

```toml
[markup]
[markup.highlight]
noClasses = true
style = 'monokai'
```

Alternatively, you can overwrite the stylesheet with your preferred color scheme using this command:

```shell
hugo gen chromastyles --style monokai > assets/css/syntax-highlighting.css
```

I suggest trying [color schemes](https://xyproto.github.io/splash/docs/all.html) and see what can work for you.

**Line Numbers**

If you want to enable line numbers, use the following, `lineNumbersInTable` is especially important. 

```toml
[markup]
[markup.highlight]
lineNos = true
lineNumbersInTable = false
```

## Footer Customization

The footer can be hidden by changing the `showFooter` parameter to `false`.
The footer content can be specified through the `footerContent` parameter, which supports Markdown.
If the footer is not hidden and the content is not specified, the default footer is shown.

```toml
[params]
showFooter = true
footerContent = "Your **custom** md `footer`"
```

[inline styles]: https://neohugo.github.io/content-management/syntax-highlighting/#noclasses