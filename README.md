## Basic Usage

```yaml
name: Doxygen GitHub Pages Deploy Action

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: Syndelis/cbindgen-action@VERSION
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          output: include/my_library.h
```