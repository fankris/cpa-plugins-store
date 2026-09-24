# CPA Plugins Store

Public GitHub Release distribution for CPA / CLIProxyAPI native plugins.

This repository intentionally contains no Go source, tests, credentials, or
private build configuration. The source and build workflow remain in the
private [`fankris/cpa-plugins`](https://github.com/fankris/cpa-plugins)
repository.

## Add to CPA

```yaml
plugins:
  enabled: true
  dir: "plugins"
  store-sources:
    - "https://raw.githubusercontent.com/fankris/cpa-plugins-store/main/registry.json"
```

Registry URL:

<https://raw.githubusercontent.com/fankris/cpa-plugins-store/main/registry.json>

The registry uses CPA plugin store schema v1 and `github-release` installation.
CPA reads the latest GitHub Release from this repository, derives the plugin
version from the release tag, downloads the matching platform ZIP and verifies
`checksums.txt` before installing it.

## Published release

The current release is [`v1.0.31`](https://github.com/fankris/cpa-plugins-store/releases/tag/v1.0.31).
It provides Linux `amd64` artifacts for:

- `account-concurrency`
- `qoder`
- `workbuddy`

Each asset follows CPA's required naming convention:

```text
<plugin-id>_<release-version>_<goos>_<goarch>.zip
checksums.txt
```

Each ZIP contains only its matching dynamic library at the archive root. The
published plugin metadata uses `Aiseek` as the author name.

`trae` is intentionally not listed until its private source build is repaired;
no placeholder or non-installable binary is published.
