# Cbindgen Action

GitHub Action for automatically generating C bindings for your Rust `staticlibrary`/`cylib` create.


## Basic Usage
---

Create a new file at `.github/workflows/any-name-here.yml` with the following contents:

```yaml
name: Cbindgen Action

on:
  push:
    paths:
      - '**/*.rs'

jobs:
  cbuild:
    runs-on: ubuntu-latest
    steps:
      - uses: Syndelis/cbindgen-action@v1.1.0
        with:
          output: include/my_header.h
          github_token: ${{ secrets.GITHUB_TOKEN }}
```

Then, any commits that create/alter/delete Rust files (`.rs`) will run the action when pushed to GitHub, creating a new `include/my_header.h` file after completing the run. This will work regarless of the branch you push your commits on.

## Options
---

The following options are available to use under the `with` tag:

- `github_token`: A GitHub token with pull/push permission. Use the variable **`${{ secrets.GITHUB_TOKEN }}`** to automatically use the commiter's token;

- `output`: The generated file's path;

- `config` *(optional)*: The file containing your `cbindgen` configuration. Grab an example [here](https://github.com/eqrion/cbindgen/blob/master/template.toml)! The default value is `cbindgen.toml`; 

## Acknowledgments
---

This action was inspired by the following actions, which I highly recommend checking out:

- [Doxygen GH Pages Action](https://github.com/DenverCoder1/doxygen-github-pages-action) by [Jonah Lawrence](https://github.com/DenverCoder1/): A GitHub Action for automatically building Doxygen documentation and publishing it to [GitHub Pages](https://pages.github.com/);

- [VHS Action](https://github.com/charmbracelet/vhs-action) by the [Charmbracelet Team](https://charm.sh/): A GitHub Action for automatically generating GIFs for CLI programs.
