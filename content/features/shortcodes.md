---
title: "Shortcodes"
weight: 20
summary: "Shortcodes bundled with the theme"
description: "Shortcodes bundled with the theme"
---

Tekst bundles a few shortcodes in `layouts/_shortcodes`.
Shortcodes can be called from any Markdown file, and their output is inserted where they are called.

## Callout

A callout draws attention to a short note.
The first argument is the title, and the content between the tags is rendered as Markdown.

```md
{{</* callout "Work in progress" */>}}
This documentation is still being written.
{{</* /callout */>}}
```

{{< callout "Work in progress" >}}
This documentation is still being written.
{{< /callout >}}

## Dropdown

A dropdown hides content behind a collapsible summary.
The first argument is the summary, and both the summary and the content are rendered as Markdown.

```md
{{</* dropdown "Show more" */>}}
Hidden content, rendered as **Markdown**.
{{</* /dropdown */>}}
```

{{< dropdown "Show more" >}}
Hidden content, rendered as **Markdown**.
{{< /dropdown >}}

## Emoji

The `emoji` shortcode inserts an SVG from the `assets/emoji` directory, referenced by file name without the extension.

```md
{{</* emoji "rocket" */>}}
```

{{< emoji "rocket" >}}

The same icons can be shown before a page title with the [`icon`]({{< relref "single-page-parameters.md#page-icon" >}}) page parameter.

## Raw HTML

Hugo escapes raw HTML in Markdown by default.
The `rawhtml` shortcode inserts its content without escaping.

```md
{{</* rawhtml */>}}
<span class="custom">Raw HTML</span>
{{</* /rawhtml */>}}
```

{{< rawhtml >}}
<span class="custom">Raw HTML</span>
{{< /rawhtml >}}

## Date and time

The `strftime` shortcode outputs the current date and time, formatted with a [Go layout string](https://pkg.go.dev/time#pkg-constants).

```md
{{</* strftime "2006-01-02" */>}}
```

{{< strftime "2006-01-02" >}}
