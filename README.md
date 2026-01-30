# Update Copyright Year GitHub Action

GitHub Action that updates the copyright year in file headers across your repository.

## What the project does

Scans files in selected directories and updates copyright header years using configurable `sed` regexps.

## Why the project is useful

Keeps year ranges in headers accurate with minimal maintenance, especially for repos with many files or templates.

## Getting started

1) Add the action to your workflow (see "Example workflow" below).
2) Optionally set `targets`, `exclude_paths`, and `headers_regexp`.
3) Run the workflow and review changes (optionally create a PR in your workflow).

## Inputs

| Name | Required | Default | Description |
| --- | --- | --- | --- |
| `targets` | No | `.` | Directories to scan (space-separated), e.g. `. src scripts` |
| `exclude_paths` | No | `.github/workflows` | Paths to exclude (space-separated), e.g. `.github/workflows build` |
| `include_glob` | No | *(empty)* | Optional glob patterns to include (space-separated), e.g. `**/*.{sh,py,js}` |
| `headers_regexp` | No | *(see below)* | Array of `sed` regexps (one per line). Use `{{CURRENT_YEAR}}` as a placeholder |

Default `headers_regexp`:

```text
s/^(.*Copyright[^0-9]*)([0-9]{4})(-[0-9]{4})?([[:space:]]+.*)?$/\1\2-{{CURRENT_YEAR}}\4/
```

Note: The action always performs a cleanup pass to collapse ranges like `2026-2026` back to `2026`.

## Examples

Update regex (default) matches both single years and ranges:

```text
Copyright 2021
Copyright (c) 2021-2024
Copyright 2021 ACME Inc.
```

Assuming the current year is 2026, the updates become:

```text
Copyright 2021-2026
Copyright (c) 2021-2026
Copyright 2021-2026 ACME Inc.
```

Cleanup regex (always applied) then collapses:

```text
Copyright 2026-2026
```

to:

```text
Copyright 2026
```

## Customization tips

Additional regex examples you can pass via `headers_regexp`:

```text
# Match "Copyright (c) 2019-2023" or "Copyright © 2019"
s/^(.*Copyright[^0-9]*)([0-9]{4})(-[0-9]{4})?([[:space:]]+.*)?$/\1\2-{{CURRENT_YEAR}}\4/

# Match "Copyright 2019, Company" (commas or extra text at end)
s/^(.*Copyright[^0-9]*)([0-9]{4})([[:space:]]*,.*)?$/\1\2-{{CURRENT_YEAR}}\3/
```

## Limitations

- Only files detected as `text/*` by the `file` command are edited.
- Uses GNU `sed` options available on `ubuntu-latest` runners.
- Include patterns are Bash globs matched against the file path (with or without a leading `./`).

## Example workflow

```yml
name: Update year in headers

on:
  workflow_dispatch:

jobs:
  update-year:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - uses: octivi/update-copyright-year@v1
        with:
          targets: ". src scripts"
          exclude_paths: ".github/workflows build"
          include_glob: "**/*.{sh,py,js}"
          headers_regexp: |
            s/^(.*Copyright[^0-9]*)([0-9]{4})(-[0-9]{4})?([[:space:]]+.*)?$/\1\2-{{CURRENT_YEAR}}\4/

      # Optional: create PR in your own workflow
      - name: Create Pull Request
        uses: peter-evans/create-pull-request@v8
        with:
          branch: update-year-in-headers
          delete-branch: true
          commit-message: "chore: Update year in headers"
          title: Update year in headers
          body: |
            Automated update of year in headers.
          labels: |
            automation
            maintenance
```

## Getting help

If you run into issues, open a GitHub issue in this repository and include a minimal reproduction (sample file + workflow snippet).

## Maintainers and contributors

Maintained by the [Octivi DevOps team](https://octivi.com/devops). Contributions are welcome via pull requests.
