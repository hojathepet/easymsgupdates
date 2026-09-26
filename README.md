# EasyMsg Updates

Public binary-only update channel for EasyMsg. The private source repository remains separate.

- `latest.json`: published version, download URLs, and SHA-256 checksums
- `EasyMsgSetup.exe`: Windows installer used by the in-app updater
- `EasyMsg-Windows-x64.zip`: optional Windows x64 package

## Publish a Windows update

The private source repository's **Publish Windows update** workflow builds and publishes these three files in one commit whenever a version bump reaches its `main` branch. It can also be started manually to retry a release. One-time setup uses a write-enabled SSH deploy key for this update repository, with its private key stored in the source repository's `EASYMSG_UPDATES_DEPLOY_KEY` Actions secret. A fine-grained `EASYMSG_UPDATES_TOKEN` with **Contents: Read and write** permission limited to this repository is also supported. No file transfer is required for later releases.

The validation workflow in this repository checks the binaries, hashes, and URLs after publication and on pull requests.

Do not store tokens, private keys, source code, or temporary artifact URLs in this repository.
