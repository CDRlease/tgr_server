# tgr_server

Public distribution repository for the smoke release flow of
`JiepengTan/tg_server`.

This repository does not store source code. During the smoke phase it only
stores release assets in GitHub Releases and validates them before notifying
`JiepengTan/tg_client`.

Current expected assets per tag:

- `tgr-server-smoke-<tag>.zip`
- `manifest.json`
- `SHA256SUMS.txt`

Required secret:

- `CLIENT_DISPATCH_TOKEN`: token used to send `repository_dispatch` events to
  `JiepengTan/tg_client`
