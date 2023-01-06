# Making documentation with Jupyter Book

### Env
```bash
python3 -m venv venv
source venv/bin/activate  # e.g. bash

python3 -m pip install -U pip
python3 -m pip install -r requirements.txt
```

### CLI tool
```bash
jupyter-book -h
```

`jb` is the short form
```bash
jb -h
```

### Create from template
```bash
jb create <name of the book>
```

For simplicity, `<NOB>` is used further to refer to the chosen `<name of the book>`.

### Building
Install requirements for the book (in `venv`)
```bash
python3 -m pip install -r <NOB>/requirements.txt
```

Building the html
```bash
jb build <NOB>
```

Note: page caching: `jb` only builds pages changed. To trigger a full re-build:
```bash
jb build --all <NOB>
```

### Github pages publish
The helper module for Github pages is already included in out-most `requirements.txt` (the `ghp-import` module). To propagate the built pages:

```bash
ghp-import -n -p -f <NOB>/_build/html
```

### Notes & Thoughts:
* Could be better: If a file is moved, e.g. to a directory, the relative links in the document would be broken. But there is no warning.
