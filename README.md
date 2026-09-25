# EasyMsg Updates

Public binary-only update channel for EasyMsg. The private source repository remains separate.

- `latest.json`: published version, download URLs, and SHA-256 checksums
- `EasyMsgSetup.exe`: Windows installer used by the in-app updater
- `EasyMsg-Windows-x64.zip`: optional Windows x64 package

## Publish a Windows update

The private source repository's **Publish Windows update** workflow builds and publishes these three files in one commit whenever a version bump reaches its `main` branch. It can also be started manually to retry a release. The source repository needs a one-time `EASYMSG_UPDATES_TOKEN` Actions secret with **Contents: Read and write** permission limited to this update repository. No file transfer is required for later releases.

The validation workflow in this repository checks the binaries, hashes, and URLs after publication and on pull requests.

Do not store tokens, private keys, source code, or temporary artifact URLs in this repository.
