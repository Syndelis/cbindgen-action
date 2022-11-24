## Basic Usage

```yaml
name: Cbindgen Action

on:
  push:
    paths:
      - '**/*.rs'

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: Syndelis/cbindgen-action@VERSION
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          output: include/my_library.h
```