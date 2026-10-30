# setup-synchestra

Install an exact [Synchestra CLI](https://github.com/synchestra-io/synchestra) release in GitHub Actions without Go. This action installs the CLI only; workflows choose which commands to run. Release-provided license and notice files are kept alongside the executable. Self-hosted runners need PowerShell (`pwsh`); Unix runners also need `tar` and `chmod`.

`version` is required and must be an exact release tag such as `cli-v0.21.1`. `expected-sha256` optionally supplies an independently obtained digest for the selected archive. A checksum from the same release detects corruption but cannot authenticate a replaced release. Outputs include the installed tag and binary path.

The action supports Linux, macOS, and Windows on amd64 and arm64 where the requested release publishes those assets. The CLI release `cli-v0.21.1` does not have a Windows arm64 archive.

```yaml
- uses: synchestra-io/setup-synchestra@46a6e003a1e883bcae588c2f15fa046c4af63f5e
  with:
    version: cli-v0.21.1
- run: synchestra --version
```
