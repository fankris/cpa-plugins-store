# CPA Plugins Store

Public binary distribution for CPA / CLIProxyAPI native plugins.

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

The registry uses CPA plugin store schema v2 and direct, SHA-256-pinned HTTPS
artifacts. Each artifact is a ZIP whose target dynamic library is at the ZIP
root, as required by CPA's native plugin installer.

## Published platforms

The initial public release provides Linux `amd64` artifacts for:

- `account-concurrency` `0.3.0`
- `qoder` `0.8.6`
- `workbuddy` `0.9.18`

Additional platforms can be added without exposing the private source tree.
`trae` is intentionally not listed until its private source build is repaired;
no placeholder or non-installable binary is published.

## Releases

Release assets are published under the `v1.0.0` distribution release. Each ZIP
contains only its matching plugin library at the archive root. Checksums are
recorded in [`checksums.txt`](https://github.com/fankris/cpa-plugins-store/releases/download/v1.0.0/checksums.txt).
