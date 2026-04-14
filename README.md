# tgr_server

Public distribution repository for the formal server release flow of
`JiepengTan/tg_server`.

This repository does not store source code. It stores mirrored GitHub Release
assets from the source repository, validates the release manifest plus bundle
checksums, and then notifies
`JiepengTan/tg_client`.

Current expected assets per tag:

- `server-linux-amd64.zip`
- `server-linux-arm64.zip`
- `server-osx-amd64.zip`
- `server-osx-arm64.zip`
- `server-win-amd64.zip`
- `server-win-arm64.zip`
- `manifest.json`
- `SHA256SUMS.txt`

Current manifest contract for `server` releases:

- `mode` is `release`
- `component` is `server`
- each `bundles[]` entry uses `name=server-{os}-{arch}.zip`
- each `bundles[]` entry uses `os=linux|osx|win`
- each `bundles[]` entry uses `arch=amd64|arm64`
- each `bundles[]` entry carries `name`, `os`, `arch`, and a
  `bundle-entry-exists` validation with required bundle paths

Required secret:

- `CLIENT_DISPATCH_TOKEN`: token used to send `repository_dispatch` events to
  `JiepengTan/tg_client`
