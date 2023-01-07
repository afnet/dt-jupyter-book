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

# Trying different contents (.md)

This page contains some random components.

## Customized Prompts

Prompt that is not selected
```{prompt}
:language: bash
:prompts: 💻

cd <folder>
cd -
```

```{prompt}
:language: bash
:prompts: 🤖

vi /etc/wpa_supplicant.conf
```

## Code executed

```{code-cell}
# print 100 empty lines
for i in range(100):
    print('placeholder')
```

Here is a [reference back to the intro](../intro.md). Here's a ref to [](section-label-1).