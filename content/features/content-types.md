---
title: "Content types"
weight: 10
summary: "How sections, list pages and entries are rendered"
description: "How sections, list pages and entries are rendered"
---

A content type is defined by a section, i.e. a folder under `content/` with an `_index.md` file.
Each section is rendered on two kinds of pages: a **list page** that lists its pages, and **single pages** that render one page each.

## How a section is rendered

List pages share a common wrapper, `layouts/_partials/list-base.html`, which renders the breadcrumbs, the intro, the entries and the pagination controls.
The wrapper leaves the actual entries to the section's list template through a [partial decorator](https://gohugo.io/templates/partial-decorators/), so each section decides how its items look.

An entry template is a partial in `layouts/_partials/entries`.
The theme provides `post.html`, `publication.html` and `tag.html`, and you can add your own.

Single pages are rendered by `layouts/_default/single.html`, unless the section provides its own `single.html`.

## Posts

Posts are the default content type.
A section without a dedicated layout uses `layouts/_default/list.html` and `layouts/_default/single.html`, and renders its items with [`entries/post.html`](https://github.com/crnh/tekst/blob/main/layouts/_partials/entries/post.html).

## Publications

The `publications` section provides a layout tailored to academic output.
It is rendered by `layouts/publications/list.html` and `layouts/publications/single.html`, using `entries/publication.html`.

On top of the [single page parameters]({{< relref "single-page-parameters.md" >}}), publication pages support the following frontmatter parameters:

```yaml
authors:
  - Jane Doe
  - John Smith
```

The author list is shown under the title.
The publication date format can be changed with the `publicationDateFormat` site parameter:

```toml
[params]
publicationDateFormat = 'Jan 2006'
```

Publications also show badges for external resources.
These are configured through frontmatter parameters, and each is rendered as a link:

```yaml
pdf: https://example.org/paper.pdf
doi: 10.1000/xyz123
code: https://github.com/user/repo
github: user/repo
badges:
  - title: Dataset
    href: https://example.org/dataset
```

- `pdf` adds a **PDF** badge linking to the file.
- `doi` adds a badge with the DOI itself, linking to `https://doi.org/<doi>`.
- `code` adds a **Code** badge.
- `github` adds a **GitHub** badge linking to `https://github.com/<github>`.
- `badges` adds arbitrary badges from a list of `title`/`href` pairs.

## Tags

The tags taxonomy is rendered by `layouts/tags/taxonomy.html`, using `entries/tag.html`.

## Adding a content type

To add a new content type, create a section folder and give it a list template and an entry template:

1. Add `content/<section>/_index.md`.
2. Add `layouts/<section>/list.html` that calls the shared wrapper and your entry partial:
   ```go-html-template
   {{ define "main" }}
   
   {{ with partial "list-base.html" . }}
   	{{ partial "entries/<name>.html" . }}
   {{ end }}
   
   {{ end }}
   ```

3. Add `layouts/_partials/entries/<name>.html` to control how each item is rendered, using the existing templates as a starting point.

The homepage can display any section with the `collection` parameter, and pick its entry template with `entry`:

```yaml
collection:
  name: publications
  title: Publications
  entry: publication
```
