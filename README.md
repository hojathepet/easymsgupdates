# EasyMsg Updates

Public binary-only update channel for EasyMsg. The private source repository remains separate.

- `latest.json`: published version, download URLs, and SHA-256 checksums
- `EasyMsgSetup.exe`: Windows installer used by the in-app updater
- `EasyMsg-Windows-x64.zip`: optional Windows x64 package

## Publish a Windows update

1. Merge the source change and download `EasyMsg-Windows-Installer` and `EasyMsg-Windows-x64` from a successful Windows CI run. Extract each artifact.
2. In a branch of this repository, replace `EasyMsgSetup.exe` and `EasyMsg-Windows-x64.zip` with the extracted files.
3. Update `latest.json` in the same branch. Set `version` to the version in the source `pubspec.yaml`, write release notes, and calculate each file's SHA-256 with `Get-FileHash` (PowerShell) or `sha256sum`.
4. Open a pull request. The validation workflow checks both files, hashes, and URLs. Merge the pull request only after it passes; the binaries and manifest then become live together.

Do not store tokens, private keys, source code, or temporary artifact URLs in this repository.
