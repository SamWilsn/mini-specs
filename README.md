mini-specs
==========

A trimmed down version of the [execution-specs](https://github.com/ethereum/execution-specs/) that's hopefully faster to render.

## Easy Mode

Quick way to get started generating documentation, but limited in what you can edit.

### Setup

```bash
$ git clone https://github.com/SamWilsn/mini-specs
$ cd mini-specs
$ python3 -m venv venv
$ . ./venv/bin/activate

(venv) $ pip install tox
```

### Render

This should render the documentation and print the location of the output files:

```bash
(venv) $ tox
```

If, for some reason, this doesn't pick up your changes, try:

```bash
(venv) $ tox --recreate
```

## Harder Mode

The Easy Mode above doesn't allow you to modify the HTML templates or core CSS. For that, you need:

### Setup

```bash
$ git clone --recurse-submodules https://github.com/SamWilsn/docc
$ git clone --branch=docc https://github.com/ethereum/execution-specs
$ git clone https://github.com/SamWilsn/mini-specs
$ python3 -m venv venv-big
$ . ./venv-big/bin/activate

(venv-big) $ pip install -e ./mini-specs[doc]
(venv-big) $ pip install -e ./execution-specs
(venv-big) $ pip install -e ./docc
```

### Render

```bash
(venv-big) $ cd mini-specs
(venv-big) $ docc
```
