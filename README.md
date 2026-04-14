# tgr_server

Public distribution repository for the formal server release flow of
`JiepengTan/tg_server`.

This repository does not store source code. It stores mirrored GitHub Release
assets from the source repository, validates the release manifest plus bundle
checksums, and then notifies
`JiepengTan/tg_client`.

Current expected assets per tag:

- `server-bin-linux-amd64.zip`
- `server-bin-linux-arm64.zip`
- `server-bin-darwin-amd64.zip`
- `server-bin-darwin-arm64.zip`
- `server-bin-windows-amd64.zip`
- `server-bin-windows-arm64.zip`
- `manifest.json`
- `SHA256SUMS.txt`

Current manifest contract for `server` releases:

- `mode` is `release`
- `component` is `server`
- each `bundles[]` entry carries `name`, `os`, `arch`, and a
  `bundle-entry-exists` validation with required bundle paths

Required secret:

- `CLIENT_DISPATCH_TOKEN`: token used to send `repository_dispatch` events to
  `JiepengTan/tg_client`
