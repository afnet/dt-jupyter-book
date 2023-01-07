---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Referencing and cross referencing

## Creating labels by titles
The following source code is used to create a hidden label `section-label-1` for the next section.
```
(section-label-1)=
## Cross-project refs
```

(section-label-1)=
## Cross-project refs


```{example}
Link to another [book11](other-book:section-label-1)

Or, with sphinx flavor:
{ref}`book11 <other-book:section-label-1>`
```

The referencing is achieved with [intersphinx](https://www.sphinx-doc.org/en/master/usage/extensions/intersphinx.html).
The reference comprises of the book name `other-book` and the label symbol `section-label-1`.

The book name is defined in `_config.yml` like below
```yaml
sphinx:
  ...
  config:
    intersphinx_mapping:
      other-book:
        - "https://afnet.github.io/book11"
        - null
```

To conveniently find the available label symbols in other books, a utility has been provided.
Take the above linked book for example:

```{prompt} bash
python -m sphinx.ext.intersphinx https://afnet.github.io/book11/objects.inv
```

Or, use it in a script (example outcomes provided below)

```{code-cell}
from sphinx.ext.intersphinx import inspect_main
inspect_main(["https://afnet.github.io/book11/objects.inv"])
```

## Ref to same book

```{example} Refer to the document from another source file
Here is a [reference back to the intro](../intro.md).
```

```{example} Refer to a section label
[Top section of this page](section-label-1)

Or, {ref}`back to the top section <section-label-1>`
```

Without contents in the `[]`, the original section title is taken. E.g.
```{example}
A ref to [](section-label-1).
```